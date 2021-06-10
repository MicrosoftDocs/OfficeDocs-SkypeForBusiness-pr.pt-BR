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
localization_priority: Normal
description: Use os Teams relatórios de utilização Power BI para acessar Microsoft Teams dados do CQD (Painel de Qualidade de Chamada) para rastrear Microsoft Teams uso em sua organização.
ms.openlocfilehash: 719f02ce7a5cd36e96ed7fd563c259c6e77764fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095035"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="9d23d-103">Exibir Microsoft Teams utilização em Power BI usando dados CQD</span><span class="sxs-lookup"><span data-stu-id="9d23d-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="9d23d-104">Novo em março de 2020, adicionamos um relatório de utilização Teams para nossos modelos de consulta Power BI download para [CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="9d23d-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="9d23d-105">Esse novo Teams relatórios de utilização permite que você veja como (e quanto) seus usuários estão usando Microsoft Teams acessando dados do CQD (Painel de Qualidade de Chamada) Teams chamada.</span><span class="sxs-lookup"><span data-stu-id="9d23d-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="9d23d-106">Esses relatórios se destinam a ser um local centralizado que tanto administradores quanto líderes de negócios podem ir rapidamente para esses dados.</span><span class="sxs-lookup"><span data-stu-id="9d23d-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="9d23d-107">O Teams relatório de utilização Power BI consiste em dois relatórios **[principais:](#call-count-summary-report)** Resumo da Contagem de Chamada e **[Resumo de Minutos de Áudio.](#audio-minutes-summary-report)**</span><span class="sxs-lookup"><span data-stu-id="9d23d-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="9d23d-108">Os [relatórios Uso](#daily-usage)Diário, Detalhes [](#user-list) de Áudio [Regionais,](#regional-audio-details)Detalhes da Conferência e Lista de Usuários são lançados quando um usuário tira proveito dos relatórios de detalhamento, notados nas descrições abaixo. [](#conference-details)</span><span class="sxs-lookup"><span data-stu-id="9d23d-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="9d23d-109">Os dados de construção e sub-rede devem ser preenchidos para fornecer recursos regionais e de filtragem de rede.</span><span class="sxs-lookup"><span data-stu-id="9d23d-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="9d23d-110">Relatório de Resumo da Contagem de Chamada</span><span class="sxs-lookup"><span data-stu-id="9d23d-110">Call Count Summary Report</span></span>

<span data-ttu-id="9d23d-111">A página principal (Resumo da Contagem de Chamada) fornece imediatamente o número de sessões de compartilhamento de áudio, vídeo e tela nos últimos 30 e 90 dias, conforme o título da seção.</span><span class="sxs-lookup"><span data-stu-id="9d23d-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="9d23d-112">Os dados inicialmente exibidos são para a organização como um todo e podem ser filtrados usando as opções de menu suspenso da slicer no lado esquerdo da página.</span><span class="sxs-lookup"><span data-stu-id="9d23d-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="9d23d-114">À direita dos menus suspensos da slicer, o número de chamadas por tipo de mídia é dividido para uma exibição interna/externa nos últimos trinta dias.</span><span class="sxs-lookup"><span data-stu-id="9d23d-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="9d23d-115">Podemos ver pela captura de tela acima que há mais chamadas acontecendo de locais organizacionais externos, o que faz sentido considerando o ambiente global atual.</span><span class="sxs-lookup"><span data-stu-id="9d23d-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="9d23d-116">![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="9d23d-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="9d23d-117">À direita da caixa de contagem de tipos de mídia, temos a Contagem de Chamada Mensal por Tipo de Mídia dos últimos 90 dias.</span><span class="sxs-lookup"><span data-stu-id="9d23d-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="9d23d-118">Cada coluna e tipo de mídia podem ser passados para exibir a contagem de um mês anterior ou o mês atual até a data, fornecendo informações de tendência de uso.</span><span class="sxs-lookup"><span data-stu-id="9d23d-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="9d23d-119">![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="9d23d-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="9d23d-120">O gráfico do meio funciona como o gráfico de 90 dias, no entanto, fornece uma exibição de uso diária para os últimos 30 dias e permite que o usuário clique com o botão direito do mouse e faça uma análise de detalhes para um dia específico.</span><span class="sxs-lookup"><span data-stu-id="9d23d-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="9d23d-121">![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="9d23d-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="9d23d-122">Na seção inferior esquerda da página, você encontrará uma tabela fornecendo valores totais para cada tipo de mídia no ano passado.</span><span class="sxs-lookup"><span data-stu-id="9d23d-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="9d23d-123">![Captura de tela: Teams relatórios de utilização ](media/CQD-teams-utilization-report5.png) ![ Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="9d23d-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="9d23d-124">À direita da tabela, um gráfico de barras mostra clientes com mais uso (chamadas/fluxos) dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="9d23d-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="9d23d-125">![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="9d23d-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="9d23d-126">O último conjunto de gráficos desta página mostra cada tipo de mídia individualmente, com uma divisão mostrando conferência e uso P2P.</span><span class="sxs-lookup"><span data-stu-id="9d23d-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="9d23d-127">Os gráficos abaixo mostram que há um número significativamente maior de uso de conferência em comparação com P2P.</span><span class="sxs-lookup"><span data-stu-id="9d23d-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="9d23d-128">![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="9d23d-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="9d23d-129">Relatório de Resumo de Minutos de Áudio</span><span class="sxs-lookup"><span data-stu-id="9d23d-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="9d23d-130">No relatório de uso de Minutos de Áudio, o uso total de minutos é fornecido por meio de algumas exibições diferentes.</span><span class="sxs-lookup"><span data-stu-id="9d23d-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="9d23d-131">Temos o resumo de uso de trinta dias mostrado ao lado das slicers como fácil de consumir caixas de texto.</span><span class="sxs-lookup"><span data-stu-id="9d23d-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="9d23d-132">O número superior mostra o total de trinta dias, com quebras internas e externas abaixo disso.</span><span class="sxs-lookup"><span data-stu-id="9d23d-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="9d23d-134">O gráfico da barra superior direita fornece uma exibição de longo período do uso de áudio de conferência.</span><span class="sxs-lookup"><span data-stu-id="9d23d-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="9d23d-135">Passe o mouse durante o mês para mostrar os minutos de áudio da conferência.</span><span class="sxs-lookup"><span data-stu-id="9d23d-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="9d23d-136">Para mostrar a diferença no áudio de conferência e P2P, o gráfico inferior esquerdo pega todo o áudio do último ano e o divide entre os dois tipos.</span><span class="sxs-lookup"><span data-stu-id="9d23d-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="9d23d-138">O último gráfico da página Minutos de áudio mostra o uso de minutos de áudio em uma sobreposição global de mapa.</span><span class="sxs-lookup"><span data-stu-id="9d23d-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="9d23d-139">Esse gráfico só funcionará se os dados de construção e sub-rede são carregados para o locatário.</span><span class="sxs-lookup"><span data-stu-id="9d23d-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="9d23d-140">A sobreposição do gráfico de pizza no mapa pode ser furada, fornecendo posteriormente o uso de áudio regional.</span><span class="sxs-lookup"><span data-stu-id="9d23d-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="9d23d-142">Recursos de drill-through</span><span class="sxs-lookup"><span data-stu-id="9d23d-142">Drill-through capabilities</span></span>

<span data-ttu-id="9d23d-143">Conforme mencionado anteriormente, os usuários podem detalhar os relatórios de uso diários e regionais.</span><span class="sxs-lookup"><span data-stu-id="9d23d-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="9d23d-144">Uso Diário</span><span class="sxs-lookup"><span data-stu-id="9d23d-144">Daily Usage</span></span>

<span data-ttu-id="9d23d-145">O relatório uso diário permite que um administrador identifique os períodos de pico de consumo ao longo de um dia.</span><span class="sxs-lookup"><span data-stu-id="9d23d-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="9d23d-146">Além do uso, também podemos capturar o sentimento geral do usuário e os comentários desse dia.</span><span class="sxs-lookup"><span data-stu-id="9d23d-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="9d23d-148">O relatório de uso diário exibe o número de compartilhamentos de Áudio, Vídeo e Tela do dia selecionado com a capacidade de diferenciar entre conectividade interna e externa.</span><span class="sxs-lookup"><span data-stu-id="9d23d-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="9d23d-149">Uma divisão De Conferência e Ponto a Ponto é à direita imediata da caixa total da modalidade.</span><span class="sxs-lookup"><span data-stu-id="9d23d-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="9d23d-150">O canto superior direito do relatório fornece uma lista de conferências com sua ID e participantes associados para o dia.</span><span class="sxs-lookup"><span data-stu-id="9d23d-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="9d23d-151">A lista de conferências também fornece uma análise adicional para o relatório de Detalhes da Conferência.</span><span class="sxs-lookup"><span data-stu-id="9d23d-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="9d23d-152">SUBSTITUIR GRÁFICO</span><span class="sxs-lookup"><span data-stu-id="9d23d-152">REPLACE GRAPHIC</span></span>

![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="9d23d-154">O gráfico de barras na área central permite que o usuário identifique os períodos de pico de consumo ao longo de um dia.</span><span class="sxs-lookup"><span data-stu-id="9d23d-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="9d23d-155">Os usuários podem detalhar a hora representada no gráfico que apresentará o relatório de Lista de Usuários por hora.</span><span class="sxs-lookup"><span data-stu-id="9d23d-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="9d23d-156">À direita do gráfico de barras, o Feedback do Usuário é apresentado em um formato visual.</span><span class="sxs-lookup"><span data-stu-id="9d23d-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="9d23d-157">Embora o sentimento do usuário possa ser subjetivo, ele fornece informações que podem ser usadas para identificar possíveis problemas.</span><span class="sxs-lookup"><span data-stu-id="9d23d-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="9d23d-158">A tabela inferior fornece um intervalo de métricas para o dia.</span><span class="sxs-lookup"><span data-stu-id="9d23d-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="9d23d-159">Porcentagens ruins, juntamente com as taxas de falha, podem fornecer a um administrador áreas de melhoria em potencial.</span><span class="sxs-lookup"><span data-stu-id="9d23d-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="9d23d-160">Cada hora também pode ser selecionada individualmente, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="9d23d-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="9d23d-161">Esses dados podem ser usados para identificar regiões com problemas durante os horários de pico de consumo.</span><span class="sxs-lookup"><span data-stu-id="9d23d-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="9d23d-162">Clique na coluna desse dia para exibir métricas para essa hora.</span><span class="sxs-lookup"><span data-stu-id="9d23d-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="9d23d-163">![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="9d23d-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="9d23d-164">A tabela abaixo do gráfico exibirá as métricas dessa hora.</span><span class="sxs-lookup"><span data-stu-id="9d23d-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="9d23d-165">Isso pode ser organizado por qualquer header de coluna; no entanto, estamos interessados em encontrar áreas problemáticas.</span><span class="sxs-lookup"><span data-stu-id="9d23d-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="9d23d-167">Vemos que a região do IND está enfrentando um desempenho de vídeo ruim em conferências durante esse período.</span><span class="sxs-lookup"><span data-stu-id="9d23d-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="9d23d-168">Subsequentemente, os relatórios da Microsoft CQD QER podem ser usados para restringir o local problemático à medida que a região e o período de tempo foram identificados.</span><span class="sxs-lookup"><span data-stu-id="9d23d-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="9d23d-169">Detalhes da conferência</span><span class="sxs-lookup"><span data-stu-id="9d23d-169">Conference Details</span></span>

<span data-ttu-id="9d23d-170">O relatório Detalhes da Conferência fornece informações adicionais para reuniões, de uma lista de participantes, aos tipos de mídia usados durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="9d23d-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="9d23d-171">Clique com o botão direito do mouse em uma conferência na barra de participantes no gráfico de ID da conferência na página uso diário para detalhar os detalhes da conferência.</span><span class="sxs-lookup"><span data-stu-id="9d23d-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report24.png)

![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="9d23d-174">Podemos ver os participantes da conferência, bem como todas as informações pertinentes para perda de pacotes e tremência para ajudar com possíveis esforços de solução de problemas na tabela inferior.</span><span class="sxs-lookup"><span data-stu-id="9d23d-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="9d23d-176">Detalhes regionais de áudio</span><span class="sxs-lookup"><span data-stu-id="9d23d-176">Regional Audio Details</span></span>

<span data-ttu-id="9d23d-177">A pesquisa detalhes de áudio regionais mostra especificamente o uso de minutos de áudio para a região selecionada.</span><span class="sxs-lookup"><span data-stu-id="9d23d-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="9d23d-178">Os usuários com acesso ao CQD podem ver tendências de uso para P2P e áudio de conferência dentro da região selecionada.</span><span class="sxs-lookup"><span data-stu-id="9d23d-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="9d23d-179">Na página Resumo da Contagem de Chamada, faça uma análise de como região específica através da tabela.</span><span class="sxs-lookup"><span data-stu-id="9d23d-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="9d23d-180">![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="9d23d-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="9d23d-181">Selecione a linha com as informações adicionais da região necessárias.</span><span class="sxs-lookup"><span data-stu-id="9d23d-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="9d23d-182">![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="9d23d-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="9d23d-183">As tendências de dados mostram um número significativo de minutos sendo usados na rede interna, com a conferência superando muito o uso de P2P.</span><span class="sxs-lookup"><span data-stu-id="9d23d-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="9d23d-184">![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="9d23d-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="9d23d-185">A tendência de áudio regional pode ser usada para mostrar como os usuários são afetados por influências externas no mundo.</span><span class="sxs-lookup"><span data-stu-id="9d23d-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="9d23d-186">Especificamente, no momento, esperamos ver o uso externo para as regiões EMEA e APAC aumentarem com as pessoas sendo solicitados a trabalhar remotamente.</span><span class="sxs-lookup"><span data-stu-id="9d23d-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="9d23d-187">Lista de usuários</span><span class="sxs-lookup"><span data-stu-id="9d23d-187">User List</span></span>

<span data-ttu-id="9d23d-188">A sonda de lista de usuários fornece, como se pode esperar, informações específicas do usuário para uma hora específica selecionada pela pessoa que está exibindo o relatório.</span><span class="sxs-lookup"><span data-stu-id="9d23d-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="9d23d-189">O relatório de Lista de Usuários é acessível por meio de uma pesquisa no gráfico Tendências por Hora no relatório de Uso Diário.</span><span class="sxs-lookup"><span data-stu-id="9d23d-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="9d23d-190">Clique com o botão direito do mouse na hora para as informações adicionais necessárias e selecione Drill through e User List, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="9d23d-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="9d23d-192">O relatório de Lista de Usuários mostra conectividade interna/externa por meio do gráfico de rosca no centro superior da página.</span><span class="sxs-lookup"><span data-stu-id="9d23d-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="9d23d-193">Podemos ver que há uma grande participação de Fora da rede corporativa na imagem abaixo.</span><span class="sxs-lookup"><span data-stu-id="9d23d-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="9d23d-194">A parte superior direita do gráfico mostra o número de chamadas feitas por cada usuário dentro dessa hora.</span><span class="sxs-lookup"><span data-stu-id="9d23d-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![Captura de tela: Teams relatórios de utilização](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="9d23d-196">A tabela inferior fornece informações detalhadas para as sessões em que cada usuário participou durante essa hora.</span><span class="sxs-lookup"><span data-stu-id="9d23d-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="9d23d-197">A coluna Tipo de Falha é útil para determinar o que causou a queda de uma chamada.</span><span class="sxs-lookup"><span data-stu-id="9d23d-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="9d23d-198">As colunas Capture e Render Device são úteis para identificar por que uma chamada foi relatada com baixa qualidade.</span><span class="sxs-lookup"><span data-stu-id="9d23d-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="9d23d-199">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9d23d-199">Related topics</span></span>

[<span data-ttu-id="9d23d-200">Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas</span><span class="sxs-lookup"><span data-stu-id="9d23d-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="9d23d-201">Classificação de fluxo no painel de qualidade da chamada</span><span class="sxs-lookup"><span data-stu-id="9d23d-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="9d23d-202">Configurar a Análise de Chamada do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9d23d-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="9d23d-203">Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada</span><span class="sxs-lookup"><span data-stu-id="9d23d-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="9d23d-204">Análise de Chamada e Painel de Qualidade de Chamadas</span><span class="sxs-lookup"><span data-stu-id="9d23d-204">Call Analytics and Call Quality Dashboard</span></span>](./monitor-call-quality-qos.md)

[<span data-ttu-id="9d23d-205">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="9d23d-205">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
