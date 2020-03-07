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
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Use os relatórios do Power BI de utilização do teams para acompanhar o uso do Microsoft Teams em sua organização.
ms.openlocfilehash: d22f37bb230ecbaa3cf6c33c2ba43f5ea92afaad
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559357"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="969a1-103">Exibir a utilização do Microsoft Teams no Power BI usando dados do CQD</span><span class="sxs-lookup"><span data-stu-id="969a1-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="969a1-104">Novidades de março de 2020, adicionamos um relatório de utilização do teams aos nossos [modelos de consulta para o Power bi](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)que podem ser baixados para CQD.</span><span class="sxs-lookup"><span data-stu-id="969a1-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="969a1-105">Esta nova equipe de relatórios de utilização permite que você veja como (e quanto) os usuários estão usando o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="969a1-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams.</span></span> <span data-ttu-id="969a1-106">Esses relatórios destinam-se a serem um local centralizado que os administradores e líderes de negócios possam acessar rapidamente para esses dados.</span><span class="sxs-lookup"><span data-stu-id="969a1-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="969a1-107">O relatório do Power BI de utilização do teams consiste em dois relatórios principais: Resumo da **[contagem de chamadas](#call-count-summary-report)** e Resumo de **[minutos de áudio](#audio-minutes-summary-report)**.</span><span class="sxs-lookup"><span data-stu-id="969a1-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="969a1-108">Os relatórios de [detalhes de áudio regional](#regional-audio-details) e de [uso diário](#daily-usage) entram em cena quando um usuário aproveita os relatórios detalhados, observados nas descrições abaixo.</span><span class="sxs-lookup"><span data-stu-id="969a1-108">The [Daily Usage](#daily-usage) and [Regional Audio Details](#regional-audio-details) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="969a1-109">Os dados de criação e de sub-rede devem ser preenchidos para fornecer recursos regionais e de filtragem de rede.</span><span class="sxs-lookup"><span data-stu-id="969a1-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="969a1-110">Relatório de Resumo de contagem de chamadas</span><span class="sxs-lookup"><span data-stu-id="969a1-110">Call Count Summary Report</span></span>

<span data-ttu-id="969a1-111">A página principal (Resumo da contagem de chamadas) fornece imediatamente o número de sessões de áudio, vídeo e compartilhamento de tela nos últimos 30 e 90 dias, conforme observado no título da seção.</span><span class="sxs-lookup"><span data-stu-id="969a1-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="969a1-112">Os dados inicialmente exibidos são para a organização como um todo e podem ser filtrados usando as opções suspensas de segmentação de dados no lado esquerdo da página.</span><span class="sxs-lookup"><span data-stu-id="969a1-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="969a1-114">À direita das listas suspensas de segmentação de texto, o número de chamadas por tipo de mídia é dividido em uma exibição interna/externa durante os últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="969a1-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="969a1-115">Podemos ver na captura de tela acima que há mais chamadas em locais organizacionais externos, o que faz sentido considerar o ambiente global atual.</span><span class="sxs-lookup"><span data-stu-id="969a1-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="969a1-116">![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="969a1-116">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="969a1-117">À direita da caixa de contagem de tipo de mídia, temos a contagem de chamadas mensal por tipo de mídia para os últimos 90 dias.</span><span class="sxs-lookup"><span data-stu-id="969a1-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="969a1-118">Cada tipo de coluna e mídia pode ser focalizado para exibir a contagem de um mês anterior ou o mês atual até o momento, fornecendo informações de tendência de uso.</span><span class="sxs-lookup"><span data-stu-id="969a1-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="969a1-119">![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="969a1-119">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report3.png)</span></span>

1. <span data-ttu-id="969a1-120">O gráfico central funciona como o gráfico de 90 dias, mas fornece um modo de exibição de uso diário dos últimos 30 dias e permite que um usuário clique com o botão direito do mouse e faça drill down nos detalhes de um dia específico.</span><span class="sxs-lookup"><span data-stu-id="969a1-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="969a1-121">![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="969a1-121">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="969a1-122">Na seção inferior esquerda da página, você encontrará uma tabela que fornece os valores totais para cada tipo de mídia no ano passado.</span><span class="sxs-lookup"><span data-stu-id="969a1-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="969a1-123">![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report5.png)</span><span class="sxs-lookup"><span data-stu-id="969a1-123">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report5.png)</span></span>
  
<span data-ttu-id="969a1-124">A tabela também tem um detalhamento disponível onde você pode ver uma divisão de dados regionais.</span><span class="sxs-lookup"><span data-stu-id="969a1-124">The table also has an available drill down where you can see a regional data breakdown.</span></span>
    <span data-ttu-id="969a1-125">![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="969a1-125">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report6.png)</span></span>

<span data-ttu-id="969a1-126">À direita da tabela, um gráfico de barras mostra os clientes com o maior uso (chamadas/fluxos) dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="969a1-126">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="969a1-127">![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="969a1-127">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report7.png)</span></span>


<span data-ttu-id="969a1-128">O último conjunto de gráficos para esta página mostra cada tipo de mídia individualmente, com uma divisão que mostra o uso de conferência e P2P.</span><span class="sxs-lookup"><span data-stu-id="969a1-128">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="969a1-129">Os gráficos abaixo mostram que há um número de uso de conferência significativamente maior se comparado ao P2P.</span><span class="sxs-lookup"><span data-stu-id="969a1-129">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="969a1-130">![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="969a1-130">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="969a1-131">Relatório de Resumo de minutos de áudio</span><span class="sxs-lookup"><span data-stu-id="969a1-131">Audio Minutes Summary Report</span></span>

<span data-ttu-id="969a1-132">No relatório de uso de minutos de áudio, o uso total de minutos é fornecido por meio de alguns modos de exibição diferentes.</span><span class="sxs-lookup"><span data-stu-id="969a1-132">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="969a1-133">Temos o resumo de uso de 30 dias mostrado ao lado da segmentação de texto como fácil de consumir caixas de texto.</span><span class="sxs-lookup"><span data-stu-id="969a1-133">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="969a1-134">O número superior mostra o total de 30 dias, com divisões internas e externas abaixo delas.</span><span class="sxs-lookup"><span data-stu-id="969a1-134">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="969a1-136">O gráfico de barras superior direita fornece uma exibição yearlong do uso de áudio da conferência.</span><span class="sxs-lookup"><span data-stu-id="969a1-136">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="969a1-137">Passe o mouse sobre o mês para mostrar os minutos de áudio da conferência.</span><span class="sxs-lookup"><span data-stu-id="969a1-137">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="969a1-138">Para mostrar a diferença no P2P e no áudio da conferência, o gráfico inferior esquerdo assume todo o áudio do ano anterior e o divide entre os dois tipos.</span><span class="sxs-lookup"><span data-stu-id="969a1-138">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

<span data-ttu-id="969a1-139">![Captura de tela: relatório](media/CQD-teams-utilization-report10.png) de resumo do Condado de chamadas o último gráfico da página minutos de áudio mostra o uso de minutos de áudio em uma sobreposição de mapa global.</span><span class="sxs-lookup"><span data-stu-id="969a1-139">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report10.png) The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="969a1-140">Este gráfico só funcionará se os dados de criação e de sub-rede forem carregados no locatário.</span><span class="sxs-lookup"><span data-stu-id="969a1-140">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="969a1-141">A sobreposição de gráfico de pizza no mapa pode ser analisada, subsequentemente fornecendo o uso de áudio regional.</span><span class="sxs-lookup"><span data-stu-id="969a1-141">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report11.png)

## <a name="drill-through-capabilities"></a><span data-ttu-id="969a1-143">Recursos de Drill-through</span><span class="sxs-lookup"><span data-stu-id="969a1-143">Drill-through capabilities</span></span>

<span data-ttu-id="969a1-144">Conforme observado anteriormente, os usuários podem analisar os relatórios de uso diários e regionais.</span><span class="sxs-lookup"><span data-stu-id="969a1-144">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="969a1-145">Uso diário</span><span class="sxs-lookup"><span data-stu-id="969a1-145">Daily Usage</span></span>

<span data-ttu-id="969a1-146">O relatório de uso diário permite que um administrador identifique os períodos de pico do consumo durante um dia.</span><span class="sxs-lookup"><span data-stu-id="969a1-146">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="969a1-147">Além do uso, também podemos capturar comentários gerais sobre o usuário e comentários sobre esse dia.</span><span class="sxs-lookup"><span data-stu-id="969a1-147">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="969a1-149">Esses dados podem ser usados para identificar regiões com problemas durante os períodos de pico de consumo.</span><span class="sxs-lookup"><span data-stu-id="969a1-149">This data can be used to identify regions having problems during peak consumption times.</span></span>

1.  <span data-ttu-id="969a1-150">Na página de Resumo de contagem de chamadas, Drill-through em uma data específica.</span><span class="sxs-lookup"><span data-stu-id="969a1-150">On the Call Count Summary page, drill-through on a specific date.</span></span> <span data-ttu-id="969a1-151">Examine a tendência por hora nesse dia para localizar o pico de utilização.</span><span class="sxs-lookup"><span data-stu-id="969a1-151">Look at the hourly trend that day to find the peak utilization.</span></span>
  <span data-ttu-id="969a1-152">![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report13.png)</span><span class="sxs-lookup"><span data-stu-id="969a1-152">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report13.png)</span></span>

2.  <span data-ttu-id="969a1-153">Clique na coluna desse dia para exibir as métricas dessa hora.</span><span class="sxs-lookup"><span data-stu-id="969a1-153">Click on the column for that day to display metrics for that hour.</span></span>
  <span data-ttu-id="969a1-154">![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="969a1-154">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report14.png)</span></span>
    
    1.  <span data-ttu-id="969a1-155">A tabela abaixo do gráfico mostrará as métricas dessa hora.</span><span class="sxs-lookup"><span data-stu-id="969a1-155">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="969a1-156">Isso pode ser classificado por qualquer cabeçalho de coluna; no entanto, ficamos interessados em encontrar áreas problemáticas.</span><span class="sxs-lookup"><span data-stu-id="969a1-156">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
        ![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report15.png)
    
    2.  <span data-ttu-id="969a1-158">Vemos que a região IND está apresentando um desempenho de vídeo ruim em conferências durante este período.</span><span class="sxs-lookup"><span data-stu-id="969a1-158">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="969a1-159">Subsequentemente, os relatórios do CQD QER da Microsoft podem ser usados para restringir o local problemático, pois o período de região e de tempo foi identificado.</span><span class="sxs-lookup"><span data-stu-id="969a1-159">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="regional-audio-details"></a><span data-ttu-id="969a1-160">Detalhes de áudio regional</span><span class="sxs-lookup"><span data-stu-id="969a1-160">Regional Audio Details</span></span>

<span data-ttu-id="969a1-161">O detalhamento de dados de áudio regional mostra especificamente o uso de minutos de áudio para a região selecionada.</span><span class="sxs-lookup"><span data-stu-id="969a1-161">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="969a1-162">Os usuários com acesso a CQD podem ver tendências de uso para áudio P2P e de conferência dentro da região selecionada.</span><span class="sxs-lookup"><span data-stu-id="969a1-162">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="969a1-163">Na página de Resumo de contagem de chamadas, faça drill-through como região específica na tabela.</span><span class="sxs-lookup"><span data-stu-id="969a1-163">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="969a1-164">![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="969a1-164">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="969a1-165">Selecione a linha com a região à qual informações adicionais são necessárias.</span><span class="sxs-lookup"><span data-stu-id="969a1-165">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="969a1-166">![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="969a1-166">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="969a1-167">As tendências de dados mostram um número significativo de minutos sendo usados na rede interna, com a conferência que supera o uso ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="969a1-167">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="969a1-168">![Captura de tela: relatório de resumo do Condado de chamadas](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="969a1-168">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="969a1-169">A tendência de áudio regional pode ser usada para mostrar como os usuários são afetados por influências externas do mundo.</span><span class="sxs-lookup"><span data-stu-id="969a1-169">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="969a1-170">Especificamente, no momento, esperamos ver o uso externo das regiões da EMEA e da Ásia-Pacífico para aumentar com as pessoas sendo solicitadas a trabalhar remotamente.</span><span class="sxs-lookup"><span data-stu-id="969a1-170">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>



## <a name="related-topics"></a><span data-ttu-id="969a1-171">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="969a1-171">Related topics</span></span>

[<span data-ttu-id="969a1-172">Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas</span><span class="sxs-lookup"><span data-stu-id="969a1-172">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="969a1-173">Classificação de fluxo no painel de qualidade da chamada</span><span class="sxs-lookup"><span data-stu-id="969a1-173">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="969a1-174">Configurar a Análise de Chamada do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="969a1-174">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="969a1-175">Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada</span><span class="sxs-lookup"><span data-stu-id="969a1-175">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="969a1-176">Análise de Chamada e Painel de Qualidade de Chamadas</span><span class="sxs-lookup"><span data-stu-id="969a1-176">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 