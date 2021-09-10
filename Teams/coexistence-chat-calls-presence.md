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
ms.openlocfilehash: 5383ff8c68b8950b449b5159a530a1439156a945
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2021
ms.locfileid: "58972919"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistência com o Skype for Business

A coexistência e a interoperabilidade entre clientes Skype for Business e Teams e usuários são definidas pelos modos TeamsUpgrade, descritos em Diretrizes de migração e [interoperabilidade](migration-interop-guidance-for-teams-with-skype.md)para organizações que usam Teams em conjunto com o Skype for Business .

Qualquer usuário determinado sempre receberá um modo TeamsUpgrade, por padrão ou explicitamente pelo administrador. O valor padrão é *Ilhas*. Os usuários atualizados para Teams têm o modo *teamsOnly*. *SfBOnly*, *SfBWithTeamsCollab* e *SfBWithTeamsCollabAndMeetings* também são modos possíveis.

## <a name="routing-parameters"></a>Parâmetros de roteamento

O modo TeamsUpgrade do destinatário é fundamental para determinar o comportamento de chats, chamadas e presença, tanto em um locatário quanto em locatários federados.

Se o remetente estiver usando Teams, a decisão de roteamento será tomada ao criar um novo thread de conversa. Threads de conversa existentes no Teams sempre retêm o método de roteamento determinado quando o thread foi criado: Teams suporta threads persistentes.

 Os métodos de roteamento de thread são:

- *nativo* para um Teams para Teams conversa no locatário
- *interop* para um Teams para Skype conversa comercial no locatário
- *federado* para uma conversa federada entre locatários

Os parâmetros que determinam o método de roteamento de thread são:

- O modo TeamsUpgrade do destinatário
- O cliente usado pelo remetente
- Se a conversa é nova ou parte de um thread existente
- Se a conversa está no locatário ou federada
- Se a conversa é possível
  - *A interoperabilidade no* locatário exige que o locatário seja puro online ou Skype for Business híbrido. Locatários locais puramente não podem ter interoperabilidade no locatário.
  - *A federação entre locatários* sempre requer Skype for Business configuração de federação adequada, bem como a configuração Teams federação adequada de ambos os locatários. Skype for Business híbrido não é necessário para nenhum dos locatários.
  - Se a Skype for Business do originador estiver no local, esse usuário não poderá usar o cliente Teams para interoperabilidade no locatário ou para federação. Esse usuário só pode usar o cliente Skype for Business para interoperabilidade e federação.
  - Teams para Teams comunicação é sempre possível no locatário.

> [!NOTE]
> Se o receptor e o remetente estão no modo de atualização do TeamsOnly, a conversa será uma experiência de chat nativa que inclui todos os recursos avançados de mensagens e chamada. Para saber mais, leia [Experiência de chat nativa para usuários externos (federados) no Teams](native-chat-for-external-users.md). Se um dos participantes da conversa não estiver no modo de atualização do TeamsOnly, a conversa permanecerá uma experiência de interop com mensagens somente texto.

## <a name="chat-and-call-routing"></a>Roteamento de chat e chamadas

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Roteamento no locatário para novos chats ou chamadas

As tabelas abaixo capturam o roteamento de chat e chamadas no locatário e são válidas para novas chamadas ou chats que não são iniciados a partir de um thread pré-existente. Ele descreve qual cliente receberá uma nova chamada ou chat, se originado por um usuário à esquerda, para um usuário destinatário no locatário à direita.

Mensagens enviadas para os usuários do TeamsOnly sempre serão roteadas para Teams. As mensagens enviadas aos usuários do SfB sempre serão roteadas para Skype for Business, se a \* conversa for possível conforme descrito acima. As mensagens enviadas aos usuários das Ilhas sempre serão roteadas para o mesmo cliente do qual foram enviadas.

As tabelas a seguir mostram qual cliente em um determinado modo receberá uma chamada do originador (três colunas mais à esquerda), dependendo do modo do originador, do cliente escolhido e de onde seu cliente Skype for Business está em casa (no local ou online).

Nas tabelas a seguir:

- **SfB \** _ representa qualquer um dos seguintes modos: _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.
- *O texto itálico realça* uma conversa de interop.
- **Not Possible** representa uma situação na qual o chat ou chamada não é possível. O originador deve usar Skype for Business em vez disso nesses casos. Este é um dos motivos pelos quais a orientação prescritiva da Microsoft para clientes on-prem/hybrid é usar um modo diferente de Ilhas (normalmente SfBWithTeamsCollab) como o ponto de partida de sua jornada de atualização para Teams.

#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>Tabela 1a: novo chat no locatário ou roteamento de chamadas para um destinatário de modo de ilhas

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>SfB &nbsp; homed|<br><br>Route->|Destinatário<br><br>Ilhas|
|---|---|---|:---:|---|
|Ilhas|Microsoft Teams <br> Skype for Business <br> Microsoft Teams <br> Skype for Business|Online <br> Online<br> On-prem<br>On-prem|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|Microsoft Teams <br> Skype for Business <br> Microsoft Teams <br> Skype for Business|
|SfB\*|Skype for Business <br>Skype for Business|Online <br> On-prem|&boxv;<br>&boxv;|Skype for Business <br> Skype for Business|
|TeamsOnly|Teams|Online|&boxv;|Teams|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-a-recipient-in-an-sfb-mode"></a>Tabela 1b: novo chat no locatário ou roteamento de chamadas para um destinatário em um modo \* SfB

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>SfB &nbsp; homed|<br><br>Route->|Destinatário<br><br>SfB\*|
|---|---|---|:---:|---|
|Ilhas|Microsoft Teams <br> Skype for Business <br> Microsoft Teams <br> Skype for Business|Online <br> Online <br> On-prem <br> On-prem|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|*Skype for Business* <br> Skype for Business <br> **Não é possível** <br> Skype for Business|
|SfB\*|Skype for Business <br> Skype for Business|Online <br> On-prem|&boxv;<br>&boxv;|Skype for Business <br> Skype for Business|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabela 1c: novo chat no locatário ou roteamento de chamadas para um destinatário do modo TeamsOnly

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>SfB &nbsp; homed|<br><br>Route->|Destinatário<br><br>TeamsOnly|
|---|---|---|:---:|---|
|Ilhas|Microsoft Teams <br> Skype for Business <br> Microsoft Teams <br> Skype for Business|Online <br> Online <br> On-prem <br> On-prem|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|Teams <br> *Microsoft Teams* <br> Microsoft Teams <br> *Microsoft Teams*|
|SfB\*|Skype for Business <br> Skype for Business|Online <br> On-prem|&boxv;<br>&boxv;|*Microsoft Teams* <br> *Microsoft Teams*|
|TeamsOnly|Teams|Online|&boxv;|Teams|
||||||

### <a name="federated-routing-for-new-chats-or-calls"></a>Roteamento federado para novos chats ou chamadas

As tabelas abaixo capturam o roteamento de chamadas e chats federados e são válidas para novas chamadas ou chats. Eles descrevem qual cliente receberá uma nova chamada ou chat, se originado por um usuário à esquerda, para um usuário de destino federado à direita.

Em resumo, se a conversa for possível conforme descrito acima, as mensagens enviadas aos usuários do TeamsOnly sempre chegarão Teams; as mensagens enviadas aos usuários do SfB sempre chegarão em Skype for Business; as mensagens enviadas aos usuários das Ilhas sempre chegarão Skype for Business independentemente do cliente do qual foram \* enviados. O roteamento para chats e chamadas federados difere do roteamento no locatário, pois os usuários das Ilhas sempre receberão uma comunicação federada no Skype for Business.

Isso acontece porque não podemos supor que um parceiro federado Skype for Business já usa Teams se estiver no modo Ilhas. Ilhas é o modo padrão, no entanto, não podemos supor que todos os usuários de Ilhas executem Teams. Ao rotear para Skype for Business, garantimos que nenhuma comunicação com um usuário das Ilhas falhe. Se roteámos para Teams, essa comunicação poderá ser perdida se o destino não usar Teams. O roteamento Skype for Business garante que a mensagem sempre será recebida.

> [!NOTE]
> A implementação atual da federação Teams baseia-se na federação Skype for Business, portanto, aproveita a infraestrutura de interoperabilidade (que exige que o locatário do originador seja pura online ou Skype for Business híbrido) e fornece um conjunto reduzido de recursos em comparação com um thread nativo. Esperamos fornecer recursos nativos Teams Teams federação no futuro, em que ponto o thread será nativo e fornecerá recursos completos.

As tabelas abaixo descrevem qual cliente receberá uma chamada do originador (três colunas mais à esquerda), dependendo do modo do originador, do cliente escolhido e de onde o cliente Skype for Business está em casa (local ou online).

#### <a name="table-2a-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>Tabela 2a: novo chat federado ou roteamento de chamadas para um destinatário das Ilhas

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>SfB homed|<br><br>Route->|Destinatário<br><br>Ilhas|
|---|---|---|:---:|---|
|Ilhas|Microsoft Teams <br> Skype for Business <br> Microsoft Teams <br> Skype for Business|Online <br> Online <br> On-prem <br> On-prem|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|*Skype for Business* <br> Skype for Business <br> **Não é possível** <br> Skype for Business|
|SfB\*|Skype for Business <br> Skype for Business|Online <br> On-prem|&boxv;<br>&boxv;|Skype for Business <br> Skype for Business|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|||||

#### <a name="table-2b-federated-new-chat-or-call-routing-to-a-recipient-in-an-sfb-mode"></a>Tabela 2b: novo chat federado ou roteamento de chamadas para um destinatário em um modo \* SfB

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>SfB homed|<br><br>Route->|Destinatário<br><br> SfB\*|
|---|---|---|:---:|---|
|Ilhas|Microsoft Teams <br> Skype for Business <br> Microsoft Teams <br> Skype for Business|Online <br> Online <br> On-prem <br> On-prem|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|*Skype for Business* <br> Skype for Business <br> **Não é possível** <br> Skype for Business|
|SfB\*|Skype for Business <br> Skype for Business|Online <br> On-prem|&boxv;<br>&boxv;|Skype for Business <br> Skype for Business|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
||||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>Tabela 2c: novo chat federado ou roteamento de chamadas para um destinatário do modo TeamsOnly

<br>

|<br><br>Modo|Originador<br><br>Cliente|<br><br>SfB homed|<br><br>Route->|Destinatário<br><br>TeamsOnly|
|---|---|---|:---:|---|
|Ilhas|Microsoft Teams <br> Skype for Business <br> Microsoft Teams <br> Skype for Business|Online <br> Online <br> On-prem <br> On-prem|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|Teams <br> *Microsoft Teams* <br> **Não é possível** <br> *Microsoft Teams*|
|SfB\*|Skype for Business <br> Skype for Business|Online <br> On-prem|&boxv;<br>&boxv;|*Microsoft Teams* <br> *Microsoft Teams*|
|TeamsOnly|Teams|Online|&boxv;|Teams|
||||||

## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats e chamadas de threads pré-existentes

### <a name="from-teams"></a>De Teams

Chamadas ou chats iniciados a partir de um thread persistente pré-existente no Teams serão roteados da mesma maneira que esse thread, se essa opção de roteamento ainda estiver disponível.

Se o thread persistente pré-existente no Teams for um thread nativo (ou seja, roteado para Teams), mensagens de chat adicionais e chamadas desse thread serão Teams. Se foi um thread de interop (ou seja, roteado para Skype for Business), mensagens de chat e chamadas adicionais serão enviadas para Skype for Business (novamente supondo que as opções de roteamento estão disponíveis).

> [!NOTE]
> É possível que threads pré-existentes no Teams não sejam mais tables, como quando o thread era um thread de interop para um usuário que agora é atualizado para Teams. Como ele foi criado como um thread de interop, o thread seria roteado para Skype for Business, mas esse usuário não pode mais usar Skype for Business para chat e chamada. Nesse caso, o thread será desabilitado e não permitirá mais comunicação.

### <a name="from-skype-for-business"></a>De Skype for Business

Skype for Business threads não persistem além do tempo de sessão SIP de 10 minutos. Chats e chamadas de um thread existente no Skype for Business antes da expiração da sessão SIP serão roteados da mesma maneira que o thread. Chamadas e chats de um thread existente no Skype for Business além do tempo de sessão SIP serão roteados para o Skype for Business da parte remota, independentemente de qual cliente o thread original veio do lado da outra parte.

### <a name="availability"></a>Disponibilidade

Os comportamentos no locatário e federado descritos acima estão disponíveis, com as seguintes limitações:

- Participantes externos cujos locatários residem em uma implantação ou geografia golocal diferente não verão chat de mensagens IM em uma reunião "federada"
- A federação e a interopção entre os Office 365 e Office 365 operados pela 21Vianet são suportados em cenários limitados.


## <a name="presence"></a>Presença

Quando você tem uma situação em que alguns de seus usuários estão usando o cliente Teams e outros ainda estão usando o cliente Skype for Business, você pode ter vários usuários que estão usando ambos os clientes. Você ainda deseja que os estados de presença sejam compartilhados com todos os usuários sem considerar o cliente que um usuário individual tem. Quando isso é compartilhado na organização, os usuários podem determinar melhor se é apropriado iniciar um chat ou fazer uma chamada.

Por exemplo, se um chat ou chamada de um originador deve chegar no cliente de Skype for Business do destino, então é a presença do cliente Skype for Business que deve ser mostrada ao originador. Se ele deve chegar no cliente Teams do destino, então é a presença do cliente Teams que deve ser mostrada.

Para saber qual comportamento esperar, você precisará entender que a Presença é compartilhada com base no modo de coexistência de um usuário:

- Se um usuário estiver no modo TeamsOnly, qualquer outro usuário (Teams ou Skype for Business) verá que a presença Teams usuário do TeamsOnly
- Se um usuário estiver em qualquer um dos modos \* SfB (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), qualquer outro usuário (seja no Teams ou no Skype for Business) verá a presença Skype for Business do usuário \* SfB
- Se um usuário estiver no modo Ilhas (ou Herdado), a presença no Teams e a presença no Skype for Business são independentes (os valores não precisam corresponder) e outros usuários verão uma ou outra presença do usuário das Ilhas, dependendo se eles estão no mesmo locatário ou em um locatário federado e qual cliente eles usam
  - A partir Teams, qualquer outro usuário dentro do mesmo locatário verá a presença Teams usuário das Ilhas; isso é alinhado com a tabela de roteamento no locatário acima
  - A partir Teams, qualquer outro usuário em um locatário federado verá a presença Skype for Business usuário das Ilhas; isso é alinhado com a tabela de roteamento federada acima
  - A partir Skype for Business, qualquer outro usuário verá a presença Skype for Business do usuário das Ilhas (in-tenant e federado); isso é alinhado com as tabelas de roteamento acima

### <a name="in-tenant-presence"></a>Presença no locatário

Mensagens enviadas para os usuários do TeamsOnly sempre chegarão Teams. As mensagens enviadas aos usuários do SfB sempre chegarão Skype for Business, se a \* conversa for possível, conforme descrito acima. As mensagens enviadas aos usuários das Ilhas sempre chegarão no cliente de onde foram originadas.

A tabela descreve Publisher presença do Publisher que será vista por um Watcher, dependendo do modo do Publisher e do cliente do Watcher (para um novo thread).

#### <a name="table-3-in-tenant-presence-new-thread"></a>Tabela 3: presença no locatário (novo thread)

<br>

|Watcher<br><br>Cliente|<br><br>Route->|<br><br>Ilhas|Publisher<br><br>SfB\*|<br>Teams Somente|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Microsoft Teams|Skype for Business|Teams|
|||||

### <a name="federated-presence"></a>Presença federada

A presença federada baseia-se na capacidade de acesso federada mostrada na tabela 2.

A tabela a seguir descreve a presença do Publisher que será vista por um Watcher, dependendo do modo do Publisher e do cliente do Watcher (para um novo thread). Na prática, o cliente do Watcher não faz diferença na federação neste estágio.

#### <a name="table-4-federated-presence-new-thread"></a>Tabela 4: presença federada (novo thread)

<br>

|Watcher<br><br>Cliente|<br><br>Route->|<br><br>Ilhas|Publisher<br><br>SfB\*|<br><br>Teams Somente|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Microsoft Teams|&boxv;|Skype for Business|Skype for Business|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>Presença em threads pré-existentes

Para alinhar a presença e a capacidade de alcance em threads pré-existentes, a presença do destino exposta nesse thread precisa ser alinhada com o roteamento do thread, supondo que o roteamento seja possível.

Em particular, se um destinatário com o que você tinha anteriormente um thread de conversa de interop persistente foi atualizado para Teams, esse thread não refletirá mais a presença precisa e não será mais routable. Você deve iniciar um novo thread.

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>Federação e interopção com Office 365 operado pela 21Vianet

A federação e a interopção entre os Office 365 e Office 365 operados pela 21Vianet são suportados quando os usuários de vários locatários Office 365 estão no modo Somente Teams. Nesse cenário, os usuários Skype for Business Online no Office 365 operados pela 21Vianet poderão se comunicar com o Teams Somente usuários em vários Office 365 por meio de chats e chamadas. A tabela a seguir mostra os cenários com suporte nesta configuração:
 
|Cenário|Origem|Destinatário|Com suporte?|
|---|---|---|---|
|Presença|Microsoft Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sim<br>Sim|
|Bate-papo|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sim (somente 1:1)<br>Sim(somente 1:1)|
|Chamadas de áudio|Microsoft Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sim (somente 1:1)<br>Sim (somente 1:1)|
|Chamadas de vídeo|Microsoft Teams <br> Skype for Business <br> | Skype for Business <br> Teams|Sim (somente 1:1)<br>Sim (somente 1:1)|
|Compartilhamento de tela|Microsoft Teams <br> Skype for Business <br> | Skype for Business <br> Teams |Sim (por meio de uma reunião Teams promoção)<br>Sim (por meio de uma reunião SfB promovida)|
|||||


## <a name="related-links"></a>Links relacionados
[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

[Vídeo: Gerenciar coexistência e interoperabilidade entre SfB e Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
