---
title: Coexistência com o Skype for Business
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: O comportamento de coexistência entre o Teams & Skype for Business, incluindo parâmetros de roteamento, roteamento de chamadas & chat, chats & chamadas de threads pré-existentes, & presença.
ms.openlocfilehash: bd3bd0c2cfad9dc06ae53ae6e26496fb48561874
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562390"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistência com o Skype for Business

A coexistência e a interoperabilidade entre Skype for Business e clientes do Teams são controladas por modos de coexistência. Para obter mais informações, consulte [as diretrizes de migração e interoperabilidade para organizações que usam o Teams junto com Skype for Business](migration-interop-guidance-for-teams-with-skype.md). Após a desativação do Skype for Business Online em 31 de julho de 2021, os usuários hospedados na nuvem são sempre usuários do TeamsOnly. Não é mais possível atribuir um modo de coexistência diferente do TeamsOnly a um usuário online. Modos de coexistência diferentes do TeamsOnly só são relevantes para organizações com implantações locais do Skype for Business Server ou Lync Server 2013. Neste artigo, qualquer referência a "Skype for Business Server" também se aplica ao Lync Server 2013.


## <a name="determining-a-users-coexistence-mode"></a>Determinando o modo de coexistência de um usuário
Todos os usuários em organizações sem nenhuma implantação local do Skype for Business Server são o modo TeamsOnly, e o modo efetivo do locatário também é TeamsOnly. Isso pode ser confirmado examinando a propriedade TeamsUpgradeEffectiveMode no locatário ou o usuário usando o Teams PowerShell.   Antes da desativação do Skype for Business Online em 31 de julho de 2021, as organizações tinham a capacidade de alterar o modo de coexistência para o usuário ou o locatário. Isso não é mais possível, exceto para organizações com uma implantação local do Skype for Business Server, que não deve ter o modo de todo o locatário do TeamsOnly. Você pode confirmar que o modo de coexistência não poderá mais ser alterado se TeamsUpgradePolicyIsReadOnly = "ModeAndNotifications" no usuário ou no locatário.  (TeamsUpgradePolicyIsReadOnly em qualquer usuário terá o mesmo valor que o valor do locatário.)  


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

Em uma organização com uma implantação local do Skype for Business Server, a política global de locatário para TeamsUpgradePolicy pode ter qualquer modo diferente do *TeamsOnly*. Os modos permitidos são: *SfBOnly*, *SfBWithTeamsCollab* e *SfBWithTeamsCollabAndMeetings*. Os usuários também podem receber diretamente uma instância do TeamsUpgradePolicy, que substituiria a política global do locatário.  Os usuários hospedados na nuvem devem ser TeamsOnly e os usuários hospedados no local devem ser qualquer modo diferente do TeamsOnly.  Se um usuário não receber uma instância do TeamsUpgradePolicy, o usuário receberá o valor da política global do locatário. 

## <a name="routing-parameters"></a>Parâmetros de roteamento

O modo de coexistência do destinatário determina o comportamento de chats, chamadas e presença, dentro de um locatário e entre locatários federados. Se o remetente estiver usando o Teams, a decisão de roteamento será tomada ao criar um novo thread de conversa. Depois que um thread de conversa é criado, seu roteamento não é alterado e retém o método de roteamento determinado quando o thread foi criado.

Os métodos de roteamento de thread são:

- *nativo* para uma conversa do Teams para o Teams no locatário
- *interoperabilidade* de um Teams para Skype for Business conversa no locatário
- *federado nativo* para uma conversa federada entre locatários quando ambos os usuários têm o modo TeamsOnly. 
- *interoperabilidade federada* para uma conversa federada entre locatários que depende da interoperabilidade entre o Skype for Business e o Teams.

> [!NOTE]
> - Conversas nativas, seja no mesmo locatário ou em cenários federados, ocorrem quando o destinatário e o remetente têm o modo TeamsOnly. A conversa será uma experiência de chat nativa, que inclui todos os recursos avançados de mensagens e chamadas. Para saber mais, leia [a experiência de chat nativo para usuários externos (federados) no Teams](native-chat-for-external-users.md). 
> - Se um dos participantes da conversa não tiver o modo TeamsOnly, a conversa será uma experiência de interoperabilidade com mensagens somente de texto.
> - As comunicações federadas entre usuários do TeamsOnly em nuvens multilocatário e ambientes de nuvem especiais (por exemplo, nuvens governamentais) aparecerão como chats federados de interoperabilidade.


Ao criar uma nova conversa, os fatores que determinam como o thread é roteado são:

- O modo de coexistência do destinatário
- O cliente usado pelo remetente
- Se a conversa está no locatário ou federada
- Se a conversa é possível. Se um usuário tiver uma Skype for Business local, esse usuário não poderá usar o cliente do Teams para interoperabilidade no locatário ou para federação. Esse usuário só pode usar o cliente Skype for Business para interoperabilidade e federação. Observe que a comunicação do Teams com o Teams é sempre possível no locatário.

## <a name="chat-and-call-routing"></a>Roteamento de chat e chamada
As tabelas a seguir mostram qual cliente em um determinado modo receberá uma chamada do originador (três colunas mais à esquerda). Qual cient recebe a chamada depende do modo do originador, do cliente escolhido e de onde a conta Skype for Business está habilitada (local ou online).

Nas tabelas a seguir:

- **Skype for Business** _ representa qualquer um dos seguintes modos: _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.
- *O texto em itálico* realça uma conversa de interoperabilidade.
- **Not Possible** representa uma situação em que o chat ou chamada não é possível. O originador deve usar Skype for Business em vez disso nesses casos. Esse é um dos motivos pelos quais a orientação prescritiva da Microsoft para clientes locais e híbridos é usar um modo diferente de Ilhas (normalmente SfBWithTeamsCollab) como o ponto de partida para sua jornada de atualização para o Teams.


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Roteamento no locatário para novos chats ou chamadas

As tabelas a seguir capturam o roteamento de chat e chamadas no locatário e são válidas para novas chamadas ou chats que não são iniciados de um thread pré-existente. Ele descreve qual cliente receberá uma nova chamada ou chat, se originado por um usuário à esquerda, para um usuário destinatário no locatário à direita.  As mensagens enviadas aos usuários do TeamsOnly sempre serão roteadas para o Teams. As mensagens enviadas Skype for Business usuários sempre serão roteadas para Skype for Business. As mensagens enviadas aos usuários das Ilhas sempre serão roteadas para o mesmo cliente do qual foram enviados.


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabela 1a: novo chat no locatário ou roteamento de chamadas para um destinatário do modo TeamsOnly

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>&nbsp;Skype for Business homed|<br><br>Rota – >|Destinatário do TeamsOnly|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Ilhas|Teams <br> Skype for Business| Local <br> Local|&boxv;<br>&boxv;|Teams <br> *Microsoft Teams*|
|Skype for Business | Skype for Business | Local|&boxv;|*Microsoft Teams*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>Tabela 1b: novo chat no locatário ou roteamento de chamada para um destinatário do modo ilhas

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>&nbsp;Skype for Business homed|<br><br>Rota – >|Destinatário das Ilhas|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Ilhas| Teams <br> Skype for Business|Local<br>Local|&boxv;<br>&boxv;| Teams <br> Skype for Business|
|Skype for Business |Skype for Business | Local|&boxv;| Skype for Business|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>Tabela 1c: novo chat no locatário ou roteamento de chamadas para um destinatário em um Skype for Business no locatário

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>&nbsp;Skype for Business homed|<br><br>Rota – >|Skype for Business destinatário|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Ilhas|Teams <br> Skype for Business| Local <br> Local|&boxv;<br>&boxv;| **Não é possível** <br> Skype for Business|
|Skype for Business | Skype for Business| Local|&boxv;| Skype for Business|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>Roteamento federado para novos chats ou chamadas

As tabelas a seguir capturam o roteamento de chamadas e chats federados e são válidas para novas chamadas ou chats. Eles descrevem qual cliente receberá uma nova chamada ou chat, se originado por um usuário à esquerda, para um usuário de destino federado à direita. Em resumo, se a conversa for possível, conforme descrito acima, as mensagens enviadas aos usuários do TeamsOnly sempre chegarão ao Teams; as mensagens enviadas Skype for Business modo de usuário sempre chegarão ao Skype for Business; as mensagens enviadas aos usuários das Ilhas sempre chegarão Skype for Business independentemente do cliente do qual foram enviados. 

O roteamento para chats e chamadas federados difere do roteamento no locatário, já que os usuários das Ilhas sempre receberão uma comunicação federada em Skype for Business. Isso ocorre porque o parceiro federado ainda não está usando o Teams. O roteamento Skype for Business para qualquer tipo de receita no modo de ilhas garante que as mensagens sempre serão recebidas.  O roteamento para o Teams pode resultar em comunicação perdida se o destinatário pretendido não usar o Teams. 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabela 2a: novo chat federado ou roteamento de chamadas para um destinatário do modo TeamsOnly

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype for Business hospedado|<br><br>Rota – >|Destinatário do TeamsOnly|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|Ilhas|Teams <br> Skype for Business|Local <br> Local|&boxv;<br>&boxv;|**Não é possível** <br> *Microsoft Teams*|
|Skype for Business |Skype for Business|Local|&boxv;| *Microsoft Teams*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>Tabela 2b: novo chat federado ou roteamento de chamada para um destinatário das Ilhas

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype for Business hospedado|<br><br>Rota – >|Destinatário das Ilhas|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Ilhas|Teams <br> Skype for Business| Local <br> Local|&boxv;<br>&boxv;| **Não é possível** <br> Skype for Business|
|Skype for Business |Skype for Business| Local|&boxv;| Skype for Business|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>Tabela 2c: novo chat federado ou roteamento de chamadas para um destinatário em Skype for Business modo

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>Skype for Business hospedado|<br><br>Rota – >|Skype for Business destinatário|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|Ilhas|Teams <br> Skype for Business| Local <br> Local|&boxv;<br>&boxv;|**Não é possível** <br> Skype for Business|
|Skype for Business |Skype for Business|Local|&boxv;<br>&boxv;|Skype for Business|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats e chamadas de threads pré-existentes

### <a name="from-teams"></a>Do Teams

Chamadas ou chats iniciados a partir de um thread de conversa pré-existente no Teams são roteados da mesma maneira que esse thread. Se o thread pré-existente no Teams fosse um thread nativo (ou seja, roteado para o Teams), mensagens de chat e chamadas adicionais desse thread irão para o Teams. Se for um thread de interoperabilidade (ou seja, roteado para Skype for Business), mensagens de chat e chamadas adicionais serão enviadas para Skype for Business (supondo que as opções de roteamento estejam disponíveis).

> [!NOTE]
> É possível que threads pré-existentes no Teams não sejam mais roteáveis, como quando o thread era um thread de interoperabilidade para um usuário que foi atualizado para o Teams. Como ele foi criado como um thread de interoperabilidade, o thread seria roteado para Skype for Business, mas esse usuário não pode mais usar Skype for Business para chat e chamada. Nesse caso, o thread será desabilitado e não permitirá mais comunicação.

### <a name="from-skype-for-business"></a>De Skype for Business

Skype for Business threads não persistem além do tempo limite da sessão SIP de 10 minutos. Chats e chamadas de um thread existente Skype for Business antes da expiração da sessão SIP serão roteados da mesma maneira que o thread. Chamadas e chats de um thread existente no Skype for Business além do tempo limite da sessão SIP serão roteados para o Skype for Business da parte remota, independentemente de qual cliente o thread original veio do lado da outra parte.

## <a name="presence"></a>Presença

Em situações em que alguns usuários estão usando o cliente do Teams e outros estão usando o Skype for Business cliente, é possível que alguns desses usuários estejam usando ambos os clientes. É importante entender que a Presença é publicada com base no modo de coexistência de um usuário. Por exemplo, se o chat ou a chamada de um originador deve chegar ao cliente Skype for Business do destino, então é a presença do cliente Skype for Business que deve ser mostrada ao originador. Se ele deve chegar ao cliente do Teams do destino, então é a presença do cliente do Teams que deve ser mostrada.

A presença é compartilhada com base no modo de coexistência de um usuário, conforme descrito abaixo:

- Se um usuário estiver no modo TeamsOnly, qualquer outro usuário (no Teams ou no Skype for Business) verá a presença do Teams do usuário do TeamsOnly
- Se um usuário estiver em qualquer um dos modos Skype for Business (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), qualquer outro usuário (no Teams ou no Skype for Business) verá a presença de Skype for Business do Skype for Business
- Se um usuário estiver no modo Ilhas, a presença no Teams e a presença no Skype for Business serão independentes (os valores não precisam corresponder) e outros usuários verão uma ou outra presença do usuário das Ilhas, dependendo se estiverem no mesmo locatário ou em um locatário federado e qual cliente usarem
  - No Teams, qualquer outro usuário dentro do mesmo locatário verá a presença do Teams do usuário das Ilhas; isso está alinhado com a tabela de roteamento no locatário acima
  - No Teams, qualquer outro usuário em um locatário federado verá a presença do usuário das Ilhas Skype for Business; isso está alinhado com a tabela de roteamento federado acima
  - A partir Skype for Business, qualquer outro usuário verá a presença de Skype for Business do usuário das Ilhas (tanto no locatário quanto federado); isso é alinhado com as tabelas de roteamento acima

### <a name="in-tenant-presence"></a>Presença no locatário

As mensagens enviadas aos usuários do TeamsOnly sempre chegarão ao Teams. As mensagens enviadas para Skype for Business modo de usuário sempre chegarão Skype for Business, se a conversa for possível, conforme descrito acima. As mensagens enviadas aos usuários das Ilhas sempre chegarão ao cliente do qual foram originados.

A tabela descreve a presença do Publicador que será vista por um Observador, dependendo do modo do Publicador e do cliente do Observador (para um novo thread).

#### <a name="table-3-in-tenant-presence-new-thread"></a>Tabela 3: presença no locatário (novo thread)

<br>

|Observador<br><br>Cliente|<br><br>Rota – >|<br><br>Ilhas|Publisher<br><br>Skype for Business|<br>Somente Equipes|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Teams|Skype for Business|Teams|
|||||

### <a name="federated-presence"></a>Presença federada

A presença federada baseia-se na acessibilidade federada mostrada na tabela 2.  A tabela a seguir descreve a presença do Publicador que será vista por um Observador, dependendo do modo do Publicador e do cliente do Observador (para um novo thread). Na prática, o cliente do Observador não faz diferença na federação neste estágio.

#### <a name="table-4-federated-presence-new-thread"></a>Tabela 4: presença federada (novo thread)

<br>

|Observador<br><br>Cliente|<br><br>Rota – >|<br><br>Ilhas|Publisher<br><br>Skype for Business|<br><br>Somente Equipes|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Skype for Business|Skype for Business|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>Presença em threads pré-existentes

Para alinhar a presença e a acessibilidade em threads pré-existentes, a presença do destino exposta nesse thread precisa ser alinhada com o roteamento do thread, supondo que o roteamento seja possível.  Em particular, se um destinatário com o qual você tinha um thread de conversa de interoperabilidade persistente foi atualizado para o Teams, esse thread não refletirá mais a presença precisa e não será mais roteável. Você deve iniciar um novo thread.

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>Federação e interoperabilidade com Office 365 operado pela 21Vianet

A federação e a interoperabilidade entre Office 365 multilocatário e Office 365 operados pela 21Vianet têm suporte quando os usuários de Office 365 multilocatário estão no modo Somente Teams. Nesse cenário, os usuários do Skype for Business Online no Office 365 operados pela 21Vianet poderão se comunicar somente com usuários do Teams em Office 365 multilocatário por meio de chats e chamadas. A tabela a seguir mostra os cenários com suporte nesta configuração:
 
|Cenário|Origem|Destinatário|Com suporte?|
|---|---|---|---|
|Presença|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sim<br>Sim|
|Bate-papo|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sim (somente 1:1)<br>Sim(somente 1:1)|
|Chamadas de áudio|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sim (somente 1:1)<br>Sim (somente 1:1)|
|Chamadas de vídeo|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sim (somente 1:1)<br>Sim (somente 1:1)|
|Compartilhamento de Tela|Teams <br> Skype for Business <br> | Skype for Business <br> Teams |Sim (por meio de uma reunião promovida do Teams)<br>Sim (por meio de uma reunião Skype for Business promovida)|
|||||


## <a name="related-links"></a>Links relacionados
[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

[Vídeo: Gerenciar coexistência e interoperabilidade entre o Skype for Business e o Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
