---
title: Exibir análise no Teams
author: cichur
ms.author: v-cichur
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
description: Saiba mais sobre a análise entre equipes, análises por equipe e análises por canal no Teams, que permitem que os usuários vejam dados de uso para equipes ou canais dos quais fazem parte.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 00ac44638a3f1b79ba98d1b2ebc6cf3645ef44bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809171"
---
# <a name="view-analytics-in-teams"></a>Exibir análise no Teams

No Microsoft Teams, os usuários podem exibir análises para equipes e canais dos que fazem parte. Essas informações proporcionam aos usuários informações sobre padrões de uso e atividades em suas equipes. Os usuários podem ver dados como o número de usuários ativos, postagens, respostas e muito mais em três níveis.

- **A análise entre equipes** oferece aos usuários uma visão geral ampla dos dados de uso de todas as equipes das que são membros ou proprietários em uma única exibição de lista.
- **A análise por equipe** oferece aos usuários uma exibição mais granular, mostrando dados de uso para uma equipe específica.
- **A análise por canal** oferece aos usuários uma exibição ainda mais granular, mostrando dados de uso para um canal específico.

Os usuários podem filtrar qualquer uma dessas exibições para ver dados por um período de tempo especificado.

## <a name="view-cross-team-analytics"></a>Exibir análise entre equipes

1. No Teams, na parte inferior da lista de equipes, ao lado de Ingressar ou **criar uma equipe,** clique em **Gerenciar equipes.**
2. Clique na **guia** Análise.
3. Selecione um intervalo de datas para mostrar os dados de uso de todas as equipes das que você é membro ou proprietário.

    ![Captura de tela do exibição de análise entre equipes](../media/view-analytics-cross-team.png)

    |Item |Descrição  |
    |--------|-------------|
    |**Nome**   |Nome da equipe. |
    |**Usuários ativos**   |Número de usuários ativos na equipe e na linha de tendência da atividade da equipe durante o período de tempo especificado.
    |**Pessoas**   |Número total de pessoas na equipe no período de tempo especificado. Isso inclui proprietários da equipe, membros da equipe e convidados.|
    |**Convidados**   |Número de convidados na equipe durante o período de tempo especificado. |
    |**Postagens**   |Número de novas mensagens publicadas no chat de equipe durante o período de tempo especificado. |
    |**Respostas**   |Número de respostas no chat em equipe durante o período de tempo especificado. |
    |**Tipo**   |Se a equipe é uma equipe privada ou pública.|

## <a name="view-per-team-analytics"></a>Exibir análise por equipe

1. No Teams, vá para a equipe que você deseja, clique em **Mais opções (...)** e clique em **Gerenciar equipe.**
2. Clique na **guia** Análise.
4. Selecione um intervalo de datas para mostrar os dados de uso da equipe.  

    ![Captura de tela da exibição de análise por equipe](../media/view-analytics-per-team.png)

    |Item |Descrição  |
    |--------|-------------|
    |**Resumo**   |Resumo da atividade da equipe, incluindo o seguinte:<ul><li>**Usuários**: Número total de usuários no período de tempo especificado. Isso inclui proprietários da equipe, membros da equipe e convidados.</li> <li>**Postagens**: Número de novas mensagens publicadas no chat de equipe durante o período de tempo especificado.</li><li>**Respostas : Número** de respostas no chat em equipe durante o período de tempo especificado.</li> <li>**Aplicativos**: número de aplicativos adicionados à equipe.</li><li>**Reuniões**: Número de reuniões do Teams organizadas no nível da equipe.</li> </ul> |
    |**Usuários ativos**   |Número de usuários ativos e inativos.|
    |**Função**   |Número de usuários por função, incluindo proprietários de equipe, membros da equipe e convidados.|
    |**Gráfico de usuários ativos**  |Número de ativos diários. Passe o mouse sobre o ponto em uma determinada data para ver o número de usuários ativos nessa data.|
    |**Gráfico de** mensagens  |Número total de mensagens postadas no chat da equipe por data. Passe o mouse sobre o ponto em uma determinada data para ver o número de novas postagens e respostas publicadas nessa data.|

> [!TIP]
> Você também pode exibir a análise por equipe clicando em uma equipe na lista na exibição de análise [entre equipes.](#view-cross-team-analytics)

## <a name="view-per-channel-analytics"></a>Exibir análise por canal

1. No Teams, vá para o canal que você deseja, clique em **Mais opções (...)** e clique em **Gerenciar canal.**
2. Clique na **guia** Análise.
3. Selecione um intervalo de datas para mostrar os dados de uso do canal.  

    ![Captura de tela da exibição de análise por canal](../media/view-analytics-per-channel.png)

    |Item |Descrição  |
    |--------|-------------|
    |**Resumo**   |Resumo da atividade do canal, incluindo o seguinte:<ul><li>**Usuários**: Número total de usuários no período de tempo especificado. Isso inclui proprietários da equipe, membros da equipe e convidados.</li> <li>**Postagens**: Número de novas mensagens postadas no canal durante o período de tempo especificado.</li><li>**Respostas :** Número de respostas no canal durante o período de tempo especificado.</li> <li>**Aplicativos**: número de aplicativos adicionados ao canal.</li> </ul> |
    |**Gráfico de** mensagens  |Número total de mensagens postadas no chat do canal por data. Passe o mouse sobre o ponto em uma determinada data para ver o número de novas postagens e respostas publicadas nessa data.|

> [!TIP]
> Você também pode exibir a análise por canal selecionando um canal na caixa de listagem na exibição de análise [por equipe.](#view-per-team-analytics)
    
> [!NOTE]
> Definimos usuários ativos como usuários que executam uma ação intencional no cliente da área de trabalho, no cliente móvel e no cliente Web. Exemplos de uma ação intencional incluem iniciar um chat, fazer uma chamada, compartilhar um arquivo, editar um documento em equipes, participar de uma reunião e assim por diante. Retiramos ações passivas como inicialização automática, minimizando uma tela ou fechando o aplicativo. Também eliminamos todas as ações em uma única ID de usuário.

## <a name="related-topics"></a>Tópicos relacionados

- [Exibir análises para suas equipes](https://support.office.com/article/view-analytics-for-your-teams-5b8ad4b1-af34-4217-aff4-cd11a820b56b)
- [Análises e relatórios do Teams](teams-reporting-reference.md)