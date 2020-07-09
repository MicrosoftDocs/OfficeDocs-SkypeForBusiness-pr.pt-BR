---
title: Exibir a utilização do Microsoft Teams no Power BI usando dados do CQD
ms.author: lolaj
author: LolaJacobsen
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
description: Use os relatórios do Power BI de utilização do teams para acessar os dados do Microsoft Teams Call Quality Dashboard (CQD) para acompanhar o uso do Microsoft Teams em sua organização.
ms.openlocfilehash: bd1a95a683da881a78acb5d4849bba0ac55f4898
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085577"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a>Exibir a utilização do Microsoft Teams no Power BI usando dados do CQD

Novidades de março de 2020, adicionamos um relatório de utilização do teams aos nossos [modelos de consulta para o Power bi](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)que podem ser baixados para CQD. 

Esta nova equipe de relatórios de utilização permite que você veja como (e quanto) os usuários estão usando o Microsoft Teams acessando os dados do painel de qualidade de chamada do Teams (CQD). Esses relatórios destinam-se a serem um local centralizado que os administradores e líderes de negócios possam acessar rapidamente para esses dados.

O relatório do Power BI de utilização do teams consiste em dois relatórios principais: Resumo da **[contagem de chamadas](#call-count-summary-report)** e Resumo de **[minutos de áudio](#audio-minutes-summary-report)**. O [uso diário](#daily-usage), [os detalhes de áudio regional](#regional-audio-details), os [detalhes da conferência](#conference-details) e os relatórios da lista de [usuários](#user-list) entram em cena quando um usuário aproveita os relatórios detalhados, observados nas descrições abaixo.

> [!NOTE]
> Os dados de criação e de sub-rede devem ser preenchidos para fornecer recursos regionais e de filtragem de rede.

## <a name="call-count-summary-report"></a>Relatório de Resumo de contagem de chamadas

A página principal (Resumo da contagem de chamadas) fornece imediatamente o número de sessões de áudio, vídeo e compartilhamento de tela nos últimos 30 e 90 dias, conforme observado no título da seção. Os dados inicialmente exibidos são para a organização como um todo e podem ser filtrados usando as opções suspensas de segmentação de dados no lado esquerdo da página.

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report1.png)

1. À direita das listas suspensas de segmentação de texto, o número de chamadas por tipo de mídia é dividido em uma exibição interna/externa durante os últimos 30 dias. Podemos ver na captura de tela acima que há mais chamadas em locais organizacionais externos, o que faz sentido considerar o ambiente global atual.
  ![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report2.png)

1. À direita da caixa de contagem de tipo de mídia, temos a contagem de chamadas mensal por tipo de mídia para os últimos 90 dias. Cada tipo de coluna e mídia pode ser focalizado para exibir a contagem de um mês anterior ou o mês atual até o momento, fornecendo informações de tendência de uso.
  ![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report3.png)
 

1. O gráfico central funciona como o gráfico de 90 dias, mas fornece um modo de exibição de uso diário dos últimos 30 dias e permite que um usuário clique com o botão direito do mouse e faça drill down nos detalhes de um dia específico.
  ![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report4.png)

Na seção inferior esquerda da página, você encontrará uma tabela que fornece os valores totais para cada tipo de mídia no ano passado. 
    ![Captura de tela: relatórios de utilização do teams ](media/CQD-teams-utilization-report5.png) ![ : relatórios de utilização do teams](media/CQD-teams-utilization-report6.png)   

À direita da tabela, um gráfico de barras mostra os clientes com o maior uso (chamadas/fluxos) dos últimos 30 dias.
   ![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report7.png)

O último conjunto de gráficos para esta página mostra cada tipo de mídia individualmente, com uma divisão que mostra o uso de conferência e P2P. Os gráficos abaixo mostram que há um número de uso de conferência significativamente maior se comparado ao P2P.
  ![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report8.png)

## <a name="audio-minutes-summary-report"></a>Relatório de Resumo de minutos de áudio

No relatório de uso de minutos de áudio, o uso total de minutos é fornecido por meio de alguns modos de exibição diferentes. 

Temos o resumo de uso de 30 dias mostrado ao lado da segmentação de texto como fácil de consumir caixas de texto. O número superior mostra o total de 30 dias, com divisões internas e externas abaixo delas.

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report9.png)

O gráfico de barras superior direita fornece uma exibição yearlong do uso de áudio da conferência. Passe o mouse sobre o mês para mostrar os minutos de áudio da conferência.

Para mostrar a diferença no P2P e no áudio da conferência, o gráfico inferior esquerdo assume todo o áudio do ano anterior e o divide entre os dois tipos.

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report10.png)

O último gráfico da página minutos de áudio mostra o uso de minutos de áudio em uma sobreposição de mapa global. Este gráfico só funcionará se os dados de criação e de sub-rede forem carregados no locatário. A sobreposição de gráfico de pizza no mapa pode ser analisada, subsequentemente fornecendo o uso de áudio regional.

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a>Recursos de Drill-through

Conforme observado anteriormente, os usuários podem analisar os relatórios de uso diários e regionais.

### <a name="daily-usage"></a>Uso diário

O relatório de uso diário permite que um administrador identifique os períodos de pico do consumo durante um dia. Além do uso, também podemos capturar comentários gerais sobre o usuário e comentários sobre esse dia.

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report12.png)

O relatório de uso diário exibe a quantidade de recursos de áudio, vídeo e de tela do dia selecionado com a capacidade adicional de diferenciar entre conectividade interna e externa. Uma divisão de conferência e ponto a ponto para ponto imediatamente à direita da caixa de total de modalidade. O canto superior direito do relatório fornece uma lista de conferências com a identificação e os participantes associados do dia. A lista de conferências também fornece um detalhamento adicional para o relatório de detalhes da conferência. SUBSTITUIR GRÁFICO

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report13.png)

O gráfico de barras na área central permite que o usuário identifique os períodos de pico de consumo durante um dia. Os usuários podem fazer buscas detalhadas na hora representada no gráfico, que apresentará o relatório da lista de usuários da hora.

À direita do gráfico de barras, o feedback do usuário é apresentado em um formato visual. Embora os problemas do usuário possam ser subjetivos, ele fornece informações que podem ser usadas para identificar possíveis problemas.

A tabela inferior fornece um intervalo de métricas para o dia. Porcentagens insatisfatórias juntamente com as tarifas de falha podem oferecer aos administradores possíveis áreas de melhoria. Cada hora também pode ser selecionada individualmente, como mostrado a seguir.

Esses dados podem ser usados para identificar regiões com problemas durante os períodos de pico de consumo.


Clique na coluna desse dia para exibir as métricas dessa hora.
![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report14.png)
  
  1.  A tabela abaixo do gráfico mostrará as métricas dessa hora. Isso pode ser classificado por qualquer cabeçalho de coluna; no entanto, ficamos interessados em encontrar áreas problemáticas.  
    ![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report15.png)
    
  2.  Vemos que a região IND está apresentando um desempenho de vídeo ruim em conferências durante este período. Subsequentemente, os relatórios do CQD QER da Microsoft podem ser usados para restringir o local problemático, pois o período de região e de tempo foi identificado.

### <a name="conference-details"></a>Detalhes da conferência

O relatório de detalhes da conferência fornece informações adicionais para reuniões, a partir de uma lista de participantes, para os tipos de mídia usados durante a sessão.

Clique com o botão direito do mouse em uma conferência na barra de participantes na página de uso diário para fazer uma busca detalhada nos detalhes da conferência.

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report24.png)

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report25.png)
  

Podemos ver os participantes da conferência, bem como todas as informações pertinentes à perda de pacotes e à tremulação, para auxiliar com possíveis esforços de solução de problemas na tabela inferior.

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a>Detalhes de áudio regional

O detalhamento de dados de áudio regional mostra especificamente o uso de minutos de áudio para a região selecionada. Os usuários com acesso a CQD podem ver tendências de uso para áudio P2P e de conferência dentro da região selecionada.

1.  Na página de Resumo de contagem de chamadas, faça drill-through como região específica na tabela.
  ![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report16.png)

2.  Selecione a linha com a região à qual informações adicionais são necessárias.
  ![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report17.png)

3.  As tendências de dados mostram um número significativo de minutos sendo usados na rede interna, com a conferência que supera o uso ponto a ponto.
  ![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report18.png)

A tendência de áudio regional pode ser usada para mostrar como os usuários são afetados por influências externas do mundo. Especificamente, no momento, esperamos ver o uso externo das regiões da EMEA e da Ásia-Pacífico para aumentar com as pessoas sendo solicitadas a trabalhar remotamente.


### <a name="user-list"></a>Lista de usuários

A lista suspensa de lista de usuários fornece, como pode esperar, informações específicas do usuário para uma hora específica selecionada pela pessoa que está visualizando o relatório. O relatório lista de usuários pode ser acessado por meio de uma busca detalhada no gráfico de tendências horárias no relatório de uso diário. Clique com o botão direito do mouse na hora de informações adicionais são necessárias e selecione Drill through e lista de usuários, conforme mostrado a seguir.

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report19.png)

O relatório lista de usuários mostra conectividade interna/externa por meio do gráfico de rosca na parte central superior da página. Podemos ver que há uma grande quantidade de participação de fora da rede corporativa na imagem abaixo.

O canto superior direito do gráfico mostra o número de chamadas feitas por cada usuário dentro dessa hora.

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report20.png)

A tabela inferior fornece informações detalhadas para as sessões que cada usuário participou durante essa hora. A coluna tipo de falha é útil para determinar o que causou uma chamada para soltar. As colunas capturar e renderizar dispositivos são úteis para identificar o motivo pelo qual uma chamada foi reportada com má qualidade.


## <a name="related-topics"></a>Tópicos relacionados

[Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no painel de qualidade da chamada](stream-classification-in-call-quality-dashboard.md)

[Configurar a Análise de Chamada do Skype for Business](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análise de Chamada e Painel de Qualidade de Chamadas](difference-between-call-analytics-and-call-quality-dashboard.md)

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
 