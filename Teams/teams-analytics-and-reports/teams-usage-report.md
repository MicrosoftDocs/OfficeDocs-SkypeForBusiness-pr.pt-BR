---
title: Relatório de uso do Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kojika
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
  - M365-collaboration
description: Saiba como usar o relatório de uso do Teams no centro de administração do Microsoft Teams para obter uma visão geral das atividades to Teams na sua organização.
appliesto:
  - Microsoft Teams
ms.custom: seo-marvel-apr2020
---
# <a name="microsoft-teams-usage-report"></a>Relatório de uso do Microsoft Teams

O relatório de uso do Teams no centro de administração do Microsoft Teams apresenta uma visão geral da atividade de uso no Teams, incluindo o número de usuários e canais ativos, para que você possa ver rapidamente quantos usuários na sua organização estão usando o Teams para se comunicar e colaborar. Você pode visualizar as informações de uso de equipes, incluindo o número de usuários e canais ativos, convidados e mensagens em cada equipe.

## <a name="view-the-usage-report"></a>Exibir o relatório de uso

1. Na navegação à esquerda do centro de administração Microsoft Teams, clique em **Análise &** **relatóriosusuário** > . Na guia **Exibir relatórios**, em **Relatório**, selecione **Teams uso**.
2. Em **Intervalo de dados**, selecione intervalo e em seguida clique em **Executar relatório**.

    ![Captura de tela do relatório Teams de uso no centro de administração Teams com explicações explicativas.](../media/teams-reports-teams-usage-with-callouts1.png "Captura de tela do relatório de Teams de uso no centro de administração Teams com callouts")

## <a name="interpret-the-report"></a>Interpretar relatório

|Texto Explicativo |Descrição  |
|--------|-------------|
|**1**   |O Teams de atividade de uso pode ser exibido para tendências nos últimos 7, 30 ou 90 dias. |
|**2**   |Cada relatório tem uma data de geração. O relatório geralmente reflete um período de latência de atividade de 24 a 48 horas. |
|**3**   |<ul><li>O eixo X no gráfico representa o intervalo selecionado de datas para o relatório.</li> <li> O eixo Y representa a contagem dos itens ativos ou atividade.</li> </ul>Passe o mouse sobre o ponto que representa um item ou atividade em uma determinada data para ver o número de instâncias de tal item ou atividade na data determinada.|
|**4**   |Você pode filtrar o que se vê no gráfico clicando em um item na legenda. Por exemplo, clique em **Total** de usuários ativos, **Teams & canais** ativos **, canais** ativos ou **Mensagens** para ver apenas as informações relacionadas a cada um. Ao alterar esta seleção, as informações da tabela não são alteradas. |
|**5**   |A tabela oferece um detalhamento do uso por equipe. <ul><li>**Nome da** equipe é o nome de exibição da equipe. Você pode clicar no nome da equipe para ir até a página de configurações da equipe no Microsoft Teams de administração. </li> <li>**Privacidade** refere-se à equipe ser particular ou pública.</li> <li>**Usuários ativos** é o número de usuários ativos na equipe no período de tempo especificado.</li><li>**Convidados** é o número de convidados na equipe no período de tempo especificado.</li> <li>**Canais ativos** é o número de canais que têm pelo menos um usuário ativo no período especificado.</li> <li>**Post Messages** é o número de todas as mensagens de postagem em canais no período de tempo especificado.</li> <li>**Mensagens de** resposta é o número de todas as mensagens de resposta nos canais no período de tempo especificado.</li> <li>**Reuniões organizadas** é o número de reuniões agendadas e ad hoc que um usuário organizou durante o período de tempo especificado. </li><li>**Mensagens urgentes** é o número de todas as mensagens urgentes no período de tempo especificado.</li><li>**Reações** é o número de todas as reações a mensagens no período de tempo especificado.</li><li>**Menções** é o número de todas as menções usadas em mensagens no período de tempo especificado.</li><li>**Mensagens de** canal é o número de mensagens exclusivas que os usuários da equipe postaram em chats de equipe durante o período especificado.</li> </li> </ul>Observe que, se uma equipe não existir mais, o nome será exibido como "--" na tabela. <br><br>Para ver as informações desejadas na tabela, certifique-se de adicionar as colunas à tabela. |
|**6**   |Selecione **Editar colunas** para adicionar ou remover colunas na tabela.|
|**7**   |Você pode exportar o relatório para um arquivo CSV para análise offline. Clique **em Exportar para Excel** e, na guia **Downloads**, clique em **Baixar** para baixar o relatório quando estiver pronto.<br><br>![Captura de tela da guia Downloads mostrando relatórios exportados para download.](../media/teams-reports-export-to-csv.png)|
|**8** |Os pontos de dados da série de tempo no gráfico mostram diferentes métricas de uso agregadas no locatário|
|**9** |Os dados tabular representam diferentes métricas de uso agregadas por equipe|

[!INCLUDE [teams-reports-definitions](../includes/teams-reports-definitions.md)]

## <a name="related-topics"></a>Tópicos relacionados

- [Análises e relatórios do Teams](teams-reporting-reference.md)
