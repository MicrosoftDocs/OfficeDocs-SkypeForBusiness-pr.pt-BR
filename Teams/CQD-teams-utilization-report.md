---
title: Exibir Microsoft Teams utilização em Power BI usando dados CQD
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
ms.localizationpriority: medium
description: Use os Teams relatórios de utilização Power BI para acessar Microsoft Teams dados do CQD (Painel de Qualidade de Chamada) para rastrear Microsoft Teams uso em sua organização.
ms.openlocfilehash: 5e569385da9a7014d1f62c2b45aed63f6eeb6364
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725470"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>Exibir Microsoft Teams utilização em Power BI usando dados CQD

Novo em março de 2020, adicionamos um relatório de utilização Teams para nossos modelos de consulta Power BI download para [CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 

Esse novo Teams relatórios de utilização permite que você veja como (e quanto) seus usuários estão usando Microsoft Teams acessando dados do CQD (Painel de Qualidade de Chamada) Teams chamada. Esses relatórios se destinam a ser um local centralizado que tanto administradores quanto líderes de negócios podem ir rapidamente para esses dados.

O Teams relatório de utilização Power BI consiste em dois relatórios **[principais:](#call-count-summary-report)** Resumo da Contagem de Chamada e **[Resumo de Minutos de Áudio.](#audio-minutes-summary-report)** Os [relatórios Uso](#daily-usage)Diário, Detalhes [](#user-list) de Áudio [Regionais,](#regional-audio-details)Detalhes da Conferência e Lista de Usuários são lançados quando um usuário tira proveito dos relatórios de detalhamento, notados nas descrições abaixo. [](#conference-details)

> [!NOTE]
> Os dados de construção e sub-rede devem ser preenchidos para fornecer recursos regionais e de filtragem de rede.

## <a name="call-count-summary-report"></a>Relatório de Resumo da Contagem de Chamada

A página principal (Resumo da Contagem de Chamada) fornece imediatamente o número de sessões de compartilhamento de áudio, vídeo e tela nos últimos 30 e 90 dias, conforme o título da seção. Os dados inicialmente exibidos são para a organização como um todo e podem ser filtrados usando as opções de menu suspenso da slicer no lado esquerdo da página.

![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report1.png)

1. À direita dos menus suspensos da slicer, o número de chamadas por tipo de mídia é dividido para uma exibição interna/externa nos últimos trinta dias. Podemos ver pela captura de tela acima que há mais chamadas acontecendo de locais organizacionais externos, o que faz sentido considerando o ambiente global atual.
  ![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report2.png)

1. À direita da caixa de contagem de tipos de mídia, temos a Contagem de Chamada Mensal por Tipo de Mídia dos últimos 90 dias. Cada coluna e tipo de mídia podem ser passados para exibir a contagem de um mês anterior ou o mês atual até a data, fornecendo informações de tendência de uso.
  ![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report3.png)
 

1. O gráfico do meio funciona como o gráfico de 90 dias, no entanto, fornece uma exibição de uso diária para os últimos 30 dias e permite que o usuário clique com o botão direito do mouse e faça uma análise de detalhes para um dia específico.
  ![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report4.png)

Na seção inferior esquerda da página, você encontrará uma tabela fornecendo valores totais para cada tipo de mídia no ano passado. 
    ![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report5.png)
    ![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report6.png)   

À direita da tabela, um gráfico de barras mostra clientes com mais uso (chamadas/fluxos) dos últimos 30 dias.
   ![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report7.png)

O último conjunto de gráficos desta página mostra cada tipo de mídia individualmente, com uma divisão mostrando conferência e uso P2P. Os gráficos abaixo mostram que há um número significativamente maior de uso de conferência em comparação com P2P.
  ![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>Relatório de Resumo de Minutos de Áudio

No relatório de uso de Minutos de Áudio, o uso total de minutos é fornecido por meio de algumas exibições diferentes. 

Temos o resumo de uso de trinta dias mostrado ao lado das slicers como fácil de consumir caixas de texto. O número superior mostra o total de trinta dias, com quebras internas e externas abaixo disso.

![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report9.png)

O gráfico da barra superior direita fornece uma exibição de longo período do uso de áudio de conferência. Passe o mouse durante o mês para mostrar os minutos de áudio da conferência.

Para mostrar a diferença no áudio de conferência e P2P, o gráfico inferior esquerdo pega todo o áudio do último ano e o divide entre os dois tipos.

![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report10.png)

O último gráfico da página Minutos de áudio mostra o uso de minutos de áudio em uma sobreposição global de mapa. Esse gráfico só funcionará se os dados de construção e sub-rede são carregados para o locatário. A sobreposição do gráfico de pizza no mapa pode ser furada, fornecendo posteriormente o uso de áudio regional.

![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>Recursos de drill-through

Conforme mencionado anteriormente, os usuários podem detalhar os relatórios de uso diários e regionais.

### <a name="daily-usage"></a>Uso Diário

O relatório uso diário permite que um administrador identifique os períodos de pico de consumo ao longo de um dia. Além do uso, também podemos capturar o sentimento geral do usuário e os comentários desse dia.

![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report12.png)

O relatório de uso diário exibe o número de compartilhamentos de Áudio, Vídeo e Tela do dia selecionado com a capacidade de diferenciar entre conectividade interna e externa. Uma divisão De Conferência e Ponto a Ponto é à direita imediata da caixa total da modalidade. O canto superior direito do relatório fornece uma lista de conferências com sua ID e participantes associados para o dia. A lista de conferências também fornece uma análise adicional para o relatório de Detalhes da Conferência. SUBSTITUIR GRÁFICO

![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report13.png)

O gráfico de barras na área central permite que o usuário identifique os períodos de pico de consumo ao longo de um dia. Os usuários podem detalhar a hora representada no gráfico que apresentará o relatório de Lista de Usuários por hora.

À direita do gráfico de barras, o Feedback do Usuário é apresentado em um formato visual. Embora o sentimento do usuário possa ser subjetivo, ele fornece informações que podem ser usadas para identificar possíveis problemas.

A tabela inferior fornece um intervalo de métricas para o dia. Porcentagens ruins, juntamente com as taxas de falha, podem fornecer a um administrador áreas de melhoria em potencial. Cada hora também pode ser selecionada individualmente, conforme mostrado abaixo.

Esses dados podem ser usados para identificar regiões com problemas durante os horários de pico de consumo.


Clique na coluna desse dia para exibir métricas para essa hora.
![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report14.png)
  
  1.  A tabela abaixo do gráfico exibirá as métricas dessa hora. Isso pode ser organizado por qualquer header de coluna; no entanto, estamos interessados em encontrar áreas problemáticas.  
    ![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report15.png)
    
  2.  Vemos que a região do IND está enfrentando um desempenho de vídeo ruim em conferências durante esse período. Subsequentemente, os relatórios da Microsoft CQD QER podem ser usados para restringir o local problemático à medida que a região e o período de tempo foram identificados.

### <a name="conference-details"></a>Detalhes da conferência

O relatório Detalhes da Conferência fornece informações adicionais para reuniões, de uma lista de participantes, aos tipos de mídia usados durante a sessão.

Clique com o botão direito do mouse em uma conferência na barra de participantes no gráfico de ID da conferência na página uso diário para detalhar os detalhes da conferência.

![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report24.png)

![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report25.png)
  

Podemos ver os participantes da conferência, bem como todas as informações pertinentes para perda de pacotes e tremência para ajudar com possíveis esforços de solução de problemas na tabela inferior.

![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>Detalhes regionais de áudio

A pesquisa detalhes de áudio regionais mostra especificamente o uso de minutos de áudio para a região selecionada. Os usuários com acesso ao CQD podem ver tendências de uso para P2P e áudio de conferência dentro da região selecionada.

1.  Na página Resumo da Contagem de Chamada, faça uma análise de como região específica através da tabela.
  ![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report16.png)

2.  Selecione a linha com as informações adicionais da região necessárias.
  ![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report17.png)

3.  As tendências de dados mostram um número significativo de minutos sendo usados na rede interna, com a conferência superando muito o uso de P2P.
  ![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report18.png)

A tendência de áudio regional pode ser usada para mostrar como os usuários são afetados por influências externas no mundo. Especificamente, no momento, esperamos ver o uso externo para as regiões EMEA e APAC aumentarem com as pessoas sendo solicitados a trabalhar remotamente.


### <a name="user-list"></a>Lista de usuários

A sonda de lista de usuários fornece, como se pode esperar, informações específicas do usuário para uma hora específica selecionada pela pessoa que está exibindo o relatório. O relatório de Lista de Usuários é acessível por meio de uma pesquisa no gráfico Tendências por Hora no relatório de Uso Diário. Clique com o botão direito do mouse na hora para as informações adicionais necessárias e selecione Drill through e User List, conforme mostrado abaixo.

![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report19.png)

O relatório de Lista de Usuários mostra conectividade interna/externa por meio do gráfico de rosca no centro superior da página. Podemos ver que há uma grande participação de Fora da rede corporativa na imagem abaixo.

A parte superior direita do gráfico mostra o número de chamadas feitas por cada usuário dentro dessa hora.

![Captura de tela: Teams relatórios de utilização.](media/CQD-teams-utilization-report20.png)

A tabela inferior fornece informações detalhadas para as sessões em que cada usuário participou durante essa hora. A coluna Tipo de Falha é útil para determinar o que causou a queda de uma chamada. As colunas Capture e Render Device são úteis para identificar por que uma chamada foi relatada com baixa qualidade.


## <a name="related-topics"></a>Tópicos relacionados

[Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no painel de qualidade da chamada](stream-classification-in-call-quality-dashboard.md)

[Configurar a Análise de Chamada do Skype for Business](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análise de Chamada e Painel de Qualidade de Chamadas](./monitor-call-quality-qos.md)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
