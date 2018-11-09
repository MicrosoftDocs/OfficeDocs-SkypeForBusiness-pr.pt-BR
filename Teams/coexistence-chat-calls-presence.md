---
title: Coexistência com o Skype para negócios
author: jambirk
ms.author: francoid
manager: Serdars
ms.date: 11/7/2018
ms.topic: article
ms.service: msteams
ms.reviewer: francoid
description: Este documento descreve o comportamento de bate-papo, roteamento de chamadas e presença entre usuários das equipes e Skype para os negócios, federados, tanto no locatário com base em modos de TeamsUpgrade atribuídos. Ela inclui as otimizações de roteamento, o comportamento de presença, bem como a alteração do modo de TeamsUpgrade padrão de *legado* para *Ilhas* e a iminente retirada de *legado*.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0d6e4ad171ffc99e1f0aaa1c3b93e0fd61443bc
ms.sourcegitcommit: 42143176c46ba9496a0fd401c8e4774075106b98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238102"
---
# <a name="coexistence-with-skype-for-business"></a>Coexistência com o Skype para negócios

Coexistência e interoperabilidade entre equipes e Skype para negócios é definida por TeamsUpgrade modos, descritos em [migração e orientações de interoperabilidade para as organizações usando equipes em conjunto com o Skype para negócios](migration-interop-guidance-for-teams-with-skype.md).

Qualquer usuário sempre será atribuído um modo de TeamsUpgrade, por padrão, ou explicitamente pelo administrador. O valor padrão é *Ilhas*. Atualizado para equipes de usuários têm o modo de *TeamsOnly*.

> [!NOTE]
> Modo *herdado* foi preterido; os usuários restantes no modo *Legacy* serão convertidos para o modo de *Ilhas* após 15 de novembro de 2018.

## <a name="routing-parameters"></a>Parâmetros de roteamento

O modo de TeamsUpgrade do destinatário é a chave na determinação o comportamento de bate-papos, chamadas e presença, dentro de um inquilino e entre locatários federados.

Se o remetente está usando equipes, a decisão de roteamento é feita ao criar um novo thread de conversação. Threads de conversa existente em equipes sempre mantém o método de roteamento determinado quando o thread foi criado. As equipes suporta segmentos persistentes.

 Métodos de roteamento de thread são:  
* *nativo* para uma conversa de equipes em locatário as equipes
* *interoperabilidade* para um equipes Skype para conversa de negócios no locatário
* *federados* para uma conversa federado entre locatários.

Os parâmetros que determinam o método de roteamento de thread são:
* O modo de TeamsUpgrade do destinatário
* O cliente utilizado pelo remetente
* Se a conversa for novo ou parte de um thread existente
* Se a conversa é no locatário ou federados
* Se a conversa é possível
    * Interoperabilidade no locatário e federação de equipes requer que locatário do originador é puro online ou Skype para o híbrido de negócios. Inquilinos puramente no local não podem ter a federação para equipes ou interoperabilidade no locatário.
    * Se o Skype para a conta de negócios do originador hospedados no local, que o usuário não pode usar o cliente de equipes para a interoperabilidade no locatário e para federação. Que o usuário deve usar o Skype para o cliente de negócios em vez disso, para interoperabilidade e federação.
    * As equipes de comunicação de equipes é sempre possíveis no inquilino.

# <a name="chat-and-call-routing"></a>Roteamento de chamadas e bate-papo

## <a name="in-tenant-routing-for-new-chats-or-calls"></a>Roteamento de chamadas ou novos chats no locatário 

A tabela a seguir captura atual prática para chat no locatário e roteamento de chamada. Esta tabela é válida para novas chamadas ou chats não iniciados a partir de um segmento existente preexistente. Ele descreve quais cliente uma nova chamada (ou chat) será roteada, se foi originada por um usuário à esquerda, para um usuário de destino no locatário à direita.

Mensagens enviadas aos usuários TeamsOnly sempre serão land em equipes. Mensagens enviadas aos usuários do SfB * sempre serão land no Skype para os negócios, se a conversa for possível, conforme descrito acima. Mensagens enviadas aos usuários Ilhas sempre serão land no cliente que eles foram originou.

**Tabela 1: novo chat locatário ou roteamento de chamadas**

| <br/> Modo   | Do&nbsp;originador <br/> Cliente | <br/> SfB&nbsp;hospedados | | <br/> Ilhas  | Para&nbsp;destino <br/> SfB\*   | <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |--- |--- |
| Ilhas <br/>Ilhas <br/>Ilhas <br/>Ilhas<br/> SfB\*<br/> SfB\* <br/> TeamsOnly |Microsoft Teams<br/>SfB <br/>Microsoft Teams <br/>SfB <br/>SfB <br/>SfB <br/>Microsoft Teams|Online<br/> Online<br/> Em prem<br/> Em prem<br/> Online<br/> Em prem<br/> Online| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>|Microsoft Teams <br/> SfB <br/> Microsoft Teams <br/> SfB <br/>  SfB <br/> SfB <br/> Microsoft Teams | *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>*SfB* <br/>  | Microsoft Teams <br/>*Microsoft Teams* <br/>Microsoft Teams <br/>*Microsoft Teams* <br/> *Microsoft Teams*  <br/>*Microsoft Teams* <br/>Microsoft Teams <br/> |
|  | | | | | | |

Na tabela, SfB * representa qualquer um dos seguintes modos: *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

O *texto em itálico* na tabela indica uma conversa de interoperabilidade.

**Negrito** na tabela representa uma situação na qual o bate-papo ou chamada não é possível. Isso ocorre porque a infraestrutura de interoperabilidade só está disponível online e requer o Skype para negócios conta associada à conta de equipes deve ser uma conta online. O originador deve usar Skype para negócios nesses casos. Este é um dos motivos por que uma orientação prescritiva da Microsoft para clientes no prem/híbrido é usar outro modo que Ilhas (geralmente *SfBWithTeamsCollab*) como ponto de partida da sua atualização jornada às equipes.

## <a name="federated-routing-for-new-chats-or-calls"></a>Federados roteamento para chamadas ou chats de novos
  
A tabela a seguir captura práticas atuais de chamada (e bate-papo) roteamento federadas. Esta tabela é válida para novas chamadas ou chats. Ele descreve para o qual cliente uma nova chamada (ou chat) será roteada, se foi originada por um usuário à esquerda, para um usuário de destino federado à direita.

Em resumo, se a conversa for possível, conforme descrito acima, as mensagens enviadas aos usuários TeamsOnly serão sempre land em equipes; mensagens enviadas aos usuários do SfB * sempre serão land no Skype para negócios; mensagens enviadas aos usuários Ilhas sempre serão land no Skype para negócios independentemente do cliente que eles foram originou. Roteamento para federados bate-papos e chamadas difere no locatário roteamento nessa usuários Ilhas sempre receberá uma comunicação federada no Skype para negócios.

O motivo para esse último ponto é que não é possível assumimos que um Skype federado para um parceiro de negócios já usa equipes se eles estão no modo de ilhas. Ilhas é o modo padrão, no entanto, não é possível assumimos que todos os usuários de ilhas executem equipes. Pelo roteamento para Skype para negócios garantimos que nenhuma comunicação a um usuário Ilhas falhar. Se é roteada para equipes, que a comunicação poderão ser perdida se o destino não usou equipes. O roteamento para Skype para negócios garante que a mensagem sempre será recebida.  

> [!NOTE]
> Implementação atual de federação de equipes baseia-se Skype para federação de negócios, portanto, ele aproveita a infraestrutura de interoperabilidade (que exige o locatário do originador seja qualquer puro online ou híbrida SfB) e fornece um conjunto de reduzido recursos em comparação com um thread nativo. Esperamos fornecer equipes nativas à Federação equipes no futuro, ' nesse momento o segmento será nativo e fornecem recursos completos.

**Tabela 2: federado chat novo ou roteamento de chamadas**

| <br/>Modo   | Do originador<br/> Cliente| <br/>SfB hospedados| | <br/> Ilhas | Para o destino<br/> SfB\* | <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |--- |---|
| Ilhas <br/>Ilhas <br/>Ilhas <br/>Ilhas<br/> SfB\*<br/> SfB\* <br/> TeamsOnly |Microsoft Teams<br/>SfB <br/>Microsoft Teams <br/>SfB <br/>SfB <br/>SfB <br/>Microsoft Teams|Online<br/> Online<br/> Em prem<br/> Em prem<br/> Online<br/> Em prem<br/> Online| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>SfB <br/> | *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>SfB <br/>  | Microsoft Teams <br/>Microsoft Teams <br/>**NA** <br/>*As equipes <br/>equipes <br/>equipes* <br/>Microsoft Teams <br/> |
|  | | | | | |

Na tabela, SfB * representa qualquer um dos seguintes modos: *SfBOnly*, *SfBWithTeamsCollab*, *SfBWithTeamsCollabAndMeetings*.

*Texto em itálico* realça uma conversa de interoperabilidade.

**Negrito** representa uma situação na qual o bate-papo ou chamada não é possível. O originador deve usar Skype para negócios nesses casos. Este é um dos motivos por que uma orientação prescritiva da Microsoft para clientes no prem/híbrido é usar outro modo que Ilhas (geralmente SfBWithTeamsCollab) como ponto de partida da sua atualização jornada às equipes.

## <a name="chats-and-calls-from-pre-existing-threads"></a>Bate-papos e chama a partir de threads pré-existente

### <a name="from-teams"></a>De equipes

Chamadas ou chats iniciado a partir de um pré-existente segmento persistente em equipes será roteado da mesma maneira como esse thread, se essa opção Roteamento ainda está disponível. 

Se o segmento persistente pré-existente em equipes era um thread nativo (isto é roteado para equipes), mensagens de chat adicionais e chamadas desse thread irão para equipes. Se foi um thread de interoperabilidade (isto é roteado para Skype for Business), chamadas e mensagens de bate-papo adicionais serão encaminhadas Skype para negócios (novamente supondo roteamento opções estão disponíveis).

> [!NOTE]
> Threads pré-existente em equipes podem não ser mais roteáveis. Isso pode acontecer por exemplo se o segmento teve um thread de interoperabilidade para um usuário que agora é atualizado para equipes. Como é um thread de interoperabilidade, o thread seria rotear para Skype para negócios mas que o usuário não é mais pode usar Skype for Business para o bate-papo e chamadas. Nesse caso, o thread não assinado será desabilitado e não permitir ainda mais a comunicação.

### <a name="from-skype-for-business"></a>Do Skype para negócios

Skype para a empresa não tem persistência de thread além do tempo limite da sessão SIP (mín. 10). Bate-papos e chamadas de um thread existente no Skype para negócios antes da expiração da sessão SIP serão roteadas da mesma maneira como o segmento. Chamadas e chats de um thread existente no Skype para negócios além o limite de sessão SIP serão roteadas para Skype do participante remoto para a empresa, independentemente de qual cliente o segmento original é proveniente no lado da outra parte.

## <a name="availability"></a>Disponibilidade

O comportamento no locatário descrito acima está disponível em produção hoje.

O comportamento federado descrito acima principalmente está disponível em produção hoje. Os seguintes elementos ainda estão sendo distribuídos e estão disponíveis somente para locatários nos primeiros usuários: 
* Federação com um locatário de local com visibilidade de presença
* Exibição dos contatos federados migrados na lista de contatos do cliente equipes
* Capacidade de usar o endereço de URI do SIP ou SMTP para descobrir um contato federado.

Distribuídas para essas tem disponibilidade começada e geral é esperada antes do final de 2018 de novembro.

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
> Isso é uma recente alteração da implementação anterior (chamada de presença unificada) que mostrou uma presença combinada, agregada de equipes e do Skype do destino para clientes corporativos. Essa abordagem anterior tornou-se confuso para os usuários conforme ele for frequentemente resultar em exibindo na presença precisa, ou seja, um usuário que não estão sendo pode ser acessado mesmo que sua presença mostrou online.

## <a name="in-tenant-presence"></a>Presença locatário

Mensagens enviadas aos usuários TeamsOnly sempre serão land em equipes. Mensagens enviadas a SfB\* usuários sempre serão land no Skype para os negócios, se a conversa for possível, conforme descrito acima. Mensagens enviadas aos usuários Ilhas sempre serão land no cliente que eles foram originou.

A tabela descreve a presença do Publisher que será vista por um Inspetor, dependendo do modo do Editor e o cliente do que o Inspetor (para um novo segmento).

**Tabela 3: no locatário presença (novo thread)**

|Inspetor <br/>Cliente| |<br/>Ilhas |Publisher <br/>SfB\* |<br/>Somente as equipes|
|--- |--- |--- |--- |---|
|SfB <br/> Microsoft Teams|&boxv;<br/>&boxv;<br/> |SfB <br/>Microsoft Teams | SfB <br/>SfB | Microsoft Teams  <br/> Microsoft Teams |
| | | | |

## <a name="federated-presence"></a>Presença federada

Presença federada baseia-se a capacidade de alcance federada mostrada na tabela 2.

A tabela abaixo descreve a presença do Publisher que será vista por um Inspetor, dependendo do modo do Editor e o cliente do que o Inspetor (para um novo segmento). Na prática o cliente do que o Inspetor não faz diferença na federação nesse estágio.

**Tabela 4: de presença federada (novo thread)**

|Inspetor <br/> Cliente | |<br/> Ilhas  |Publisher <br/> SfB\* |<br/> Somente as equipes  |
|--- |--- |--- |--- |---|
|SfB <br/> Microsoft Teams|&boxv;<br/>&boxv; |SfB <br/> SfB | SfB <br/> SfB | Microsoft Teams <br/> Microsoft Teams |
| | | | ||

## <a name="presence-in-pre-existing-threads"></a>Presença em threads pré-existente

Para alinhar a presença e a acessibilidade em segmentos pré-existente, a presença do destino exposto nesse thread precisa ser alinhado com o roteamento do thread, é possível considerando roteamento.

Em particular, se um destinatário anteriormente possuía um thread de conversação interoperabilidade persistente com subsequentemente é atualizado para equipes, que thread deixará de refletir presença precisa e deixará de ser roteável. Você deve iniciar um novo segmento.
