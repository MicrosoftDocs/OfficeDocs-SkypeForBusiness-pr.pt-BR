---
title: Exibir análises no Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: rahulmi
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-collaboration
description: Saiba mais sobre a análise de várias equipes, a análise por equipe e a análise por canal no Teams, que permitem que os usuários vejam dados de uso para equipes ou canais dos quais fazem parte.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9261678848589028155d58449bf84d083ff756c2
ms.sourcegitcommit: 929c050c038a64216e38b0a67569a8f18ad4baf2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43940891"
---
# <a name="view-analytics-in-teams"></a>Exibir análises no Teams

No Microsoft Teams, os usuários podem exibir análises para equipes e canais dos quais fazem parte. Essas informações dão aos usuários a percepção dos padrões de uso e atividades em suas equipes. Os usuários podem ver dados como o número de usuários ativos, postagens, respostas e muito mais em três níveis.

- A **análise de equipe cruzada** oferece aos usuários uma ampla visão geral dos dados de uso para todas as equipes que são membros ou proprietários de um único modo de exibição de lista.
- A **análise por equipe** proporciona aos usuários uma exibição mais granular, mostrando dados de uso para uma equipe específica.
- **A análise por canal** proporciona aos usuários uma exibição ainda mais granular, mostrando dados de uso para um canal específico.

Os usuários podem filtrar qualquer um desses modos de exibição para ver os dados por um período de tempo especificado.

## <a name="view-cross-team-analytics"></a>Exibir a análise de equipe cruzada

1. No Teams, na parte inferior da lista de equipes, ao lado de **ingressar ou criar uma equipe**, clique em **gerenciar equipes**.
2. Clique na guia **análise** .
3. Selecione um intervalo de datas para mostrar os dados de uso de todas as equipes das quais você é membro ou proprietário.

    ![Captura de tela do modo de exibição de análise de equipe cruzada](../media/view-analytics-cross-team.png)

    |Item |Descrição  |
    |--------|-------------|
    |**Nome**   |Nome da equipe. |
    |**Usuários ativos**   |Número de usuários ativos na linha de equipe e na linha de tendência das atividades da equipe durante o período de tempo especificado.
    |**Pessoas**   |Número total de pessoas na equipe no período de tempo especificado. Isso inclui os proprietários da equipe, os membros da equipe e os convidados.|
    |**Pessoas**   |Número de convidados na equipe durante o período de tempo especificado. |
    |**Lançada**   |Número de novas mensagens postadas no chat da equipe durante o período de tempo especificado. |
    |**Responde**   |Número de respostas no chat da equipe durante o período de tempo especificado. |
    |**Tipo**   |Se a equipe é uma equipe particular ou uma equipe pública.|

## <a name="view-per-team-analytics"></a>Exibir por análise de equipe

1. No Teams, vá para a equipe desejada, clique em **mais opções (...)** e, em seguida, clique em **Gerenciar equipe**.
2. Clique na guia **análise** .
4. Selecione um intervalo de datas para mostrar os dados de uso da equipe.  

    ![Captura de tela do modo de exibição por análise de equipe](../media/view-analytics-per-team.png)

    |Item |Descrição  |
    |--------|-------------|
    |**Resumo**   |Resumo das atividades da equipe, incluindo as seguintes:<ul><li>**Usuários**: número total de usuários no período de tempo especificado. Isso inclui os proprietários da equipe, os membros da equipe e os convidados.</li> <li>**Postagens**: número de novas mensagens publicadas no chat da equipe durante o período de tempo especificado.</li><li>**Respostas**: número de respostas no chat da equipe durante o período de tempo especificado.</li> <li>**Aplicativos**: número de aplicativos adicionados à equipe.</li><li>**Reuniões**: número de reuniões de equipes organizadas no nível da equipe.</li> </ul> |
    |**Usuários ativos**   |Número de usuários ativos e inativos.|
    |**Função**   |Números de usuários por função, incluindo proprietários de equipes, membros da equipe e convidados.|
    |Gráfico **usuários ativos**  |Número de dias ativos diariamente. Passe o mouse sobre o ponto em uma determinada data para ver o número de usuários ativos nessa data.|
    |Gráfico de **mensagens**  |Número total de mensagens postadas no chat da equipe por data. Passe o mouse sobre o ponto em uma determinada data para ver o número de novas postagens e respostas lançadas nessa data.|

> [!TIP]
> Você também pode exibir a análise por equipe clicando em uma equipe em uma lista no [modo de exibição de análise de várias equipes](#view-cross-team-analytics).

## <a name="view-per-channel-analytics"></a>Exibir análise por canal

1. No Teams, vá para o canal desejado, clique em **mais opções (...)** e clique em **gerenciar canal**.
2. Clique na guia **análise** .
3. Selecione um intervalo de datas para mostrar os dados de uso do canal.  

    ![Captura de tela do modo de exibição analítico por canal](../media/view-analytics-per-channel.png)

    |Item |Descrição  |
    |--------|-------------|
    |**Resumo**   |Resumo da atividade do canal, incluindo o seguinte:<ul><li>**Usuários**: número total de usuários no período de tempo especificado. Isso inclui os proprietários da equipe, os membros da equipe e os convidados.</li> <li>**Postagens**: número de novas mensagens publicadas no canal durante o período de tempo especificado.</li><li>**Respostas**: número de respostas no canal durante o período de tempo especificado.</li> <li>**Aplicativos**: número de aplicativos adicionados ao canal.</li> </ul> |
    |Gráfico de **mensagens**  |Número total de mensagens postadas no chat do canal por data. Passe o mouse sobre o ponto em uma determinada data para ver o número de novas postagens e respostas lançadas nessa data.|

> [!TIP]
> Você também pode visualizar a análise por canal selecionando um canal na caixa de listagem suspensa no [modo de exibição por análise de equipe](#view-per-team-analytics).
    
> [!NOTE]
> Definimos usuários ativos como usuários que executam uma ação intencional no cliente da área de trabalho, cliente móvel e cliente Web. Exemplos de uma ação intencional incluem o início de um chat, a realização de uma chamada, o compartilhamento de um arquivo, a edição de um documento dentro do Microsoft Teams, a participação em uma reunião e assim por diante. Impedimos ações passivas, como inicialização automática, minimizando uma tela ou fechando o aplicativo. Também eliminamos a duplicação de todas as ações em uma única ID de usuário.

## <a name="related-topics"></a>Tópicos relacionados

- [Exibir análises para suas equipes](https://support.office.com/article/view-analytics-for-your-teams-5b8ad4b1-af34-4217-aff4-cd11a820b56b)
- [Análises e relatórios do Teams](teams-reporting-reference.md)