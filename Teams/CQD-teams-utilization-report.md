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
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="2d5d0-103">Exibir o uso do Microsoft Teams no Power BI usando dados CQD</span><span class="sxs-lookup"><span data-stu-id="2d5d0-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="2d5d0-104">Novo em março de 2020, adicionamos um relatório de Uso do Teams aos nossos modelos de consulta do Power BI para [download para CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="2d5d0-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="2d5d0-105">Esses novos relatórios de Uso do Teams permitem que você veja como (e quanto) seus usuários estão usando o Microsoft Teams acessando dados do Painel de Qualidade de Chamada do Teams (CQD).</span><span class="sxs-lookup"><span data-stu-id="2d5d0-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="2d5d0-106">Esses relatórios destinam-se a ser um local centralizado que tanto os administradores quanto os líderes de negócios podem ir rapidamente para esses dados.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="2d5d0-107">O relatório do Power BI de Uso do Teams consiste em dois relatórios principais: Resumo da Contagem de Chamada **[e](#call-count-summary-report)** Resumo **[de Minutos de Áudio.](#audio-minutes-summary-report)**</span><span class="sxs-lookup"><span data-stu-id="2d5d0-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="2d5d0-108">Os [relatórios Uso Diário,](#daily-usage)Detalhes [](#user-list) de [Áudio Regional,](#regional-audio-details)Detalhes de Conferência e Lista de Usuários são lançados quando um usuário tira proveito dos relatórios de drill down, que estão nas descrições abaixo. [](#conference-details)</span><span class="sxs-lookup"><span data-stu-id="2d5d0-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="2d5d0-109">Os dados de construção e sub-rede devem ser preenchidos para fornecer recursos regionais e de filtragem de rede.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="2d5d0-110">Relatório de Resumo da Contagem de Chamada</span><span class="sxs-lookup"><span data-stu-id="2d5d0-110">Call Count Summary Report</span></span>

<span data-ttu-id="2d5d0-111">A página principal (Resumo da Contagem de Chamada) fornece imediatamente o número de sessões de áudio, vídeo e compartilhamento de tela dos últimos 30 e 90 dias, conforme o título da seção.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="2d5d0-112">Os dados exibidos inicialmente são para a organização como um todo e podem ser filtrados usando as opções de menu suspenso da slicer no lado esquerdo da página.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="2d5d0-114">À direita dos menus suspensos da slicer, o número de chamadas por tipo de mídia é dividido em uma exibição interna/externa nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="2d5d0-115">Podemos ver através da captura de tela acima que há mais chamadas acontecendo de locais organizacionais externos, o que faz sentido considerando o ambiente global atual.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="2d5d0-116">![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="2d5d0-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="2d5d0-117">À direita da caixa de contagem de tipos de mídia, temos a Contagem Mensal de Chamada por Tipo de Mídia dos últimos 90 dias.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="2d5d0-118">Cada tipo de coluna e mídia pode ser passado o mouse sobre para exibir a contagem de um mês anterior ou o mês atual até a data, fornecendo informações de tendência de uso.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="2d5d0-119">![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="2d5d0-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="2d5d0-120">O gráfico intermediário funciona como o gráfico de 90 dias, no entanto, ele fornece uma exibição de uso diário dos últimos 30 dias e permite que um usuário clique com o botão direito do mouse e faça uma busca drill down nos detalhes de um dia específico.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="2d5d0-121">![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="2d5d0-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="2d5d0-122">Na seção inferior esquerda da página, você encontrará uma tabela que fornece valores totais para cada tipo de mídia no ano passado.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="2d5d0-123">![Captura de tela: Captura de tela relatórios de uso ](media/CQD-teams-utilization-report5.png) ![ do Teams: Relatórios de uso do Teams](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="2d5d0-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="2d5d0-124">À direita da tabela, um gráfico de barras mostra os clientes com mais uso (chamadas/fluxos) dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="2d5d0-125">![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="2d5d0-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="2d5d0-126">O último conjunto de gráficos desta página mostra cada tipo de mídia individualmente, com uma divisão mostrando o uso de conferência e P2P.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="2d5d0-127">Os gráficos a seguir mostram que há um número significativamente maior de uso de conferência em comparação com P2P.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="2d5d0-128">![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="2d5d0-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="2d5d0-129">Relatório de Resumo de Minutos de Áudio</span><span class="sxs-lookup"><span data-stu-id="2d5d0-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="2d5d0-130">No relatório de uso de Minutos de Áudio, o uso total de minutos é fornecido por meio de algumas exibições diferentes.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="2d5d0-131">Temos o resumo de uso de 30 dias mostrado ao lado das slicers como fácil de consumir caixas de texto.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="2d5d0-132">O número superior mostra o total de 30 dias, com detalhamentos internos e externos abaixo disso.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="2d5d0-134">O gráfico de barras superior direita fornece uma exibição anual do uso de áudio de conferência.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="2d5d0-135">Passe o mouse sobre o mês para mostrar os minutos de áudio da conferência.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="2d5d0-136">Para mostrar a diferença no áudio de conferência e P2P, o gráfico inferior esquerdo leva todo o áudio do ano passado e divide-o entre os dois tipos.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="2d5d0-138">O último gráfico da página Minutos de áudio mostra o uso de minutos de áudio em uma sobreposição global de mapa.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="2d5d0-139">Esse gráfico só funcionará se dados de construção e sub-rede são carregados para o locatário.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="2d5d0-140">A sobreposição do gráfico de pizza no mapa pode ser detalhada, fornecendo posteriormente o uso de áudio regional.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="2d5d0-142">Recursos de drill-through</span><span class="sxs-lookup"><span data-stu-id="2d5d0-142">Drill-through capabilities</span></span>

<span data-ttu-id="2d5d0-143">Conforme mencionado anteriormente, os usuários podem detalhar os relatórios de uso diário e regional.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="2d5d0-144">Uso Diário</span><span class="sxs-lookup"><span data-stu-id="2d5d0-144">Daily Usage</span></span>

<span data-ttu-id="2d5d0-145">O relatório Uso Diário permite que um administrador identifique períodos de pico de consumo durante um dia.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="2d5d0-146">Além do uso, também podemos capturar o sentimento geral do usuário e os comentários desse dia.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="2d5d0-148">O relatório de uso diário exibe o número de compartilhamentos de Áudio, Vídeo e Tela do dia selecionado com a capacidade de diferenciar conectividade interna e externa.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="2d5d0-149">Uma divisão de Conferência e Ponto a Ponto está à direita imediata da caixa de total de modalidades.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="2d5d0-150">O canto superior direito do relatório fornece uma lista de conferências com sua ID associada e os participantes do dia.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="2d5d0-151">A lista de conferências fornece um drill down adicional para o relatório Detalhes da Conferência também.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="2d5d0-152">SUBSTITUIR GRÁFICO</span><span class="sxs-lookup"><span data-stu-id="2d5d0-152">REPLACE GRAPHIC</span></span>

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="2d5d0-154">O gráfico de barras na área central permite que o usuário identifique os períodos de pico de consumo durante um dia.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="2d5d0-155">Os usuários podem fazer drill down na hora representada no gráfico que apresentará o relatório da Lista de Usuários por hora.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="2d5d0-156">À direita do gráfico de barras, os Comentários do Usuário são apresentados em um formato visual.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="2d5d0-157">Embora o sentimentos do usuário possa ser subjetivo, ele fornece informações que podem ser usadas para identificar possíveis problemas.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="2d5d0-158">A tabela inferior fornece um intervalo de métricas para o dia.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="2d5d0-159">Porcentagens ruins juntamente com taxas de falha podem fornecer ao administrador áreas potenciais de melhoria.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="2d5d0-160">Cada hora também pode ser selecionada individualmente, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="2d5d0-161">Esses dados podem ser usados para identificar regiões com problemas durante os períodos de consumo máximo.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="2d5d0-162">Clique na coluna desse dia para exibir as métricas dessa hora.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="2d5d0-163">![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="2d5d0-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="2d5d0-164">A tabela abaixo do gráfico exibirá as métricas para essa hora.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="2d5d0-165">Isso pode ser classificação por qualquer header de coluna; no entanto, teríamos interesse em encontrar áreas problemáticas.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="2d5d0-167">Vemos que a região IND está enfrentando um desempenho de vídeo ruim em conferências durante esse período.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="2d5d0-168">Posteriormente, os relatórios CQD QER Microsoft podem ser usados para restringir o local problemático à medida que a região e o período de tempo foram identificados.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="2d5d0-169">Detalhes da Conferência</span><span class="sxs-lookup"><span data-stu-id="2d5d0-169">Conference Details</span></span>

<span data-ttu-id="2d5d0-170">O relatório Detalhes da Conferência fornece informações adicionais para reuniões, desde uma lista de participantes até os tipos de mídia usados durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="2d5d0-171">Clique com o botão direito do mouse em uma conferência na barra de participantes no gráfico de ID de conferência na página Uso diário para detalhar os detalhes da conferência.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report24.png)

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="2d5d0-174">Podemos ver os participantes da conferência, bem como todas as informações pertinentes até a perda de pacotes e tremidação para ajudar com possíveis esforços de solução de problemas na tabela inferior.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="2d5d0-176">Detalhes regionais do áudio</span><span class="sxs-lookup"><span data-stu-id="2d5d0-176">Regional Audio Details</span></span>

<span data-ttu-id="2d5d0-177">A busca de Detalhes Regionais do Áudio mostra especificamente o uso de minutos de áudio para a região selecionada.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="2d5d0-178">Os usuários com acesso ao CQD podem ver tendências de uso para P2P e áudio de conferência dentro da região selecionada.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="2d5d0-179">Na página Resumo da Contagem de Chamada, faça drill-through para uma região específica na tabela.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="2d5d0-180">![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="2d5d0-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="2d5d0-181">Selecione a linha com as informações adicionais de região necessárias.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="2d5d0-182">![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="2d5d0-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="2d5d0-183">As tendências de dados mostram um número significativo de minutos sendo usados na rede interna, com a conferência superando o uso de P2P.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="2d5d0-184">![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="2d5d0-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="2d5d0-185">A tendência de áudio regional pode ser usada para mostrar como os usuários são afetados por influencias externas no mundo.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="2d5d0-186">Especificamente, no momento, esperamos ver o uso externo para as regiões emEA e APAC aumentarem, com as pessoas sendo convidadas a trabalhar remotamente.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="2d5d0-187">Lista de Usuários</span><span class="sxs-lookup"><span data-stu-id="2d5d0-187">User List</span></span>

<span data-ttu-id="2d5d0-188">O drill down da Lista de Usuários fornece, como se espera, informações específicas do usuário para uma hora específica selecionada pela pessoa que está exibindo o relatório.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="2d5d0-189">O relatório lista de usuários pode ser acessado por meio de uma análise do gráfico De tendências por hora no relatório Uso Diário.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="2d5d0-190">Clique com o botão direito do mouse nas informações adicionais de hora necessárias e selecione Drill through e Lista de Usuários, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="2d5d0-192">O relatório lista de usuários mostra conectividade interna/externa por meio do gráfico de rosca na parte superior central da página.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="2d5d0-193">Podemos ver que há uma grande quantidade de participação de Fora da rede corporativa na imagem abaixo.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="2d5d0-194">O canto superior direito do gráfico mostra o número de chamadas feitas por cada usuário dentro dessa hora.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![Captura de tela: Relatórios de Uso do Teams](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="2d5d0-196">A tabela inferior fornece informações detalhadas para as sessões em que cada usuário participou durante essa hora.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="2d5d0-197">A coluna Tipo de Falha é útil para determinar o que causou a queda de uma chamada.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="2d5d0-198">As colunas Capturar e Renderizar Dispositivo são úteis para identificar por que uma chamada foi relatada com baixa qualidade.</span><span class="sxs-lookup"><span data-stu-id="2d5d0-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="2d5d0-199">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2d5d0-199">Related topics</span></span>

[<span data-ttu-id="2d5d0-200">Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas</span><span class="sxs-lookup"><span data-stu-id="2d5d0-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="2d5d0-201">Classificação de fluxo no painel de qualidade da chamada</span><span class="sxs-lookup"><span data-stu-id="2d5d0-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="2d5d0-202">Configurar a Análise de Chamada do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2d5d0-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="2d5d0-203">Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada</span><span class="sxs-lookup"><span data-stu-id="2d5d0-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="2d5d0-204">Análise de Chamada e Painel de Qualidade de Chamadas</span><span class="sxs-lookup"><span data-stu-id="2d5d0-204">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

[<span data-ttu-id="2d5d0-205">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="2d5d0-205">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
 