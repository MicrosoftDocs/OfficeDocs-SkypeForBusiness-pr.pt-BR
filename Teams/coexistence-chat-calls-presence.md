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
ms.openlocfilehash: 9dd2baa717466b0f414168356256b6d78ce33f6a
ms.sourcegitcommit: e5e60079cf9d62627de6b26dd4badd353bcc190c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48661343"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistência com o Skype for Business

A coexistência e a interoperabilidade entre clientes e usuários do Skype for Business e do Teams é definida pelos modos teamsUpgrade, descritos na orientação de migração e interoperabilidade para organizações que usam o Teams em conjunto com o [Skype for Business.](migration-interop-guidance-for-teams-with-skype.md)

Qualquer usuário determinado sempre receberá um modo TeamsUpgrade, por padrão ou explicitamente pelo administrador. O valor padrão é *Ilhas.* Os usuários atualizados para o Teams têm o modo *do TeamsOnly.* *SfBOnly,* *SfBWithTeamsCollab* e *SfBWithTeamsCollabAndMeetings* também são modos possíveis.


## <a name="routing-parameters"></a>Parâmetros de roteamento

O modo TeamsUpgrade do destinatário é fundamental para determinar o comportamento de chats, chamadas e presença, dentro de um locatário e entre locatários federados.

Se o remetente estiver usando o Teams, a decisão de roteamento será tomada ao criar um novo thread de conversa. Os threads de conversa existentes no Teams sempre mantêm o método de roteamento determinado quando o thread foi criado: o Teams dá suporte a threads persistentes.

 Os métodos de roteamento de thread são:  

- *nativo* para uma conversa do Teams com o Teams no locatário
- *interop* para uma conversa do Teams para Skype for Business no locatário
- *federado* para uma conversa federada entre locatários

Os parâmetros que determinam o método de roteamento de thread são:

- O modo TeamsUpgrade do destinatário
- O cliente usado pelo remetente
- Se a conversa é nova ou parte de um thread existente
- Se a conversa está no locatário ou federada
- Se a conversa é possível
    - *A interoperabilidade no* locatário exige que o locatário seja puro online ou híbrido do Skype for Business. Locatários locais não podem ter interoperabilidade no locatário.
    - *A federação entre locatários* sempre requer a configuração adequada de federação do Skype for Business, bem como a configuração adequada de federação do Teams de ambos os locatários. A híbrida do Skype for Business não é necessária para nenhum dos locatários.
    - Se a conta do Skype for Business do originador estiver no local, esse usuário não poderá usar o cliente teams para interoperabilidade no locatário ou para federação. Esse usuário só pode usar o cliente Skype for Business para interoperabilidade e federação.
    - A comunicação entre equipes e equipes é sempre possível no locatário.

> [!NOTE]
> Se o destinatário e o remetente estão no modo de atualização do TeamsOnly, a conversa será uma experiência de chat nativa que inclui todos os recursos avançados de mensagens e chamada. Para saber mais, leia [a experiência de chat nativo para usuários externos (federados) no Teams.](native-chat-for-external-users.md) Se um dos participantes da conversa não estiver no modo de atualização do TeamsOnly, a conversa permanecerá uma experiência interop com mensagens somente de texto.

## <a name="chat-and-call-routing"></a>Roteamento de chat e chamada

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Roteamento no locatário para novos chats ou chamadas 

As tabelas a seguir capturam o roteamento de chats e chamadas no locatário e são válidas para novas chamadas ou chats que não são iniciados a partir de um thread pré-existente. Descreve qual cliente receberá uma nova chamada ou chat, se originado por um usuário à esquerda, para um usuário destinatário no locatário à direita.

As mensagens enviadas aos usuários do TeamsOnly sempre serão roteadas para o Teams. As mensagens enviadas para usuários SfB sempre serão roteadas para o Skype for Business, se a \* conversa for possível, conforme descrito acima. As mensagens enviadas para usuários de Ilhas sempre serão roteadas para o mesmo cliente do qual foram enviadas.

As tabelas a seguir mostram qual cliente em um determinado modo receberá uma chamada do originador (três colunas mais à esquerda), dependendo do modo do originador, do cliente escolhido e de onde o cliente skype for Business está instalado (no local ou online).

Nas tabelas a seguir: 
- **SfB \** _ representa qualquer um dos seguintes modos: _SfBOnly*, *SfBWithTeamsCollab,* *SfBWithTeamsCollabAndMeetings.*

- *O texto em itálico* realça uma conversa interop.

- **Não Possível** representa uma situação em que o chat ou chamada não é possível. O autor deve usar o Skype for Business nesses casos. Esse é um dos motivos pelos quais a orientação prescritiva da Microsoft para clientes híbridos/locais é usar um modo diferente de Ilhas (normalmente SfBWithTeamsCollab) como ponto de partida de sua jornada de atualização para o Teams.

**Tabela 1a: novo chat no locatário ou roteamento de chamada para um destinatário do modo ilhas**

| <br/><br/> Modo | Originador <br/><br/> Cliente | <br/><br/> Homed SfB &nbsp; |<br/><br/>Rota– >| Destinatário <br/><br/> Ilhas  |
|--- |--- |--- |--- |--- |
| Ilhas | Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business| Online<br/> Online<br/> No mesmo caso<br/>No mesmo caso| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business|
|Sfb\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> No mesmo caso<br/> |&boxv;<br/>&boxv;|Skype for Business<br/>Skype for Business<br/>|
|TeamsOnly |Teams| Online<br/>|&boxv;<br/>|Teams|
| | | | | |

**Tabela 1b: novo chat no locatário ou roteamento de chamada para um destinatário no modo \* SfB**

| <br/><br/> Modo   | Originador <br/><br/> Cliente | <br/><br/> Homed SfB &nbsp; |<br/><br/>Rota– > |   Destinatário <br/><br/> Sfb\*   |
|--- |--- |--- |---   |--- |
| Ilhas |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business  |Online<br/> Online<br/> No mesmo caso<br/> No mesmo caso<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business<br/> **Não é Possível** <br/>Skype for Business<br/> |
|Sfb\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> No mesmo caso<br/> |&boxv;<br/>&boxv; |  Skype for Business<br/>Skype for Business<br/> |
|TeamsOnly |Teams| Online<br/>|&boxv;<br/> |  *Skype for Business* <br/>| 
| | | | | |

**Tabela 1c: novo chat no locatário ou roteamento de chamada para um destinatário do modo TeamsOnly**

| <br/><br/> Modo   | Originador <br/><br/> Cliente | <br/><br/> Homed SfB &nbsp; |<br/><br/>Rota– >|   Destinatário <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Ilhas   |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business<br/>|Online<br/> Online<br/> No mesmo caso<br/> No mesmo caso<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Microsoft Teams* <br/>Microsoft Teams <br/>*Microsoft Teams*  |
|Sfb\*  | Skype for Business<br/>Skype for Business<br/> | Online<br/> No mesmo caso<br/> | &boxv;<br/>&boxv; | *Microsoft Teams*  <br/>*Microsoft Teams*   |
|TeamsOnly  | Teams | Online |  &boxv; |Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>Roteamento federado para novos chats ou chamadas
  
As tabelas a seguir capturam o roteamento de chamadas e chats federados e são válidas para novas chamadas ou chats. Eles descrevem qual cliente receberá uma nova chamada ou chat, se originado por um usuário à esquerda, para um usuário de destino federado à direita.

Em resumo, se a conversa for possível conforme descrito acima, as mensagens enviadas aos usuários do TeamsOnly sempre chegarão no Teams; as mensagens enviadas para usuários SfB sempre chegarão ao Skype for Business; as mensagens enviadas para usuários de Ilhas sempre chegarão ao Skype for Business independentemente do cliente do qual foram \* enviados. O roteamento para chats e chamadas federados é diferente do roteamento no locatário, pois os usuários das Ilhas sempre receberão uma comunicação federada no Skype for Business.

Isso acontece porque não podemos supor que um parceiro federado do Skype for Business já use o Teams se ele estiver no modo Ilhas. Ilhas é o modo padrão, mas não podemos supor que todos os usuários de Ilhas executem o Teams. Ao rotear para o Skype for Business, garantimos que nenhuma comunicação com um usuário de Ilhas falhe. Se direcionarmos para o Teams, essa comunicação poderá ser perdida se o destino não usar o Teams. O roteamento para o Skype for Business garante que a mensagem sempre será recebida.  

> [!NOTE]
> A implementação atual da federação do Teams baseia-se na federação do Skype for Business, portanto, ela aproveita a infraestrutura de interoperabilidade (que exige que o locatário do criador seja puro online ou híbrido do Skype for Business) e fornece um conjunto reduzido de recursos em comparação com um thread nativo. Esperamos fornecer equipes nativas para a federação do Teams no futuro, em que ponto o thread será nativo e fornecerá recursos completos.

As tabelas a seguir descrevem qual cliente receberá uma chamada do originador (três colunas mais à esquerda), dependendo do modo do originador, do cliente escolhido e de onde o cliente skype for Business está instalado (no local ou online).

**Tabela 2a: novo chat federado ou roteamento de chamada para um destinatário das Ilhas**

| <br/><br/>Modo   | Originador<br/><br/> Cliente| <br/><br/>Homed SfB|<br/><br/>Rota– > | Destinatário<br/><br/> Ilhas |
|--- |--- |--- |--- |--- |
| Ilhas |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business  |Online<br/> Online<br/> No mesmo caso<br/> No mesmo caso<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Não é Possível**   <br/> Skype for Business |
| Sfb\* |Skype for Business <br/>Skype for Business |Online<br/> No mesmo caso<br/> | &boxv;<br/>&boxv;|Skype for Business <br/>Skype for Business |
| TeamsOnly |Teams |Online| &boxv;|*Skype for Business* |
|  | | | | 

**Tabela 2b: novo chat federado ou roteamento de chamada para um destinatário no modo \* SfB**

| <br/><br/>Modo   | Originador<br/><br/> Cliente| <br/><br/>Homed SfB|<br/><br/>Rota– >|  Destinatário<br/><br/> Sfb\* |  
|--- |--- |--- |--- |--- |
| Ilhas |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> No mesmo caso<br/> No mesmo caso<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Não é Possível** <br/>Skype for Business <br/> |  
| Sfb\* |Skype for Business <br/>Skype for Business  |Online<br/> No mesmo caso<br/>  |&boxv;<br/>&boxv; | Skype for Business <br/>Skype for Business  |
| TeamsOnly | Teams|Online |&boxv; |*Skype for Business*  |
|  | | | | |

**Tabela 2c: novo chat federado ou roteamento de chamada para um destinatário do modo TeamsOnly**

| <br/><br/>Modo | Originador<br/><br/> Cliente| <br/><br/>Homed SfB|<br/><br/>Rota– >|  Destinatário<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Ilhas  |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> No mesmo caso<br/> No mesmo caso<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Microsoft Teams* <br/>**Não é Possível** <br/>*Microsoft Teams* |
| Sfb\* |Skype for Business <br/>Skype for Business  | Online<br/> No mesmo caso| &boxv;<br/>&boxv;|*Microsoft Teams* <br/>*Microsoft Teams*   |
| TeamsOnly |Teams |Online |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats e chamadas de threads pré-existentes

### <a name="from-teams"></a>Do Teams

Chamadas ou chats iniciados a partir de um thread persistente pré-existente no Teams serão roteados da mesma maneira que esse thread, se essa opção de roteamento ainda estiver disponível.

Se o thread persistente pré-existente no Teams era um thread nativo (ou seja, roteado para o Teams), mensagens de chat e chamadas adicionais desse thread irão para o Teams. Se era um thread interop (ou seja, roteado para o Skype for Business), mensagens de chat e chamadas adicionais irão para o Skype for Business (supondo novamente que as opções de roteamento estão disponíveis).

> [!NOTE]
> É possível que threads pré-existentes no Teams não sejam mais rouáveis, como quando o thread era uma conversa interop para um usuário que agora está atualizado para o Teams. Como ele foi criado como um thread interop, o thread seria roteada para o Skype for Business, mas esse usuário não pode mais usar o Skype for Business para chat e chamadas. Nesse caso, o thread será desabilitado e não permitirá mais comunicação.

### <a name="from-skype-for-business"></a>Do Skype for Business

Os threads do Skype for Business não persistem além dos 10 min. Tempo de sessão SIP. Chats e chamadas de um thread existente no Skype for Business antes da expiração da sessão SIP serão roteados da mesma maneira que o thread. Chamadas e chats de um thread existente no Skype for Business além do tempo de sessão SIP serão roteados para o Skype for Business da parte remota, independentemente de qual cliente o thread original veio do lado da outra parte.

### <a name="availability"></a>Disponibilidade

Os comportamentos no locatário e federado descritos acima estão disponíveis, com as seguintes limitações:

- Participantes externos cujos locatários residem em uma implantação ou geografia diferente da GoLocal não verão o chat de mensagens de chat enquanto estiver em uma reunião "federada"
- Não há suporte para federação e interopção entre o Multitenant O365 e As Nuvens Soberanas

## <a name="presence"></a>Presença

Quando você tem uma situação em que alguns de seus usuários estão usando o cliente teams e outros ainda estão usando o cliente Skype for Business, você pode ter vários usuários que estão usando os dois clientes. Você ainda quer que os estados de presença sejam compartilhados com todos os usuários, sem levar em consideração o cliente que um usuário individual tem. Quando isso é compartilhado em toda a organização, os usuários podem determinar melhor se é apropriado iniciar um chat ou fazer uma chamada.

Por exemplo, se o chat ou a chamada de um originador chegar ao cliente Skype for Business do destino, então é a presença do cliente Skype for Business que deve ser mostrada ao autor. Se ele chegar ao cliente do Teams do destino, então é a presença do cliente do Teams que deve ser mostrada.

Para saber qual comportamento esperar, você precisará entender que a Presença é compartilhada com base no modo de coexistência do usuário:

* Se um usuário estiver no modo TeamsOnly, qualquer outro usuário (seja no Teams ou no Skype for Business) verá a presença do teams do usuário do TeamsOnly
* Se um usuário estiver em qualquer um dos modos \* SfB (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), qualquer outro usuário (seja no Teams ou no Skype for Business) verá a presença do usuário SfB no \* Skype for Business
* Se um usuário estiver no modo Ilhas (ou Herdado), a presença no Teams e a presença no Skype for Business serão independentes (os valores não precisam corresponder) e outros usuários verão uma ou outra presença do usuário das Ilhas, dependendo se eles estão no mesmo locatário ou em um locatário federado e qual cliente eles usam
    * No Teams, qualquer outro usuário dentro do mesmo locatário verá a presença do Teams do usuário das Ilhas; isso está alinhado com a tabela de roteamento no locatário acima
    * No Teams, qualquer outro usuário em um locatário federado verá a presença do usuário das Ilhas no Skype for Business; isso está alinhado com a tabela de roteamento federado acima
    * No Skype for Business, qualquer outro usuário verá a presença do usuário das Ilhas no Skype for Business (no locatário e federado); isso está alinhado com as tabelas de roteamento acima


### <a name="in-tenant-presence"></a>Presença no locatário

As mensagens enviadas aos usuários do TeamsOnly sempre chegarão no Teams. As mensagens enviadas para usuários SfB sempre chegarão ao Skype for Business, se a \* conversa for possível, conforme descrito acima. As mensagens enviadas para usuários de Ilhas sempre chegarão ao cliente de onde foram originadas.

A tabela descreve a presença do Publisher que será vista por um Watcher, dependendo do modo do Publisher e do cliente do Watcher (para um novo thread).

**Tabela 3: presença no locatário (novo thread)**

|Observador <br/><br/>Cliente|<br/><br/>Rota– > |<br/><br/>Ilhas |Publisher <br/><br/>Sfb\* |<br/>Somente equipes|
|--- |--- |--- |--- |---|
|Skype for Business |&boxv;|Skype for Business | Skype for Business | Teams|
|Teams |&boxv; |Microsoft Teams |Skype for Business |Teams |
| | | | |

### <a name="federated-presence"></a>Presença federada

A presença federada baseia-se na acessibilidade federada mostrada na tabela 2.

A tabela a seguir descreve a presença do Publisher que será vista por um Watcher, dependendo do modo do Publisher e do cliente do Watcher (para um novo thread). Na prática, o cliente do Watcher não faz diferença na federação neste estágio.

**Tabela 4: presença federada (novo thread)**

|Observador <br/><br/> Cliente |<br/><br/>Rota– >|<br/><br/> Ilhas  |Publisher <br/><br/> Sfb\* |<br/><br/> Somente equipes |
|--- |--- |--- |--- |---|
|Skype for Business |&boxv; |Skype for Business  | Skype for Business  | Teams  |
|Microsoft Teams | &boxv;|Skype for Business |Skype for Business |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>Presença em threads pré-existentes

Para alinhar a presença e a acessibilidade em threads pré-existentes, a presença do destino exposta nesse thread precisa ser alinhada com o roteamento do thread, supondo que o roteamento seja possível.

Em particular, se um destinatário com quem você tinha um thread de conversa interop persistente tiver sido atualizado para o Teams, esse thread não refletirá mais a presença precisa e não será mais roueável. Você deve iniciar um novo thread.

## <a name="related-links"></a>Links Relacionados
[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Vídeo: Gerenciar coexistência e interoperabilidade entre o SfB e o Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
