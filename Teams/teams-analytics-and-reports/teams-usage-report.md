---
title: Relatório de uso do Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como usar o relatório de uso do Teams no centro de administração do Microsoft Teams para obter uma visão geral das atividades to Teams na sua organização.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 993c1b124737a0f335e9c9b1e720af72fcc88a8e
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122251"
---
# <a name="microsoft-teams-usage-report"></a>Relatório de uso do Microsoft Teams

O relatório de uso do Teams no centro de administração do Microsoft Teams apresenta uma visão geral da atividade de uso no Teams, incluindo o número de usuários e canais ativos, para que você possa ver rapidamente quantos usuários na sua organização estão usando o Teams para se comunicar e colaborar. Você pode visualizar as informações de uso de equipes, incluindo o número de usuários e canais ativos, convidados e mensagens em cada equipe.

## <a name="view-the-usage-report"></a>Exibir o relatório de uso

1. Na navegação à esquerda do centro de administração Microsoft Teams, clique **em Análise & relatórios** de  >  **uso.** Na guia **Exibir relatórios,** em **Relatório,** selecione **Teams uso**.
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

    ![Captura de tela do relatório de Teams de uso no centro de administração Teams com callouts](../media/teams-reports-teams-usage-with-callouts.png "Captura de tela do relatório de Teams de uso no centro de administração Teams com callouts")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O Teams de atividade de uso pode ser exibido para tendências nos últimos 7 dias, 30 ou 90 dias. |
|**2**   |Cada relatório tem uma data de geração. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |<ul><li>O eixo X no gráfico representa o intervalo selecionado de datas para o relatório.</li> <li> O eixo Y representa a contagem dos itens ativos ou atividade.</li> </ul>Passe o mouse sobre o ponto que representa um item ou atividade em uma determinada data para ver o número de instâncias de tal item ou atividade na data determinada.|
|**4**   |Você pode filtrar o que se vê no gráfico clicando em um item na legenda. Por exemplo, clique em **Total** de usuários ativos, Teams &  **canais** ativos, canais ativos ou Mensagens para ver apenas as informações relacionadas a cada um. Ao alterar esta seleção, as informações da tabela não são alteradas. |
|**5**   |A tabela oferece um detalhamento do uso por equipe. <ul><li>**Nome da** equipe é o nome de exibição da equipe. Você pode clicar no nome da equipe para ir até a página de configurações da equipe no Microsoft Teams de administração. </li> <li>**Privacidade** refere-se à equipe ser particular ou pública.</li> <li>**Usuários ativos** é o número de usuários ativos na equipe no período de tempo especificado.</li><li>**Convidados** é o número de convidados na equipe no período de tempo especificado.</li> <li>**Canais ativos** é o número de canais que têm pelo menos um usuário ativo no período especificado.</li> <li>**Post Messages** é o número de todas as mensagens de postagem em canais no período de tempo especificado.</li> <li>**Mensagens de** resposta é o número de todas as mensagens de resposta nos canais no período de tempo especificado.</li> <li>**Reuniões organizadas** é o número de reuniões agendadas e ad hoc que um usuário organizou durante o período de tempo especificado. </li><li>**Mensagens urgentes** é o número de todas as mensagens urgentes no período de tempo especificado.</li><li>**Reações** é o número de todas as reações a mensagens no período de tempo especificado.</li><li>**Menções** é o número de todas as menções usadas em mensagens no período de tempo especificado.</li><li>**Mensagens de** canal é o número de mensagens exclusivas que os usuários da equipe postaram em chats de equipe durante o período especificado.</li> </li> </ul>Observe que, se uma conta de usuário não existir mais no Azure AD, o nome de usuário será exibido como "--" na tabela. <br><br>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.|
|**7**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique **em Exportar para Excel** e, na guia **Downloads,** clique em **Baixar** para baixar o relatório quando estiver pronto.<br><br>![Captura de tela da guia Downloads mostrando relatórios exportados para download](../media/teams-reports-export-to-csv.png)|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
