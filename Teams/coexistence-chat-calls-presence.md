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
description: Comportamento de coexistência entre equipes & Skype for Business, incluindo parâmetros de roteamento, chat & encaminhamento de chamadas, chats & chamadas de threads pré-existentes, & presença.
ms.openlocfilehash: 9dd2baa717466b0f414168356256b6d78ce33f6a
ms.sourcegitcommit: e5e60079cf9d62627de6b26dd4badd353bcc190c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48661343"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistência com o Skype for Business

A coexistência e interoperabilidade entre os clientes e os clientes do Skype for Business e do teams é definida pelos modos TeamsUpgrade, descritas em [orientação de migração e interoperabilidade para organizações que usam o Microsoft Teams em conjunto com o Skype for Business](migration-interop-guidance-for-teams-with-skype.md).

Qualquer usuário sempre será atribuído um modo TeamsUpgrade, por padrão ou explicitamente pelo administrador. O valor padrão é *ilhas*. Os usuários atualizados para o Microsoft Teams têm o modo de *TeamsOnly*. *SfBOnly*, *SfBWithTeamsCollab*e *SfBWithTeamsCollabAndMeetings* também são possíveis modos.


## <a name="routing-parameters"></a>Parâmetros de roteamento

O modo TeamsUpgrade do destinatário é fundamental para determinar o comportamento de chats, chamadas e presença, ambos dentro de um locatário e entre locatários federados.

Se o remetente estiver usando o Microsoft Teams, a decisão de roteamento será feita durante a criação de um novo thread de conversa. Os threads de conversa existentes no Teams sempre mantêm o método de roteamento determinado quando o thread foi criado: o Teams dá suporte a threads persistentes.

 Os métodos de roteamento de thread são:  

- *nativo* para uma conversa do teams in Teams in-Tenant
- *interoperabilidade* para uma equipe do Skype for Business conversa no locatário
- *federado* para uma conversa federada entre locatários

Os parâmetros que determinam o método de roteamento de thread são:

- O modo TeamsUpgrade do destinatário
- O cliente usado pelo remetente
- Se a conversa é nova ou parte de um thread existente
- Se a conversa é no locatário ou federado
- Se a conversa é possível
    - A interoperabilidade *no locatário* requer que o locatário seja puro online ou Skype for Business híbrido. Locatários puramente locais não podem ter interoperabilidade no locatário.
    - *A Federação entre locatários* sempre exige a configuração de Federação apropriada do Skype for Business, bem como a configuração de Federação apropriada do teams de ambos os locatários. O Skype for Business Hybrid não é necessário para qualquer locatário.
    - Se a conta do Skype for Business do originador for hospedada localmente, esse usuário não poderá usar o cliente do teams para interoperabilidade dentro do locatário ou para Federação. Esse usuário somente pode usar o cliente Skype for Business para interoperabilidade e agrupamento.
    - O Teams para comunicação de equipes sempre é possível no locatário.

> [!NOTE]
> Se o receptor e o remetente estiverem no modo de atualização do TeamsOnly, a conversa será uma experiência de chat nativa que inclui todos os recursos avançados de mensagens e chamadas. Para saber mais, leia [experiência de chat nativo para usuários externos (federados) no Teams](native-chat-for-external-users.md). Se algum dos participantes da conversa não estiver no modo de atualização do TeamsOnly, a conversa permanecerá interoperabilidade com mensagens somente texto.

## <a name="chat-and-call-routing"></a>Chat e encaminhamento de chamadas

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>Roteamento no locatário para novos chats ou chamadas 

As tabelas abaixo encaminham a circulação de chat e chamadas no locatário e são válidas para novas chamadas ou chats que não são iniciados a partir de um thread pré-existente. Ele descreve qual cliente receberá uma nova chamada ou chat, se for originado por um usuário à esquerda, a um usuário do destinatário no locatário à direita.

As mensagens enviadas para os usuários do TeamsOnly sempre serão roteadas para o Microsoft Teams. As mensagens enviadas para \* os usuários do SfB sempre direcionarão para o Skype for Business, se a conversa for possível, conforme descrito acima. As mensagens enviadas para as ilhas usuários sempre serão roteadas para o mesmo cliente a partir do qual elas foram enviadas.

As tabelas a seguir mostram qual cliente em um determinado modo receberá uma chamada do originador (três colunas mais à esquerda), dependendo do modo do originador, do cliente escolhido e onde o cliente do Skype for Business é hospedado (local ou online).

Nas tabelas a seguir: 
- **SfB \* * _ representa qualquer um dos seguintes modos: _SfBOnly *, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

- O *texto em itálico* realça uma conversa de interoperabilidade.

- **Não é possível** representar uma situação na qual o chat ou a chamada não é possível. O originador deve usar o Skype for Business em vez desses casos. Esse é um dos motivos pelos quais a orientação prescritiva da Microsoft para clientes locais/híbridos é usar um modo que não seja ilhas (geralmente SfBWithTeamsCollab) como o ponto de partida da viagem de atualização para o Teams.

**Tabela 1a: novo chat no locatário ou encaminhamento de chamadas para um destinatário do modo de ilhas**

| <br/><br/> Modo | Criador <br/><br/> Cliente | <br/><br/> SfB &nbsp; homed |<br/><br/>Rota-->| Correspondente <br/><br/> Ilhas  |
|--- |--- |--- |--- |--- |
| Ilhas | Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business| Online<br/> Online<br/> Local<br/>Local| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business|
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> Local<br/> |&boxv;<br/>&boxv;|Skype for Business<br/>Skype for Business<br/>|
|TeamsOnly |Teams| Online<br/>|&boxv;<br/>|Teams|
| | | | | |

**Tabela 1b: novo chat no locatário ou encaminhamento de chamadas para um destinatário em um \* modo de SfB**

| <br/><br/> Modo   | Criador <br/><br/> Cliente | <br/><br/> SfB &nbsp; homed |<br/><br/>Rota--> |   Correspondente <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| Ilhas |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business  |Online<br/> Online<br/> Local<br/> Local<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business<br/> **Não é possível** <br/>Skype for Business<br/> |
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> Local<br/> |&boxv;<br/>&boxv; |  Skype for Business<br/>Skype for Business<br/> |
|TeamsOnly |Teams| Online<br/>|&boxv;<br/> |  *Skype for Business* <br/>| 
| | | | | |

**Tabela 1C: novo chat no locatário ou encaminhamento de chamadas para um destinatário do modo TeamsOnly**

| <br/><br/> Modo   | Criador <br/><br/> Cliente | <br/><br/> SfB &nbsp; homed |<br/><br/>Rota-->|   Correspondente <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Ilhas   |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business<br/>|Online<br/> Online<br/> Local<br/> Local<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Microsoft Teams* <br/>Microsoft Teams <br/>*Microsoft Teams*  |
|SfB\*  | Skype for Business<br/>Skype for Business<br/> | Online<br/> Local<br/> | &boxv;<br/>&boxv; | *Microsoft Teams*  <br/>*Microsoft Teams*   |
|TeamsOnly  | Teams | Online |  &boxv; |Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>Roteamento federado para novos chats ou chamadas
  
As tabelas abaixo encaminham a circulação de chamadas federadas e chats e são válidas para novas chamadas ou chats. Elas descrevem qual cliente receberá uma nova chamada ou chat, se for originado por um usuário à esquerda, a um usuário de destino federado à direita.

Em resumo, se a conversa for possível, conforme descrito acima, as mensagens enviadas para os usuários do TeamsOnly sempre irão parar em equipes; as mensagens enviadas para \* os usuários do SfB sempre vão parar no Skype for Business; mensagens enviadas para as ilhas os usuários sempre vão parar no Skype for Business, independentemente do cliente do qual foram enviadas. O roteamento de chats federados e chamadas é diferente do roteamento de locatários nessas ilhas que os usuários sempre receberão uma comunicação federada no Skype for Business.

Isso ocorre porque não podemos pressupor que um parceiro federado do Skype for Business já usa o Teams se ele está no modo de ilhas. Ilhas é o modo padrão, no entanto, não podemos supor que todos os usuários de ilhas executam Teams. Ao direcionar para o Skype for Business, garantimos que não há comunicação com um usuário de ilhas. Se encaminhadas para o Microsoft Teams, essa comunicação poderá ser perdida se o destino não usar o Teams. O roteamento para o Skype for Business garante que a mensagem sempre será recebida.  

> [!NOTE]
> A implementação atual da Federação do teams é baseada na Federação do Skype for Business, portanto, aproveita a infraestrutura de interoperabilidade (que exige que o locatário do originador seja puro online ou híbrido do Skype for Business) e forneça um conjunto reduzido de recursos comparados a um thread nativo. Esperamos fornecer às equipes nativas a Federação de equipes no futuro, em que o thread será nativo e oferecer recursos completos.

As tabelas a seguir descrevem qual cliente receberá uma chamada do originador (três colunas mais à esquerda), dependendo do modo do originador, do cliente escolhido e do local em que o cliente do Skype for Business está hospedado (local ou online).

**Tabela 2a: novo chat federado ou encaminhamento de chamadas para um destinatário de ilhas**

| <br/><br/>Modo   | Criador<br/><br/> Cliente| <br/><br/>SfB homed|<br/><br/>Rota--> | Correspondente<br/><br/> Ilhas |
|--- |--- |--- |--- |--- |
| Ilhas |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business  |Online<br/> Online<br/> Local<br/> Local<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Não é possível**   <br/> Skype for Business |
| SfB\* |Skype for Business <br/>Skype for Business |Online<br/> Local<br/> | &boxv;<br/>&boxv;|Skype for Business <br/>Skype for Business |
| TeamsOnly |Teams |Online| &boxv;|*Skype for Business* |
|  | | | | 

**Tabela 2B: novo chat federado ou encaminhamento de chamadas para um destinatário em um modo de SfB \***

| <br/><br/>Modo   | Criador<br/><br/> Cliente| <br/><br/>SfB homed|<br/><br/>Rota-->|  Correspondente<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| Ilhas |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> Local<br/> Local<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Não é possível** <br/>Skype for Business <br/> |  
| SfB\* |Skype for Business <br/>Skype for Business  |Online<br/> Local<br/>  |&boxv;<br/>&boxv; | Skype for Business <br/>Skype for Business  |
| TeamsOnly | Teams|Online |&boxv; |*Skype for Business*  |
|  | | | | |

**Tabela 2C: novo chat federado ou encaminhamento de chamadas para um destinatário do modo TeamsOnly**

| <br/><br/>Modo | Criador<br/><br/> Cliente| <br/><br/>SfB homed|<br/><br/>Rota-->|  Correspondente<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Ilhas  |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> Local<br/> Local<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Microsoft Teams* <br/>**Não é possível** <br/>*Microsoft Teams* |
| SfB\* |Skype for Business <br/>Skype for Business  | Online<br/> Local| &boxv;<br/>&boxv;|*Microsoft Teams* <br/>*Microsoft Teams*   |
| TeamsOnly |Teams |Online |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Chats e chamadas de threads preexistentes

### <a name="from-teams"></a>Do teams

Chamadas ou chats iniciados a partir de um thread persistente pré-existente no Teams serão roteados da mesma maneira que aquele thread, se essa opção de direcionamento ainda estiver disponível.

Se o thread persistente pré-existente no Microsoft Teams era um thread nativo (ou seja, roteado para equipes), mensagens de chat e chamadas adicionais desse thread vão para o Teams. Se for um thread de interoperabilidade (ou seja, roteado para o Skype for Business), mensagens de chat e chamadas adicionais vão para o Skype for Business (novamente presumindo que as opções de roteamento estão disponíveis).

> [!NOTE]
> É possível que threads pré-existentes no Microsoft Teams não sejam mais roteáveis, como quando o thread era um thread de interoperabilidade para um usuário que agora está atualizado para o Microsoft Teams. Desde que ele foi criado como um thread de interoperabilidade, o thread encaminharia para o Skype for Business, mas esse usuário não pode mais usar o Skype for Business para chat e chamadas. Nesse caso, o thread será desabilitado e não permitirá outras comunicações.

### <a name="from-skype-for-business"></a>Do Skype for Business

Os threads do Skype for Business não persistem além do tempo limite de sessão SIP de 10 min. Chats e chamadas de um thread existente no Skype for Business antes da expiração da sessão SIP serão roteadas da mesma maneira que o thread. Chamadas e chats de um thread existente no Skype for Business além do tempo limite da sessão SIP serão roteadas para o Skype for Business da parte remota, independentemente do cliente do qual o thread original veio no lado da outra pessoa.

### <a name="availability"></a>Disponibilidade

Os comportamentos de locatário e federado descritos acima estão disponíveis com as seguintes limitações:

- Os participantes externos cujos locatários residem em uma implantação diferente do GoLocal ou geografia não verão chats de mensagem instantânea enquanto estiverem em uma reunião "federada"
- Não há suporte para Agrupamento e interoperabilidade entre nuvens multilocatário do O365 e do soberana

## <a name="presence"></a>Presença

Quando alguns usuários estiverem usando o cliente do Microsoft Teams e outros ainda estiverem usando o cliente do Skype for Business, você pode ter vários usuários que estão usando os dois clientes. Você ainda quer que os Estados de presença sejam compartilhados com todos os usuários sem considerar o cliente que um usuário individual tem. Quando isso é compartilhado em toda a organização, os usuários podem determinar melhor se é apropriado iniciar um chat ou fazer uma chamada.

Por exemplo, se o chat ou a chamada de um originador deve se chamar no cliente Skype for Business do alvo, a presença do cliente do Skype for Business que deve ser mostrada para o originador. Se ele deve ser apresentado no cliente do teams do destino, então é a presença do cliente das equipes que deve ser mostrada.

Para saber qual comportamento esperar, você precisará compreender que a presença é compartilhada com base no modo de coexistência de um usuário:

* Se um usuário estiver no modo TeamsOnly, qualquer outro usuário (seja no Teams ou no Skype for Business) verá que a presença de equipes do usuário do TeamsOnly
* Se um usuário estiver em qualquer um dos modos de SfB \* (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), qualquer outro usuário (seja no Teams ou no Skype for Business) verá a \* presença do SfB do Skype for Business do
* Se um usuário estiver no modo de ilhas (ou herdado), a presença nas equipes e presença no Skype for Business é independente (os valores precisam não corresponder) e outros usuários verão uma ou outra presença do usuário da Ilhas, dependendo se estiverem no mesmo locatário ou em um locatário federado e qual cliente ele usa
    * No Teams, qualquer outro usuário no mesmo locatário verá a presença de equipes do usuário das Ilhas; Isso é alinhado com a tabela de roteamento do locatário acima
    * No Teams, qualquer outro usuário em um locatário federado verá a presença do Skype for Business do usuário de ilhas; Isso é alinhado com a tabela de roteamento federado acima
    * No Skype for Business, qualquer outro usuário verá a presença do Skype for Business do usuário das ilhas (dentro do locatário e federado); Isso é alinhado com as tabelas de roteamento acima


### <a name="in-tenant-presence"></a>Presença no locatário

As mensagens enviadas para usuários do TeamsOnly sempre vão para o Microsoft Teams. As mensagens enviadas para \* usuários do SfB sempre vão parar no Skype for Business, se a conversa for possível, conforme descrito acima. As mensagens enviadas para as ilhas usuários sempre vão para o cliente do qual elas se originaram.

A tabela descreve a presença do fornecedor que será vista por um observador, dependendo do modo do fornecedor e do cliente do Inspetor (para um novo thread).

**Tabela 3: presença no locatário (novo thread)**

|Inspetor <br/><br/>Cliente|<br/><br/>Rota--> |<br/><br/>Ilhas |Publisher <br/><br/>SfB\* |<br/>Somente equipes|
|--- |--- |--- |--- |---|
|Skype for Business |&boxv;|Skype for Business | Skype for Business | Teams|
|Teams |&boxv; |Microsoft Teams |Skype for Business |Teams |
| | | | |

### <a name="federated-presence"></a>Presença federada

A presença federada se baseia na acessibilidade federada mostrada na tabela 2.

A tabela a seguir descreve a presença do fornecedor que será vista por um observador, dependendo do modo do fornecedor e do cliente do Inspetor (para um novo thread). Na prática, o cliente do inspetor não faz diferença na Federação neste estágio.

**Tabela 4: presença federada (novo thread)**

|Inspetor <br/><br/> Cliente |<br/><br/>Rota-->|<br/><br/> Ilhas  |Publisher <br/><br/> SfB\* |<br/><br/> Somente equipes |
|--- |--- |--- |--- |---|
|Skype for Business |&boxv; |Skype for Business  | Skype for Business  | Teams  |
|Microsoft Teams | &boxv;|Skype for Business |Skype for Business |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>Presença em threads preexistentes

Para alinhar a presença e a acessibilidade em threads pré-existentes, a presença do destino exposta nesse thread precisa ser alinhada com o roteamento do thread, pressupondo que o roteamento seja possível.

Em particular, se um destinatário com o qual você tinha anteriormente um thread de conversa de interoperabilidade persistente tivesse sido atualizado para o Teams, esse thread não refletirá mais a presença precisa e não será mais roteável. Você deve iniciar um novo thread.

## <a name="related-links"></a>Links relacionados
[Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Vídeo: gerenciar a coexistência e interoperabilidade entre o SfB e o Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
