---
title: Coexistência com o Skype for Business
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: Comportamento de coexistência entre Teams & Skype for Business, incluindo parâmetros de roteamento, roteamento de chamadas de chat &, chats & chamadas de threads pré-existentes, & presença.
ms.openlocfilehash: 5c32e99ad7cd74966cc7d8f22bd19a2520249b85
ms.sourcegitcommit: a5b80ad33b4ee9505ea2be1a37f5ec2d8bf5ba76
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2021
ms.locfileid: "61042362"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistência com o Skype for Business

A coexistência e a interoperabilidade entre Skype for Business e Teams clientes são controladas por modos de coexistência. Para obter mais informações, consulte [Diretrizes de migração](migration-interop-guidance-for-teams-with-skype.md)e interoperabilidade para organizações que usam Teams em conjunto com Skype for Business . Após a aposentadoria do Skype for Business Online, em 31 de julho de 2021, os usuários que estão na nuvem são sempre usuários do TeamsOnly. Não é mais possível atribuir um modo de coexistência diferente do TeamsOnly a um usuário online. Modos de coexistência diferentes do TeamsOnly só são relevantes para organizações com implantações locais de Skype for Business Server ou Lync Server 2013. Neste artigo, qualquer referência a "Skype for Business Server" também se aplica ao Lync Server 2013.


## <a name="determining-a-users-coexistence-mode"></a>Determinando o modo de coexistência de um usuário
Todos os usuários em organizações sem qualquer implantação local do Skype for Business Server são o modo TeamsOnly, e o modo efetivo do locatário também é o TeamsOnly. Isso pode ser confirmado analisando a propriedade TeamsUpgradeEffectiveMode no locatário ou o usuário usando Teams PowerShell.   Antes da reforma do Skype for Business Online, em 31 de julho de 2021, as organizações tinham a capacidade de alterar o modo de coexistência para o usuário ou o locatário. Isso não é mais possível, exceto para organizações com uma implantação local do Skype for Business Server, que não deve ter o modo de locatário do TeamsOnly. Você pode confirmar que o modo de coexistência não poderá mais ser alterado se TeamsUpgradePolicyIsReadOnly = "ModeAndNotifications" no usuário ou no locatário.  (TeamsUpgradePolicyIsReadOnly em qualquer usuário terá o mesmo valor que o valor do locatário.)  


 ```powershell
 //Check if Tenant is TeamsOnly and if mode is read only.
$t=Get-CsTenant
$t|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications

 //Check if user is TeamsOnly and if mode is read only.
$u=Get-CsOnlineUser
$u|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications
 ```

Em uma organização com uma implantação local do Skype for Business Server, a política global de locatários do TeamsUpgradePolicy pode ter qualquer modo diferente do *TeamsOnly*. Os modos permitidos são: *SfBOnly*, *SfBWithTeamsCollab* e *SfBWithTeamsCollabAndMeetings*. Os usuários também podem ser atribuídos diretamente a uma instância do TeamsUpgradePolicy, que seria supersedida da política global do locatário.  Os usuários que estão na nuvem devem ser o TeamsOnly, e os usuários que estão no local devem ser qualquer modo diferente do TeamsOnly.  Se um usuário não receber uma instância do TeamsUpgradePolicy, o usuário receberá o valor da política global do locatário. 

## <a name="routing-parameters"></a>Parâmetros de roteamento

O modo de coexistência do destinatário determina o comportamento de chats, chamadas e presença, tanto em um locatário quanto em locatários federados. Se o remetente estiver usando Teams, a decisão de roteamento será tomada ao criar um novo thread de conversa. Depois que um thread de conversa é criado, seu roteamento não muda e mantém o método de roteamento determinado quando o thread foi criado.

Os métodos de roteamento de thread são:

- *nativo* para um Teams para Teams conversa no locatário
- *interop* para um Teams para Skype for Business conversa no locatário
- *federado nativo para* uma conversa federada entre locatários quando ambos os usuários têm o modo TeamsOnly. 
- *interop federado para* uma conversa federada entre locatários que depende da interopção entre Skype for Business e Teams.

> [!NOTE]
> - As conversas nativas, seja nos mesmos cenários de locatário ou federado, ocorrem quando o receptor e o remetente têm o modo TeamsOnly. A conversa será uma experiência de chat nativa, que inclui todos os recursos avançados de mensagens e chamada. Para saber mais, leia [Experiência de chat nativa para usuários externos (federados) no Teams](native-chat-for-external-users.md). 
> - Se um dos participantes da conversa não tiver o modo TeamsOnly, a conversa será uma experiência de interop com mensagens somente texto.
> - Comunicações federadas entre usuários do TeamsOnly em nuvens de vários locatários e ambientes de nuvem especiais (por exemplo, nuvens do governo) aparecerão como chats federados de interop.


Ao criar uma nova conversa, os fatores que determinam como o thread é roteado são:

- O modo de coexistência do destinatário
- O cliente usado pelo remetente
- Se a conversa está no locatário ou federada
- Se a conversa é possível. Se um usuário tiver uma conta Skype for Business local, esse usuário não poderá usar o cliente Teams para interoperabilidade no locatário ou para federação. Esse usuário só pode usar o cliente Skype for Business para interoperabilidade e federação. Observe que Teams para Teams comunicação é sempre possível no locatário.

## <a name="chat-and-call-routing"></a>Roteamento de chat e chamadas
As tabelas abaixo mostram qual cliente em um determinado modo receberá uma chamada do originador (três colunas mais à esquerda). Qual cient recebe a chamada depende do modo do originador, do cliente escolhido e de onde a conta Skype for Business está em casa (local ou online).

Nas tabelas a seguir:

- **Skype for Business** _ representa qualquer um dos seguintes modos: _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.
- *O texto itálico realça* uma conversa de interop.
- **Not Possible** representa uma situação na qual o chat ou chamada não é possível. O originador deve usar Skype for Business em vez disso nesses casos. Este é um dos motivos pelos quais a orientação prescritiva da Microsoft para clientes locais e híbridos é usar um modo diferente de Ilhas (normalmente SfBWithTeamsCollab) como o ponto de partida para sua jornada de atualização para Teams.


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Roteamento no locatário para novos chats ou chamadas

As tabelas abaixo capturam o roteamento de chat e chamadas no locatário e são válidas para novas chamadas ou chats que não são iniciados a partir de um thread pré-existente. Ele descreve qual cliente receberá uma nova chamada ou chat, se originado por um usuário à esquerda, para um usuário destinatário no locatário à direita.  Mensagens enviadas para os usuários do TeamsOnly sempre serão roteadas para Teams. Mensagens enviadas para Skype for Business usuários sempre serão roteadas para Skype for Business. As mensagens enviadas aos usuários das Ilhas sempre serão roteadas para o mesmo cliente do qual foram enviadas.


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabela 1a: novo chat no locatário ou roteamento de chamadas para um destinatário do modo TeamsOnly

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype for Business &nbsp; homed|<br><br>Route->|Destinatário teamsOnly|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Ilhas|Teams <br> Skype for Business| Local <br> Local|&boxv;<br>&boxv;|Teams <br> *Microsoft Teams*|
|Skype for Business | Skype for Business | Local|&boxv;|*Microsoft Teams*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>Tabela 1b: novo chat no locatário ou roteamento de chamadas para um destinatário do modo de ilhas

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype for Business &nbsp; homed|<br><br>Route->|Destinatário de Ilhas|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Ilhas| Teams <br> Skype for Business|Local<br>Local|&boxv;<br>&boxv;| Teams <br> Skype for Business|
|Skype for Business |Skype for Business | Local|&boxv;| Skype for Business|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>Tabela 1c: novo chat no locatário ou roteamento de chamadas para um destinatário em Skype for Business modo

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype for Business &nbsp; homed|<br><br>Route->|Skype for Business Destinatário|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Ilhas|Teams <br> Skype for Business| Local <br> Local|&boxv;<br>&boxv;| **Não é possível** <br> Skype for Business|
|Skype for Business | Skype for Business| Local|&boxv;| Skype for Business|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>Roteamento federado para novos chats ou chamadas

As tabelas abaixo capturam o roteamento de chamadas e chats federados e são válidas para novas chamadas ou chats. Eles descrevem qual cliente receberá uma nova chamada ou chat, se originado por um usuário à esquerda, para um usuário de destino federado à direita. Em resumo, se a conversa for possível conforme descrito acima, as mensagens enviadas aos usuários do TeamsOnly sempre chegarão em Teams; as mensagens enviadas para o modo Skype for Business os usuários sempre chegarão em Skype for Business; as mensagens enviadas aos usuários das Ilhas sempre chegarão Skype for Business  independentemente do cliente do qual eles foram enviados. 

O roteamento para chats e chamadas federados difere do roteamento no locatário, pois os usuários das Ilhas sempre receberão uma comunicação federada no Skype for Business. Isso porque o parceiro federado pode ainda não estar usando Teams. O roteamento para Skype for Business para qualquer modo de ilhas garante que as mensagens sempre serão recebidas.  O roteamento Teams pode resultar em comunicação perdida se o destinatário pretendido não usar Teams. 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabela 2a: novo chat federado ou roteamento de chamadas para um destinatário do modo TeamsOnly

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype for Business homed|<br><br>Route->|Destinatário teamsOnly|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Ilhas|Teams <br> Skype for Business|Local <br> Local|&boxv;<br>&boxv;|**Não é possível** <br> *Microsoft Teams*|
|Skype for Business |Skype for Business|Local|&boxv;| *Microsoft Teams*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>Tabela 2b: novo chat federado ou roteamento de chamadas para um destinatário das Ilhas

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype for Business homed|<br><br>Route->|Destinatário de Ilhas|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Ilhas|Teams <br> Skype for Business| Local <br> Local|&boxv;<br>&boxv;| **Não é possível** <br> Skype for Business|
|Skype for Business |Skype for Business| Local|&boxv;| Skype for Business|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>Tabela 2c: novo chat federado ou roteamento de chamadas para um destinatário em Skype for Business modo

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype for Business homed|<br><br>Route->|Skype for Business Destinatário|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Ilhas|Teams <br> Skype for Business| Local <br> Local|&boxv;<br>&boxv;|**Não é possível** <br> Skype for Business|
|Skype for Business |Skype for Business|Local|&boxv;<br>&boxv;|Skype for Business|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats e chamadas de threads pré-existentes

### <a name="from-teams"></a>De Teams

Chamadas ou chats iniciados a partir de um thread de conversa pré-existente no Teams são roteados da mesma maneira que esse thread. Se o thread pré-existente no Teams era um thread nativo (ou seja, roteado para Teams), mensagens de chat adicionais e chamadas desse thread serão Teams. Se foi um thread de interop (ou seja, roteado para Skype for Business), mensagens de chat e chamadas adicionais serão enviadas para Skype for Business (supondo que as opções de roteamento estão disponíveis).

> [!NOTE]
> É possível que threads pré-existentes no Teams não sejam mais table, como quando o thread era um thread de interop para um usuário que foi atualizado para Teams. Como ele foi criado como um thread de interop, o thread seria roteado para Skype for Business, mas esse usuário não pode mais usar Skype for Business para chat e chamada. Nesse caso, o thread será desabilitado e não permitirá mais comunicação.

### <a name="from-skype-for-business"></a>De Skype for Business

Skype for Business threads não persistem além do tempo de sessão SIP de 10 minutos. Chats e chamadas de um thread existente no Skype for Business antes da expiração da sessão SIP serão roteados da mesma maneira que o thread. Chamadas e chats de um thread existente no Skype for Business além do tempo de sessão SIP serão roteados para o Skype for Business da parte remota, independentemente de qual cliente o thread original veio do lado da outra parte.

## <a name="presence"></a>Presença

Em situações em que alguns usuários estão usando o cliente Teams e outros estão usando o cliente Skype for Business, é possível que alguns desses usuários usem ambos os clientes. É importante entender que a Presença é publicada com base no modo de coexistência de um usuário. Por exemplo, se um chat ou chamada de um originador deve chegar no cliente de Skype for Business do destino, então é a presença do cliente Skype for Business que deve ser mostrada ao originador. Se ele deve chegar no cliente Teams do destino, então é a presença do cliente Teams que deve ser mostrada.

A presença é compartilhada com base no modo de coexistência de um usuário conforme descrito abaixo:

- Se um usuário estiver no modo TeamsOnly, qualquer outro usuário (Teams ou Skype for Business) verá que a presença Teams usuário do TeamsOnly
- Se um usuário estiver em qualquer um dos modos Skype for Business (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), qualquer outro usuário (seja no Teams ou no Skype for Business) verá que o Skype for Business do usuário Skype for Business presença
- Se um usuário estiver no modo Ilhas, a presença no Teams e a presença no Skype for Business são independentes (os valores não precisam corresponder) e outros usuários verão uma ou outra presença do usuário das Ilhas, dependendo se eles estão no mesmo locatário ou em um locatário federado e qual cliente eles usam
  - A partir Teams, qualquer outro usuário no mesmo locatário verá a presença Teams do usuário das Ilhas; isso é alinhado com a tabela de roteamento no locatário acima
  - A partir Teams, qualquer outro usuário em um locatário federado verá a presença Skype for Business do usuário das Ilhas; isso é alinhado com a tabela de roteamento federado acima
  - A partir Skype for Business, qualquer outro usuário verá a presença Skype for Business do usuário das Ilhas (no locatário e federado); isso é alinhado com as tabelas de roteamento acima

### <a name="in-tenant-presence"></a>Presença no locatário

Mensagens enviadas para os usuários do TeamsOnly sempre chegarão Teams. As mensagens enviadas para Skype for Business modo de usuário sempre chegarão Skype for Business, se a conversa for possível, conforme descrito acima. As mensagens enviadas aos usuários das Ilhas sempre chegarão no cliente de onde foram originadas.

A tabela descreve Publisher presença do Publisher que será vista por um Watcher, dependendo do modo do Publisher e do cliente do Watcher (para um novo thread).

#### <a name="table-3-in-tenant-presence-new-thread"></a>Tabela 3: presença no locatário (novo thread)

<br>

|Watcher<br><br>Cliente|<br><br>Route->|<br><br>Ilhas|Publisher<br><br>Skype for Business|<br>Teams Somente|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Teams|Skype for Business|Teams|
|||||

### <a name="federated-presence"></a>Presença federada

A presença federada baseia-se na capacidade de acesso federada mostrada na tabela 2.  A tabela a seguir descreve a presença do Publisher que será vista por um Watcher, dependendo do modo do Publisher e do cliente do Watcher (para um novo thread). Na prática, o cliente do Watcher não faz diferença na federação neste estágio.

#### <a name="table-4-federated-presence-new-thread"></a>Tabela 4: presença federada (novo thread)

<br>

|Watcher<br><br>Cliente|<br><br>Route->|<br><br>Ilhas|Publisher<br><br>Skype for Business|<br><br>Teams Somente|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Skype for Business|Skype for Business|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>Presença em threads pré-existentes

Para alinhar a presença e a capacidade de alcance em threads pré-existentes, a presença do destino exposta nesse thread precisa ser alinhada com o roteamento do thread, supondo que o roteamento seja possível.  Em particular, se um destinatário com o que você tinha anteriormente um thread de conversa de interop persistente foi atualizado para Teams, esse thread não refletirá mais a presença precisa e não será mais routable. Você deve iniciar um novo thread.

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>Federação e interopção com Office 365 operado pela 21Vianet

A federação e a interopção entre os Office 365 e Office 365 operados pela 21Vianet são suportados quando os usuários de vários locatários Office 365 estão no modo Somente Teams. Nesse cenário, os usuários Skype for Business Online no Office 365 operados pela 21Vianet poderão se comunicar com o Teams Somente usuários em vários Office 365 por meio de chats e chamadas. A tabela a seguir mostra os cenários com suporte nesta configuração:
 
|Cenário|Origem|Destinatário|Com suporte?|
|---|---|---|---|
|Presença|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sim<br>Sim|
|Chat|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sim (somente 1:1)<br>Sim(somente 1:1)|
|Chamadas de áudio|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sim (somente 1:1)<br>Sim (somente 1:1)|
|Chamadas de vídeo|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sim (somente 1:1)<br>Sim (somente 1:1)|
|Compartilhamento de tela|Teams <br> Skype for Business <br> | Skype for Business <br> Teams |Sim (por meio de uma reunião Teams promoção)<br>Sim (por meio de uma reunião Skype for Business promoção)|
|||||


## <a name="related-links"></a>Links relacionados
[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

[Vídeo: Gerenciar coexistência e interoperabilidade entre Skype for Business e Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
