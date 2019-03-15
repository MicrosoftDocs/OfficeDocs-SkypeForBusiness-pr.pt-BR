---
title: Coexistência com o Skype for Business
author: jambirk
ms.author: francoid
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
description: Este documento descreve o comportamento de bate-papo, roteamento de chamadas e presença entre usuários das equipes e Skype para os negócios, federados, tanto no locatário com base em modos de TeamsUpgrade atribuídos. Ela inclui as otimizações de roteamento, o comportamento de presença, bem como a alteração do modo de TeamsUpgrade padrão de *legado* para *Ilhas* e a iminente retirada de *legado*.
ms.openlocfilehash: c6343b7f62249dab6e02c1e42fce1cc567f5035a
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569699"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistência com o Skype for Business

Coexistência e interoperabilidade entre os usuários e Skype para clientes empresariais e equipes é definida por TeamsUpgrade modos, descritos na [migração e orientações de interoperabilidade para organizações que usam equipes em conjunto com o Skype para negócios](migration-interop-guidance-for-teams-with-skype.md).

Qualquer usuário sempre será atribuído um modo de TeamsUpgrade, por padrão, ou explicitamente pelo administrador. O valor padrão é *Ilhas*. Atualizado para equipes de usuários têm o modo de *TeamsOnly*. *SfBOnly*, *SfBWithTeamsCollab*e *SfBWithTeamsCollabAndMeetings* também são modos possíveis.

> [!NOTE]
> Modo *herdado* foi preterido; os usuários que estavam em modo *Legacy* foram convertidos em modo *Ilhas* .

## <a name="routing-parameters"></a>Parâmetros de roteamento

O modo de TeamsUpgrade do destinatário é a chave na determinação o comportamento de bate-papos, chamadas e presença, dentro de um inquilino e entre locatários federados.

Se o remetente está usando equipes, a decisão de roteamento é feita ao criar um novo thread de conversação. Threads de conversa existente em equipes sempre retêm o método de roteamento determinado quando o thread foi criado: equipes suporta segmentos persistentes.

 Métodos de roteamento de thread são:  

- *nativo* para uma conversa de equipes em locatário as equipes
- *interoperabilidade* para um equipes Skype para conversa de negócios no locatário
- *federados* para uma conversa federado entre locatários

Os parâmetros que determinam o método de roteamento de thread são:

- O modo de TeamsUpgrade do destinatário
- O cliente utilizado pelo remetente
- Se a conversa for novo ou parte de um thread existente
- Se a conversa é no locatário ou federados
- Se a conversa é possível
    - Interoperabilidade de *no locatário* requer que o inquilino é puro online ou Skype para o híbrido de negócios. Inquilinos puramente no local não podem ter interoperabilidade no inquilino.
    - *A federação de locatário entre* sempre requer Skype adequado para configuração da federação de negócios, bem como a configuração apropriada de federação de equipes de ambos os locatários. Skype para o híbrido de negócios não é necessário de um inquilino.
    - Se o Skype para a conta de negócios do originador hospedados no local, o que o usuário não pode usar o cliente de equipes para a interoperabilidade no locatário ou para federação. Esse usuário só pode usar o Skype para o cliente de negócios para interoperabilidade e federação.
    - As equipes de comunicação de equipes é sempre possíveis no inquilino.

> [!NOTE]
> Atualmente, todos os federação envolvendo equipes aproveita o Skype para o pipeline de federação de negócios, bem como as equipes – Skype para a interoperabilidade de negócios. Podemos estiver planejando equipes nativas – federação de equipes. O documento presente será atualizado mediante a liberação da federação nativa.

# <a name="chat-and-call-routing"></a>Roteamento de chamadas e bate-papo

## <a name="in-tenant-routing-for-new-chats-or-calls"></a>Roteamento de chamadas ou novos chats no locatário 

As tabelas a seguir capturam o roteamento de chamadas e no locatário chat e são válidas para novas chamadas ou chats não iniciados a partir de um segmento preexistente. Ele descreve qual cliente receberá uma nova chamada ou bate-papo, se foi originada por um usuário à esquerda, para um usuário de destinatário no locatário à direita.

Mensagens enviadas aos usuários TeamsOnly sempre roteará para equipes. Mensagens enviadas a SfB\* usuários sempre roteará para Skype para os negócios, se a conversa for possível, conforme descrito acima. Mensagens enviadas aos usuários Ilhas sempre roteará para o mesmo cliente do qual eles foram enviados.

As tabelas a seguir mostram qual cliente em um determinado modo receberá uma chamada do originador (três extrema esquerdas colunas), dependendo do modo do originador, o cliente escolhido, e onde os seu Skype para o cliente de negócios está hospedado (em prem ou online).

Nas tabelas a seguir: 
- **SfB\* ** representa qualquer um dos seguintes modos: *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

- *Texto em itálico* realça uma conversa de interoperabilidade.

- **Não é possível** representa uma situação na qual o bate-papo ou chamada não é possível. O originador deve usar Skype para negócios nesses casos. Este é um dos motivos por que uma orientação prescritiva da Microsoft para clientes no prem/híbrido é usar um modo que não seja Ilhas (geralmente SfBWithTeamsCollab) como ponto de partida da sua atualização jornada às equipes.

**Tabela 1a: novo chat locatário ou para um destinatário de modo Ilhas o roteamento de chamadas**

| <br/><br/> Modo | Originador <br/><br/> Cliente | <br/><br/> SfB&nbsp;hospedados | | Destinatário <br/><br/> Ilhas  |
|--- |--- |--- |--- |--- |
| Ilhas | Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business| Online<br/> Online<br/> Em prem<br/>Em prem| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Microsoft Teams <br/> Skype for Business<br/> Microsoft Teams<br/> Skype for Business|
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> Em prem<br/> |&boxv;<br/>&boxv;|Skype for Business<br/>Skype for Business<br/>|
|TeamsOnly |Microsoft Teams| Online<br/>|&boxv;<br/>|Microsoft Teams|
| | | | | |

**Tabela 1b: chat novo inquilino ou chamada de roteamento para um destinatário em uma SfB\* modo**

| <br/><br/> Modo   | Originador <br/><br/> Cliente | <br/><br/> SfB&nbsp;hospedados | |   Destinatário <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| Ilhas |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business  |Online<br/> Online<br/> Em prem<br/> Em prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business<br/> **Não é possível** <br/>Skype for Business<br/> |
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> Em prem<br/> |&boxv;<br/>&boxv; |  Skype for Business<br/>Skype for Business<br/> |
|TeamsOnly |Microsoft Teams| Online<br/>|&boxv;<br/> |  *Skype for Business* <br/>| 
| | | | | |

**Tabela 1c: novo chat locatário ou para um destinatário de modo TeamsOnly o roteamento de chamadas**

| <br/><br/> Modo   | Originador <br/><br/> Cliente | <br/><br/> SfB&nbsp;hospedados | |   Destinatário <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| Ilhas   |Microsoft Teams<br/>Skype for Business<br/>Microsoft Teams <br/>Skype for Business<br/>|Online<br/> Online<br/> Em prem<br/> Em prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Microsoft Teams <br/>*Microsoft Teams* <br/>Microsoft Teams <br/>*Microsoft Teams*  |
|SfB\*  | Skype for Business<br/>Skype for Business<br/> | Online<br/> Em prem<br/> | &boxv;<br/>&boxv; | *Microsoft Teams*  <br/>*Microsoft Teams*   |
|TeamsOnly  | Microsoft Teams | Online |  &boxv; |Microsoft Teams   |
|  |  |  | | |

## <a name="federated-routing-for-new-chats-or-calls"></a>Federados roteamento para chamadas ou chats de novos
  
As tabelas a seguir capturam o roteamento de bate-papos e chamadas federadas e são válidas para novas chamadas ou chats. Eles descrevem qual cliente receberá uma nova chamada ou bate-papo, se foi originada por um usuário à esquerda, para um usuário de destino federado à direita.

Em resumo, se a conversa for possível, conforme descrito acima, as mensagens enviadas aos usuários TeamsOnly serão sempre land em equipes; mensagens enviadas a SfB\* usuários sempre serão land no Skype para negócios; mensagens enviadas aos usuários Ilhas sempre serão land no Skype para negócios independentemente do cliente do qual eles foram enviados. Roteamento para federados bate-papos e chamadas difere no locatário roteamento nessa usuários Ilhas sempre receberá uma comunicação federada no Skype para negócios.

Isso ocorre porque não é possível assumimos que um Skype federado para um parceiro de negócios já usa equipes se eles estão no modo de ilhas. Ilhas é o modo padrão, no entanto, não é possível assumimos que todos os usuários de ilhas executem equipes. Pelo roteamento para Skype para negócios garantimos que nenhuma comunicação a um usuário Ilhas falhar. Se é roteada para equipes, que a comunicação poderão ser perdida se o destino não usou equipes. O roteamento para Skype para negócios garante que a mensagem sempre será recebida.  

> [!NOTE]
> Implementação atual de federação de equipes baseia-se Skype para federação de negócios, portanto, ele aproveita a infraestrutura de interoperabilidade (que exige o locatário do originador seja qualquer puro online ou Skype para o híbrido de negócios) e fornece um conjunto de recursos em comparação com um thread nativo reduzido. Esperamos fornecer equipes nativas à Federação equipes no futuro, ' nesse momento o segmento será nativo e fornecem recursos completos.

As tabelas a seguir descrevem qual cliente receberá uma chamada do originador (três extrema esquerdas colunas), dependendo do modo do originador, escolhido do cliente, e onde os seu Skype para o cliente de negócios está hospedado (em prem ou online).

**Tabela 2a: federados novo bate-papo ou roteamento de chamadas para um destinatário de ilhas**

| <br/><br/>Modo   | Originador<br/><br/> Cliente| <br/><br/>SfB hospedados| | Destinatário<br/><br/> Ilhas |
|--- |--- |--- |--- |--- |
| Ilhas |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business  |Online<br/> Online<br/> Em prem<br/> Em prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Não é possível**   <br/> Skype for Business |
| SfB\* |Skype for Business <br/>Skype for Business |Online<br/> Em prem<br/> | &boxv;<br/>&boxv;|Skype for Business <br/>Skype for Business |
| TeamsOnly |Microsoft Teams |Online| &boxv;|*Skype for Business* |
|  | | | | 

**Tabela 2b: federados novo bate-papo ou roteamento de chamadas para a um destinatário em uma SfB\* modo**

| <br/><br/>Modo   | Originador<br/><br/> Cliente| <br/><br/>SfB hospedados| |  Destinatário<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| Ilhas |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> Em prem<br/> Em prem<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **Não é possível** <br/>Skype for Business <br/> |  
| SfB\* |Skype for Business <br/>Skype for Business  |Online<br/> Em prem<br/>  |&boxv;<br/>&boxv; | Skype for Business <br/>Skype for Business  |
| TeamsOnly | Microsoft Teams|Online |&boxv; |*Skype for Business*  |
|  | | | | |

**Tabela 2c: federados novo bate-papo ou roteamento de chamadas para um destinatário de modo TeamsOnly**

| <br/><br/>Modo | Originador<br/><br/> Cliente| <br/><br/>SfB hospedados| |  Destinatário<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| Ilhas  |Microsoft Teams<br/>Skype for Business <br/>Microsoft Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> Em prem<br/> Em prem<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Microsoft Teams <br/>*Microsoft Teams* <br/>**Não é possível** <br/>*Microsoft Teams* |
| SfB\* |Skype for Business <br/>Skype for Business  | Online<br/> Em prem| &boxv;<br/>&boxv;|*Microsoft Teams* <br/>*Microsoft Teams*   |
| TeamsOnly |Microsoft Teams |Online |&boxv; |Microsoft Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>Bate-papos e chama a partir de threads pré-existente

### <a name="from-teams"></a>De equipes

Chamadas ou chats iniciado a partir de um pré-existente segmento persistente em equipes será roteado da mesma maneira como esse thread, se essa opção Roteamento ainda está disponível.

Se o segmento persistente pré-existente em equipes era um thread nativo (isto é roteado para equipes), mensagens de chat adicionais e chamadas desse thread irão para equipes. Se foi um thread de interoperabilidade (isto é roteado para Skype for Business), chamadas e mensagens de bate-papo adicionais serão encaminhadas Skype para negócios (novamente supondo roteamento opções estão disponíveis).

> [!NOTE]
> É possível que pré-existente threads em equipes deixará de ser roteável, como quando o thread foi um thread de interoperabilidade para um usuário que agora é atualizado para equipes. Desde que ela foi criada por um segmento de interoperabilidade, o thread seria rotear para Skype para negócios, mas que o usuário não é mais pode usar Skype for Business para chamadas e bate-papo. Nesse caso, o thread não assinado será desabilitado e não permitir ainda mais a comunicação.

### <a name="from-skype-for-business"></a>Do Skype para negócios

Skype para os segmentos de negócios não persiste além do tempo limite da sessão SIP mín. 10. Bate-papos e chamadas de um thread existente no Skype para negócios antes da expiração da sessão SIP serão roteadas da mesma maneira como o segmento. Chamadas e chats de um thread existente no Skype para negócios além o limite de sessão SIP serão roteadas para Skype do participante remoto para a empresa, independentemente de qual cliente o segmento original é proveniente no lado da outra parte.

## <a name="availability"></a>Disponibilidade

Ambos no locatário e federados comportamentos descritos acima estão disponíveis, com as seguintes limitações:

- Participantes externos cujos inquilinos residem em uma implantação de GoLocal diferente ou um geografia não verá a mensagem Instantânea em uma reunião "federada" o bate-papo
- Não há suporte para federação e interoperabilidade entre multi-inquilinos O365 e nuvens Sovereign

# <a name="presence"></a>Presença

Quando você tem uma situação na qual alguns dos usuários estão usando o cliente de equipes e outros ainda estiver usando o Skype para o cliente de negócios, você pode ter um número de usuários que estejam usando ambos os clientes. Deseja continuar a estados de presença para serem compartilhadas com todos os usuários sem relação com os qual um usuário individual tem de cliente. Quando isso é compartilhado em toda a organização, os usuários podem determinar melhor se é apropriado iniciar um bate-papo ou fazer uma chamada.

Por exemplo, se o bate-papo ou chamada de um originador deve parar em Skype do destino para o cliente de negócios, ele será o Skype para presença do cliente de negócios que deve ser exibida ao originador. Se ele deve land no cliente de equipes do destino, ele é presença do cliente equipes que deve ser exibida.

Para saber qual comportamento esperar, você precisará compreender o que a presença é compartilhada com base no modo de coexistência de um usuário:

* Se um usuário estiver em modo TeamsOnly, qualquer outro usuário (seja expressa em equipes ou Skype para negócios) verá presença de equipes desse usuário TeamsOnly
* Se um usuário estiver em qualquer uma do SfB\* modos (SfbOnly, SfbWithTeamsCollab, SfbWithTeamsCollabAndMeetings), então qualquer outro usuário (seja expressa em equipes ou Skype para negócios) verão que SfB\* Skype do usuário para a presença de negócios
* Se um usuário está em Ilhas (ou herdada) modo, a presença em equipes e presença em Skype para negócios são independente (os valores não precisam corresponder) e outros usuários verão uma ou as outras informações de presença do usuário Ilhas, dependendo se eles estão no mesmo inquilino ou em um federat locatário ED e quais clientes utilizarem
    * De equipes, qualquer outro usuário dentro do mesmo inquilino verá a presença de equipes do usuário Ilhas; Isso é alinhado com a tabela de roteamento no locatário acima
    * De equipes, qualquer outro usuário em um locatário federado verá Skype do usuário ilhas de presença de negócios; Isso é alinhado com a tabela de roteamento federada acima
    * Do Skype para os negócios, qualquer outro usuário verá Skype do usuário ilhas de presença de negócios (no locatário e federada); Isso é alinhado com as tabelas de roteamento acima

> [!NOTE]
> Isso é uma recente alteração da implementação anterior (chamada de presença unificada) que mostrou uma presença combinada, agregada de equipes e do Skype do destino para clientes corporativos. Essa abordagem anterior tornou-se confuso para os usuários conforme ele for frequentemente resultar em exibindo imprecisa presença, ou seja, um usuário que não estão sendo pode ser acessado mesmo que sua presença mostrou online.

## <a name="in-tenant-presence"></a>Presença locatário

Mensagens enviadas aos usuários TeamsOnly sempre serão land em equipes. Mensagens enviadas a SfB\* usuários sempre serão land no Skype para os negócios, se a conversa for possível, conforme descrito acima. Mensagens enviadas aos usuários Ilhas sempre serão land no cliente que eles foram originou.

A tabela descreve a presença do Publisher que será vista por um Inspetor, dependendo do modo do Editor e o cliente do que o Inspetor (para um novo segmento).

**Tabela 3: no locatário presença (novo thread)**

|Inspetor <br/><br/>Cliente| |<br/><br/>Ilhas |Publisher <br/><br/>SfB\* |<br/>Somente as equipes|
|--- |--- |--- |--- |---|
|Skype for Business |&boxv;|Skype for Business | Skype for Business | Microsoft Teams|
|Microsoft Teams |&boxv; |Microsoft Teams |Skype for Business |Microsoft Teams |
| | | | |

## <a name="federated-presence"></a>Presença federada

Presença federada baseia-se a capacidade de alcance federada mostrada na tabela 2.

A tabela abaixo descreve a presença do Publisher que será vista por um Inspetor, dependendo do modo do Editor e o cliente do que o Inspetor (para um novo segmento). Na prática o cliente do que o Inspetor não faz diferença na federação nesse estágio.

**Tabela 4: de presença federada (novo thread)**

|Inspetor <br/><br/> Cliente | |<br/><br/> Ilhas  |Publisher <br/><br/> SfB\* |<br/><br/> Somente as equipes |
|--- |--- |--- |--- |---|
|Skype for Business |&boxv; |Skype for Business  | Skype for Business  | Microsoft Teams  |
|Microsoft Teams | &boxv;|Skype for Business |Skype for Business |Microsoft Teams|
| | | | ||

## <a name="presence-in-pre-existing-threads"></a>Presença em threads pré-existente

Para alinhar a presença e a acessibilidade em segmentos pré-existente, a presença do destino exposto nesse thread precisa ser alinhado com o roteamento do thread, é possível considerando roteamento.

Em particular, se um destinatário anteriormente possuía um thread de conversação interoperabilidade persistente com foi atualizado para equipes, que thread deixará de refletir presença precisa e deixará de ser roteável. Você deve iniciar um novo segmento.

## <a name="related-links"></a>Links relacionados

[Vídeo: Gerenciar a interoperabilidade entre SfB e equipes e coexistência](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
