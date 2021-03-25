---
title: Coexistência com o Skype for Business
author: serdarsoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: Comportamento de coexistência entre o Teams & Skype for Business, incluindo parâmetros de roteamento, roteamento de chamadas de chat &, chats & chamadas de threads pré-existentes, & presença.
ms.openlocfilehash: 603356df5e6f5006ea67f6a84141acf1347c1235
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122335"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistência com o Skype for Business

A coexistência e a interoperabilidade entre clientes e usuários do Skype for Business e do Teams são definidas pelos modos TeamsUpgrade, descritos em Diretrizes de migração e interoperabilidade para organizações que usam o Teams em conjunto com [o Skype for Business.](migration-interop-guidance-for-teams-with-skype.md)

Qualquer usuário determinado sempre receberá um modo TeamsUpgrade, por padrão ou explicitamente pelo administrador. O valor padrão é *Ilhas*. Os usuários atualizados para o Teams têm o modo *teamsOnly*. *SfBOnly*, *SfBWithTeamsCollab* e *SfBWithTeamsCollabAndMeetings* também são modos possíveis.


## <a name="routing-parameters"></a>Parâmetros de roteamento

O modo TeamsUpgrade do destinatário é fundamental para determinar o comportamento de chats, chamadas e presença, tanto em um locatário quanto em locatários federados.

Se o remetente estiver usando o Teams, a decisão de roteamento será tomada ao criar um novo thread de conversa. Threads de conversa existentes no Teams sempre retêm o método de roteamento determinado quando o thread foi criado: o Teams dá suporte a threads persistentes.

 Os métodos de roteamento de thread são:  

- *nativo* para uma conversa do Teams para o Teams no locatário
- *interop* para uma conversa do Teams para Skype for Business no locatário
- *federado* para uma conversa federada entre locatários

Os parâmetros que determinam o método de roteamento de thread são:

- O modo TeamsUpgrade do destinatário
- O cliente usado pelo remetente
- Se a conversa é nova ou parte de um thread existente
- Se a conversa está no locatário ou federada
- Se a conversa é possível
    - *A interoperabilidade no* locatário exige que o locatário seja puro online ou híbrido do Skype for Business. Locatários locais puramente não podem ter interoperabilidade no locatário.
    - *A federação entre locatários* sempre exige a configuração de federação adequada do Skype for Business, bem como a configuração de federação adequada do Teams de ambos os locatários. O Skype for Business híbrido não é necessário para nenhum dos locatários.
    - Se a conta do Skype for Business do originador estiver no local, esse usuário não poderá usar o cliente do Teams para interoperabilidade no locatário ou para federação. Esse usuário só pode usar o cliente Skype for Business para interoperabilidade e federação.
    - A comunicação do Teams com o Teams é sempre possível no locatário.

> [!NOTE]
> Se o receptor e o remetente estão no modo de atualização do TeamsOnly, a conversa será uma experiência de chat nativa que inclui todos os recursos avançados de mensagens e chamada. Para saber mais, leia [Experiência de chat nativa para usuários externos (federados) no Teams](native-chat-for-external-users.md). Se um dos participantes da conversa não estiver no modo de atualização do TeamsOnly, a conversa permanecerá uma experiência de interop com mensagens somente texto.

## <a name="chat-and-call-routing"></a>Roteamento de chat e chamadas

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Roteamento no locatário para novos chats ou chamadas 

As tabelas abaixo capturam o roteamento de chat e chamadas no locatário e são válidas para novas chamadas ou chats que não são iniciados a partir de um thread pré-existente. Ele descreve qual cliente receberá uma nova chamada ou chat, se originado por um usuário à esquerda, para um usuário destinatário no locatário à direita.

Mensagens enviadas para os usuários do TeamsOnly sempre serão roteadas para o Teams. As mensagens enviadas aos usuários do SfB sempre serão roteadas para o Skype for Business, se a \* conversa for possível conforme descrito acima. As mensagens enviadas aos usuários das Ilhas sempre serão roteadas para o mesmo cliente do qual foram enviadas.

As tabelas a seguir mostram qual cliente em um determinado modo receberá uma chamada do originador (três colunas mais à esquerda), dependendo do modo do originador, do cliente escolhido e de onde o cliente skype for Business está instalado (no local ou online).

Nas tabelas a seguir: 
- **SfB \** _ representa qualquer um dos seguintes modos: _SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

- *O texto itálico realça* uma conversa de interop.

- **Not Possible** representa uma situação na qual o chat ou chamada não é possível. O originador deve usar o Skype for Business nesses casos. Este é um dos motivos pelos quais a orientação prescritiva da Microsoft para clientes on-prem/hybrid é usar um modo diferente de Ilhas (normalmente SfBWithTeamsCollab) como o ponto de partida de sua jornada de atualização para o Teams.

**Tabela 1a: novo chat no locatário ou roteamento de chamadas para um destinatário de modo de ilhas**

| <br/><br/> Modo | Originador <br/><br/> Cliente | <br/><br/> SfB &nbsp; homed |<br/><br/>Route->| Destinatário <br/><br/> Ilhas  |
|--- |--- |--- |--- |--- |
| Ilhas | Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business| Online<br/> Online<br/> On-prem<br/>On-prem| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business|
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> On-prem<br/> |&boxv;<br/>&boxv;|Skype for Business<br/>Skype for Business<br/>|
|TeamsOnly |Teams| Online<br/>|&boxv;<br/>|Teams|
| | | | | |

**Tabela 1b: novo chat no locatário ou roteamento de chamadas para um destinatário em um modo \* SfB**

| <br/><br/> Modo   | Originador <br/><br/> Cliente | <br/><br/> SfB &nbsp; homed |<br/><br/>Route-> |   Destinatário <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| Ilhas |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business  |Online<br/> Online<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business<br/> **Não é possível** <br/>Skype for Business<br/> |
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> On-prem<br/> |&boxv;<br/>&boxv; |  Skype for Business<br/>Skype for Business<br/> |
|TeamsOnly |Teams| Online<br/>|&boxv;<br/> |  *Skype for Business* <br/>| 
| | | | | |

**Tabela 1c: novo chat no locatário ou roteamento de chamadas para um destinatário do modo TeamsOnly**

| <br/><br/> Modo   | Originador <br/><br/> Cliente | <br/><br/> SfB &nbsp; homed |<br/><br/>Route->|   Destinatário <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Ilhas   |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business<br/>|Online<br/> Online<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Microsoft Teams* <br/>Microsoft Teams <br/>*Microsoft Teams*  |
|SfB\*  | Skype for Business<br/>Skype for Business<br/> | Online<br/> On-prem<br/> | &boxv;<br/>&boxv; | *Microsoft Teams*  <br/>*Microsoft Teams*   |
|TeamsOnly  | Teams | Online |  &boxv; |Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>Roteamento federado para novos chats ou chamadas
  
As tabelas abaixo capturam o roteamento de chamadas e chats federados e são válidas para novas chamadas ou chats. Eles descrevem qual cliente receberá uma nova chamada ou chat, se originado por um usuário à esquerda, para um usuário de destino federado à direita.

Em resumo, se a conversa for possível conforme descrito acima, as mensagens enviadas aos usuários do TeamsOnly sempre chegarão no Teams; as mensagens enviadas aos usuários do SfB sempre chegarão no Skype for Business; as mensagens enviadas aos usuários das Ilhas sempre chegarão no Skype for Business, independentemente do cliente do qual foram \* enviados. O roteamento para chats e chamadas federados difere do roteamento no locatário, pois os usuários de Ilhas sempre receberão uma comunicação federada no Skype for Business.

Isso acontece porque não podemos supor que um parceiro federado do Skype for Business já use o Teams se estiver no modo Ilhas. Ilhas é o modo padrão, no entanto, não podemos supor que todos os usuários de Ilhas executem o Teams. Ao rotear para o Skype for Business, garantimos que nenhuma comunicação com um usuário das Ilhas falhe. Se roteámos para o Teams, essa comunicação poderia ser perdida se o destino não tivesse usado o Teams. O roteamento para o Skype for Business garante que a mensagem sempre será recebida.  

> [!NOTE]
> A implementação atual da federação do Teams baseia-se na federação do Skype for Business, portanto, aproveita a infraestrutura de interoperabilidade (que exige que o locatário do originador seja puro online ou híbrido do Skype for Business) e fornece um conjunto reduzido de recursos em comparação com um thread nativo. Esperamos fornecer federação nativa do Teams para o Teams no futuro, em que ponto o thread será nativo e fornecerá recursos completos.

As tabelas abaixo descrevem qual cliente receberá uma chamada do originador (três colunas mais à esquerda), dependendo do modo do originador, do cliente escolhido e de onde o cliente skype for Business está instalado (no local ou online).

**Tabela 2a: novo chat federado ou roteamento de chamadas para um destinatário das Ilhas**

| <br/><br/>Modo   | Originador<br/><br/> Cliente| <br/><br/>SfB homed|<br/><br/>Route-> | Destinatário<br/><br/> Ilhas |
|--- |--- |--- |--- |--- |
| Ilhas |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business  |Online<br/> Online<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Não é possível**   <br/> Skype for Business |
| SfB\* |Skype for Business <br/>Skype for Business |Online<br/> On-prem<br/> | &boxv;<br/>&boxv;|Skype for Business <br/>Skype for Business |
| TeamsOnly |Teams |Online| &boxv;|*Skype for Business* |
|  | | | | 

**Tabela 2b: novo chat federado ou roteamento de chamadas para um destinatário em um modo \* SfB**

| <br/><br/>Modo   | Originador<br/><br/> Cliente| <br/><br/>SfB homed|<br/><br/>Route->|  Destinatário<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| Ilhas |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> On-prem<br/> On-prem<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Não é possível** <br/>Skype for Business <br/> |  
| SfB\* |Skype for Business <br/>Skype for Business  |Online<br/> On-prem<br/>  |&boxv;<br/>&boxv; | Skype for Business <br/>Skype for Business  |
| TeamsOnly | Teams|Online |&boxv; |*Skype for Business*  |
|  | | | | |

**Tabela 2c: novo chat federado ou roteamento de chamadas para um destinatário do modo TeamsOnly**

| <br/><br/>Modo | Originador<br/><br/> Cliente| <br/><br/>SfB homed|<br/><br/>Route->|  Destinatário<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Ilhas  |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> On-prem<br/> On-prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Microsoft Teams* <br/>**Não é possível** <br/>*Microsoft Teams* |
| SfB\* |Skype for Business <br/>Skype for Business  | Online<br/> On-prem| &boxv;<br/>&boxv;|*Microsoft Teams* <br/>*Microsoft Teams*   |
| TeamsOnly |Teams |Online |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats e chamadas de threads pré-existentes

### <a name="from-teams"></a>Do Teams

Chamadas ou chats iniciados a partir de um thread persistente pré-existente no Teams serão roteados da mesma maneira que esse thread, se essa opção de roteamento ainda estiver disponível.

Se o thread persistente pré-existente no Teams fosse um thread nativo (ou seja, roteado para o Teams), mensagens de chat adicionais e chamadas desse thread irão para o Teams. Se foi um thread de interop (ou seja, roteado para o Skype for Business), mensagens de chat adicionais e chamadas serão enviadas para o Skype for Business (novamente supondo que as opções de roteamento estão disponíveis).

> [!NOTE]
> É possível que threads pré-existentes no Teams não sejam mais tables, como quando o thread era um thread de interop para um usuário que agora é atualizado para o Teams. Como ele foi criado como um thread de interop, o thread seria roteada para o Skype for Business, mas esse usuário não pode mais usar o Skype for Business para chat e chamadas. Nesse caso, o thread será desabilitado e não permitirá mais comunicação.

### <a name="from-skype-for-business"></a>Do Skype for Business

Os threads do Skype for Business não persistem além dos 10 min. Tempo de sessão SIP. Chats e chamadas de um thread existente no Skype for Business antes da expiração da sessão SIP serão roteados da mesma maneira que o thread. Chamadas e chats de um thread existente no Skype for Business além do tempo de tempo de sessão SIP serão roteados para o Skype for Business da parte remota, independentemente de qual cliente o thread original veio do lado da outra parte.

### <a name="availability"></a>Disponibilidade

Os comportamentos no locatário e federado descritos acima estão disponíveis, com as seguintes limitações:

- Participantes externos cujos locatários residem em uma implantação ou geografia golocal diferente não verão chat de mensagens IM em uma reunião "federada"
- Não há suporte para federação e interopção entre Multitenant O365 e Nuvens Soberanas

## <a name="presence"></a>Presença

Quando você tem uma situação em que alguns de seus usuários estão usando o cliente do Teams e outros ainda estão usando o cliente Skype for Business, você pode ter vários usuários que estão usando ambos os clientes. Você ainda deseja que os estados de presença sejam compartilhados com todos os usuários sem considerar o cliente que um usuário individual tem. Quando isso é compartilhado na organização, os usuários podem determinar melhor se é apropriado iniciar um chat ou fazer uma chamada.

Por exemplo, se o chat ou a chamada de um originador deve chegar no cliente skype for Business do destino, então é a presença do cliente do Skype for Business que deve ser mostrada ao originador. Se ele deve chegar no cliente do Teams do destino, então é a presença do cliente do Teams que deve ser mostrada.

Para saber qual comportamento esperar, você precisará entender que a Presença é compartilhada com base no modo de coexistência de um usuário:

* Se um usuário estiver no modo TeamsOnly, qualquer outro usuário (seja no Teams ou no Skype for Business) verá que a presença do TeamsOnly do usuário do TeamsOnly
* Se um usuário estiver em qualquer um dos modos \* SfB (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), qualquer outro usuário (seja no Teams ou no Skype for Business) verá que a presença do usuário SfB no \* Skype for Business
* Se um usuário estiver no modo Ilhas (ou Herdado), a presença no Teams e a presença no Skype for Business são independentes (os valores não precisam corresponder) e outros usuários verão uma ou outra presença do usuário das Ilhas, dependendo se eles estão no mesmo locatário ou em um locatário federado e qual cliente eles usam
    * No Teams, qualquer outro usuário dentro do mesmo locatário verá a presença do Teams do usuário das Ilhas; isso é alinhado com a tabela de roteamento no locatário acima
    * No Teams, qualquer outro usuário em um locatário federado verá a presença do usuário do Skype for Business das Ilhas; isso é alinhado com a tabela de roteamento federada acima
    * No Skype for Business, qualquer outro usuário verá a presença do skype for Business do usuário das ilhas (in-tenant e federado); isso é alinhado com as tabelas de roteamento acima


### <a name="in-tenant-presence"></a>Presença no locatário

Mensagens enviadas aos usuários do TeamsOnly sempre chegarão no Teams. As mensagens enviadas aos usuários do SfB sempre chegarão no Skype for Business, se a conversa for \* possível conforme descrito acima. As mensagens enviadas aos usuários das Ilhas sempre chegarão no cliente de onde foram originadas.

A tabela descreve a presença do Publisher que será vista por um Watcher, dependendo do modo do Publisher e do cliente do Watcher (para um novo thread).

**Tabela 3: presença no locatário (novo thread)**

|Watcher <br/><br/>Cliente|<br/><br/>Route-> |<br/><br/>Ilhas |Publisher <br/><br/>SfB\* |<br/>Somente equipes|
|--- |--- |--- |--- |---|
|Skype for Business |&boxv;|Skype for Business | Skype for Business | Teams|
|Teams |&boxv; |Microsoft Teams |Skype for Business |Teams |
| | | | |

### <a name="federated-presence"></a>Presença federada

A presença federada baseia-se na capacidade de acesso federada mostrada na tabela 2.

A tabela abaixo descreve a presença do Publisher que será vista por um Watcher, dependendo do modo do Publisher e do cliente do Watcher (para um novo thread). Na prática, o cliente do Watcher não faz diferença na federação neste estágio.

**Tabela 4: presença federada (novo thread)**

|Watcher <br/><br/> Cliente |<br/><br/>Route->|<br/><br/> Ilhas  |Publisher <br/><br/> SfB\* |<br/><br/> Somente equipes |
|--- |--- |--- |--- |---|
|Skype for Business |&boxv; |Skype for Business  | Skype for Business  | Teams  |
|Microsoft Teams | &boxv;|Skype for Business |Skype for Business |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>Presença em threads pré-existentes

Para alinhar a presença e a capacidade de alcance em threads pré-existentes, a presença do destino exposta nesse thread precisa ser alinhada com o roteamento do thread, supondo que o roteamento seja possível.

Em particular, se um destinatário com o que você já teve um thread de conversa de interop persistente foi atualizado para o Teams, esse thread não refletirá mais a presença precisa e não será mais stável. Você deve iniciar um novo thread.

## <a name="related-links"></a>Links relacionados
[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)

[Vídeo: Gerenciar coexistência e interoperabilidade entre o SfB e o Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)