---
title: Exibir o uso do Microsoft Teams no Power BI usando dados CQD
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Use os relatórios do Power BI de Uso do Teams para acessar dados do CQD (Painel de Qualidade de Chamada) do Microsoft Teams para controlar o uso do Microsoft Teams em sua organização.
ms.openlocfilehash: bda89f3715997016e6c1bea242dcf6b8b182c6bf
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581542"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>Exibir o uso do Microsoft Teams no Power BI usando dados CQD

Novo em março de 2020, adicionamos um relatório de Uso do Teams aos nossos modelos de consulta do Power BI para [download para CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) 

Esses novos relatórios de Uso do Teams permitem que você veja como (e quanto) seus usuários estão usando o Microsoft Teams acessando dados do Painel de Qualidade de Chamada do Teams (CQD). Esses relatórios destinam-se a ser um local centralizado que tanto os administradores quanto os líderes de negócios podem ir rapidamente para esses dados.

O relatório do Power BI de Uso do Teams consiste em dois relatórios principais: Resumo da Contagem de Chamada **[e](#call-count-summary-report)** Resumo **[de Minutos de Áudio.](#audio-minutes-summary-report)** Os [relatórios Uso Diário,](#daily-usage)Detalhes [](#user-list) de [Áudio Regional,](#regional-audio-details)Detalhes de Conferência e Lista de Usuários são lançados quando um usuário tira proveito dos relatórios de drill down, que estão nas descrições abaixo. [](#conference-details)

> [!NOTE]
> Os dados de construção e sub-rede devem ser preenchidos para fornecer recursos regionais e de filtragem de rede.

## <a name="call-count-summary-report"></a>Relatório de Resumo da Contagem de Chamada

A página principal (Resumo da Contagem de Chamada) fornece imediatamente o número de sessões de áudio, vídeo e compartilhamento de tela dos últimos 30 e 90 dias, conforme o título da seção. Os dados exibidos inicialmente são para a organização como um todo e podem ser filtrados usando as opções de menu suspenso da slicer no lado esquerdo da página.

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report1.png)

1. À direita dos menus suspensos da slicer, o número de chamadas por tipo de mídia é dividido em uma exibição interna/externa nos últimos 30 dias. Podemos ver através da captura de tela acima que há mais chamadas acontecendo de locais organizacionais externos, o que faz sentido considerando o ambiente global atual.
  ![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report2.png)

1. À direita da caixa de contagem de tipos de mídia, temos a Contagem Mensal de Chamada por Tipo de Mídia dos últimos 90 dias. Cada tipo de coluna e mídia pode ser passado o mouse sobre para exibir a contagem de um mês anterior ou o mês atual até a data, fornecendo informações de tendência de uso.
  ![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report3.png)
 

1. O gráfico intermediário funciona como o gráfico de 90 dias, no entanto, ele fornece uma exibição de uso diário dos últimos 30 dias e permite que um usuário clique com o botão direito do mouse e faça uma busca drill down nos detalhes de um dia específico.
  ![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report4.png)

Na seção inferior esquerda da página, você encontrará uma tabela que fornece valores totais para cada tipo de mídia no ano passado. 
    ![Captura de tela: Captura de tela relatórios de uso ](media/CQD-teams-utilization-report5.png) ![ do Teams: Relatórios de uso do Teams](media/CQD-teams-utilization-report6.png)   

À direita da tabela, um gráfico de barras mostra os clientes com mais uso (chamadas/fluxos) dos últimos 30 dias.
   ![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report7.png)

O último conjunto de gráficos desta página mostra cada tipo de mídia individualmente, com uma divisão mostrando o uso de conferência e P2P. Os gráficos a seguir mostram que há um número significativamente maior de uso de conferência em comparação com P2P.
  ![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>Relatório de Resumo de Minutos de Áudio

No relatório de uso de Minutos de Áudio, o uso total de minutos é fornecido por meio de algumas exibições diferentes. 

Temos o resumo de uso de 30 dias mostrado ao lado das slicers como fácil de consumir caixas de texto. O número superior mostra o total de 30 dias, com detalhamentos internos e externos abaixo disso.

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report9.png)

O gráfico de barras superior direita fornece uma exibição anual do uso de áudio de conferência. Passe o mouse sobre o mês para mostrar os minutos de áudio da conferência.

Para mostrar a diferença no áudio de conferência e P2P, o gráfico inferior esquerdo leva todo o áudio do ano passado e divide-o entre os dois tipos.

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report10.png)

O último gráfico da página Minutos de áudio mostra o uso de minutos de áudio em uma sobreposição global de mapa. Esse gráfico só funcionará se dados de construção e sub-rede são carregados para o locatário. A sobreposição do gráfico de pizza no mapa pode ser detalhada, fornecendo posteriormente o uso de áudio regional.

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>Recursos de drill-through

Conforme mencionado anteriormente, os usuários podem detalhar os relatórios de uso diário e regional.

### <a name="daily-usage"></a>Uso Diário

O relatório Uso Diário permite que um administrador identifique períodos de pico de consumo durante um dia. Além do uso, também podemos capturar o sentimento geral do usuário e os comentários desse dia.

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report12.png)

O relatório de uso diário exibe o número de compartilhamentos de Áudio, Vídeo e Tela do dia selecionado com a capacidade de diferenciar conectividade interna e externa. Uma divisão de Conferência e Ponto a Ponto está à direita imediata da caixa de total de modalidades. O canto superior direito do relatório fornece uma lista de conferências com sua ID associada e os participantes do dia. A lista de conferências fornece um drill down adicional para o relatório Detalhes da Conferência também. SUBSTITUIR GRÁFICO

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report13.png)

O gráfico de barras na área central permite que o usuário identifique os períodos de pico de consumo durante um dia. Os usuários podem fazer drill down na hora representada no gráfico que apresentará o relatório da Lista de Usuários por hora.

À direita do gráfico de barras, os Comentários do Usuário são apresentados em um formato visual. Embora o sentimentos do usuário possa ser subjetivo, ele fornece informações que podem ser usadas para identificar possíveis problemas.

A tabela inferior fornece um intervalo de métricas para o dia. Porcentagens ruins juntamente com taxas de falha podem fornecer ao administrador áreas potenciais de melhoria. Cada hora também pode ser selecionada individualmente, conforme mostrado abaixo.

Esses dados podem ser usados para identificar regiões com problemas durante os períodos de consumo máximo.


Clique na coluna desse dia para exibir as métricas dessa hora.
![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report14.png)
  
  1.  A tabela abaixo do gráfico exibirá as métricas para essa hora. Isso pode ser classificação por qualquer header de coluna; no entanto, teríamos interesse em encontrar áreas problemáticas.  
    ![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report15.png)
    
  2.  Vemos que a região IND está enfrentando um desempenho de vídeo ruim em conferências durante esse período. Posteriormente, os relatórios CQD QER Microsoft podem ser usados para restringir o local problemático à medida que a região e o período de tempo foram identificados.

### <a name="conference-details"></a>Detalhes da Conferência

O relatório Detalhes da Conferência fornece informações adicionais para reuniões, desde uma lista de participantes até os tipos de mídia usados durante a sessão.

Clique com o botão direito do mouse em uma conferência na barra de participantes no gráfico de ID de conferência na página Uso diário para detalhar os detalhes da conferência.

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report24.png)

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report25.png)
  

Podemos ver os participantes da conferência, bem como todas as informações pertinentes até a perda de pacotes e tremidação para ajudar com possíveis esforços de solução de problemas na tabela inferior.

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>Detalhes regionais do áudio

A busca de Detalhes Regionais do Áudio mostra especificamente o uso de minutos de áudio para a região selecionada. Os usuários com acesso ao CQD podem ver tendências de uso para P2P e áudio de conferência dentro da região selecionada.

1.  Na página Resumo da Contagem de Chamada, faça drill-through para uma região específica na tabela.
  ![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report16.png)

2.  Selecione a linha com as informações adicionais de região necessárias.
  ![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report17.png)

3.  As tendências de dados mostram um número significativo de minutos sendo usados na rede interna, com a conferência superando o uso de P2P.
  ![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report18.png)

A tendência de áudio regional pode ser usada para mostrar como os usuários são afetados por influencias externas no mundo. Especificamente, no momento, esperamos ver o uso externo para as regiões emEA e APAC aumentarem, com as pessoas sendo convidadas a trabalhar remotamente.


### <a name="user-list"></a>Lista de Usuários

O drill down da Lista de Usuários fornece, como se espera, informações específicas do usuário para uma hora específica selecionada pela pessoa que está exibindo o relatório. O relatório lista de usuários pode ser acessado por meio de uma análise do gráfico De tendências por hora no relatório Uso Diário. Clique com o botão direito do mouse nas informações adicionais de hora necessárias e selecione Drill through e Lista de Usuários, conforme mostrado abaixo.

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report19.png)

O relatório lista de usuários mostra conectividade interna/externa por meio do gráfico de rosca na parte superior central da página. Podemos ver que há uma grande quantidade de participação de Fora da rede corporativa na imagem abaixo.

O canto superior direito do gráfico mostra o número de chamadas feitas por cada usuário dentro dessa hora.

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report20.png)

A tabela inferior fornece informações detalhadas para as sessões em que cada usuário participou durante essa hora. A coluna Tipo de Falha é útil para determinar o que causou a queda de uma chamada. As colunas Capturar e Renderizar Dispositivo são úteis para identificar por que uma chamada foi relatada com baixa qualidade.


## <a name="related-topics"></a>Tópicos relacionados

[Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no painel de qualidade da chamada](stream-classification-in-call-quality-dashboard.md)

[Configurar a Análise de Chamada do Skype for Business](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análise de Chamada e Painel de Qualidade de Chamadas](difference-between-call-analytics-and-call-quality-dashboard.md)

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
 