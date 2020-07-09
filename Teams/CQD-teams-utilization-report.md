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
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="16736-103">Exibir a utilização do Microsoft Teams no Power BI usando dados do CQD</span><span class="sxs-lookup"><span data-stu-id="16736-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="16736-104">Novidades de março de 2020, adicionamos um relatório de utilização do teams aos nossos [modelos de consulta para o Power bi](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)que podem ser baixados para CQD.</span><span class="sxs-lookup"><span data-stu-id="16736-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="16736-105">Esta nova equipe de relatórios de utilização permite que você veja como (e quanto) os usuários estão usando o Microsoft Teams acessando os dados do painel de qualidade de chamada do Teams (CQD).</span><span class="sxs-lookup"><span data-stu-id="16736-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="16736-106">Esses relatórios destinam-se a serem um local centralizado que os administradores e líderes de negócios possam acessar rapidamente para esses dados.</span><span class="sxs-lookup"><span data-stu-id="16736-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="16736-107">O relatório do Power BI de utilização do teams consiste em dois relatórios principais: Resumo da **[contagem de chamadas](#call-count-summary-report)** e Resumo de **[minutos de áudio](#audio-minutes-summary-report)**.</span><span class="sxs-lookup"><span data-stu-id="16736-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="16736-108">O [uso diário](#daily-usage), [os detalhes de áudio regional](#regional-audio-details), os [detalhes da conferência](#conference-details) e os relatórios da lista de [usuários](#user-list) entram em cena quando um usuário aproveita os relatórios detalhados, observados nas descrições abaixo.</span><span class="sxs-lookup"><span data-stu-id="16736-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="16736-109">Os dados de criação e de sub-rede devem ser preenchidos para fornecer recursos regionais e de filtragem de rede.</span><span class="sxs-lookup"><span data-stu-id="16736-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="16736-110">Relatório de Resumo de contagem de chamadas</span><span class="sxs-lookup"><span data-stu-id="16736-110">Call Count Summary Report</span></span>

<span data-ttu-id="16736-111">A página principal (Resumo da contagem de chamadas) fornece imediatamente o número de sessões de áudio, vídeo e compartilhamento de tela nos últimos 30 e 90 dias, conforme observado no título da seção.</span><span class="sxs-lookup"><span data-stu-id="16736-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="16736-112">Os dados inicialmente exibidos são para a organização como um todo e podem ser filtrados usando as opções suspensas de segmentação de dados no lado esquerdo da página.</span><span class="sxs-lookup"><span data-stu-id="16736-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="16736-114">À direita das listas suspensas de segmentação de texto, o número de chamadas por tipo de mídia é dividido em uma exibição interna/externa durante os últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="16736-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="16736-115">Podemos ver na captura de tela acima que há mais chamadas em locais organizacionais externos, o que faz sentido considerar o ambiente global atual.</span><span class="sxs-lookup"><span data-stu-id="16736-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="16736-116">![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="16736-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="16736-117">À direita da caixa de contagem de tipo de mídia, temos a contagem de chamadas mensal por tipo de mídia para os últimos 90 dias.</span><span class="sxs-lookup"><span data-stu-id="16736-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="16736-118">Cada tipo de coluna e mídia pode ser focalizado para exibir a contagem de um mês anterior ou o mês atual até o momento, fornecendo informações de tendência de uso.</span><span class="sxs-lookup"><span data-stu-id="16736-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="16736-119">![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="16736-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="16736-120">O gráfico central funciona como o gráfico de 90 dias, mas fornece um modo de exibição de uso diário dos últimos 30 dias e permite que um usuário clique com o botão direito do mouse e faça drill down nos detalhes de um dia específico.</span><span class="sxs-lookup"><span data-stu-id="16736-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="16736-121">![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="16736-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="16736-122">Na seção inferior esquerda da página, você encontrará uma tabela que fornece os valores totais para cada tipo de mídia no ano passado.</span><span class="sxs-lookup"><span data-stu-id="16736-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="16736-123">![Captura de tela: relatórios de utilização do teams ](media/CQD-teams-utilization-report5.png) ![ : relatórios de utilização do teams](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="16736-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="16736-124">À direita da tabela, um gráfico de barras mostra os clientes com o maior uso (chamadas/fluxos) dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="16736-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="16736-125">![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="16736-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="16736-126">O último conjunto de gráficos para esta página mostra cada tipo de mídia individualmente, com uma divisão que mostra o uso de conferência e P2P.</span><span class="sxs-lookup"><span data-stu-id="16736-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="16736-127">Os gráficos abaixo mostram que há um número de uso de conferência significativamente maior se comparado ao P2P.</span><span class="sxs-lookup"><span data-stu-id="16736-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="16736-128">![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="16736-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="16736-129">Relatório de Resumo de minutos de áudio</span><span class="sxs-lookup"><span data-stu-id="16736-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="16736-130">No relatório de uso de minutos de áudio, o uso total de minutos é fornecido por meio de alguns modos de exibição diferentes.</span><span class="sxs-lookup"><span data-stu-id="16736-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="16736-131">Temos o resumo de uso de 30 dias mostrado ao lado da segmentação de texto como fácil de consumir caixas de texto.</span><span class="sxs-lookup"><span data-stu-id="16736-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="16736-132">O número superior mostra o total de 30 dias, com divisões internas e externas abaixo delas.</span><span class="sxs-lookup"><span data-stu-id="16736-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="16736-134">O gráfico de barras superior direita fornece uma exibição yearlong do uso de áudio da conferência.</span><span class="sxs-lookup"><span data-stu-id="16736-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="16736-135">Passe o mouse sobre o mês para mostrar os minutos de áudio da conferência.</span><span class="sxs-lookup"><span data-stu-id="16736-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="16736-136">Para mostrar a diferença no P2P e no áudio da conferência, o gráfico inferior esquerdo assume todo o áudio do ano anterior e o divide entre os dois tipos.</span><span class="sxs-lookup"><span data-stu-id="16736-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="16736-138">O último gráfico da página minutos de áudio mostra o uso de minutos de áudio em uma sobreposição de mapa global.</span><span class="sxs-lookup"><span data-stu-id="16736-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="16736-139">Este gráfico só funcionará se os dados de criação e de sub-rede forem carregados no locatário.</span><span class="sxs-lookup"><span data-stu-id="16736-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="16736-140">A sobreposição de gráfico de pizza no mapa pode ser analisada, subsequentemente fornecendo o uso de áudio regional.</span><span class="sxs-lookup"><span data-stu-id="16736-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="16736-142">Recursos de Drill-through</span><span class="sxs-lookup"><span data-stu-id="16736-142">Drill-through capabilities</span></span>

<span data-ttu-id="16736-143">Conforme observado anteriormente, os usuários podem analisar os relatórios de uso diários e regionais.</span><span class="sxs-lookup"><span data-stu-id="16736-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="16736-144">Uso diário</span><span class="sxs-lookup"><span data-stu-id="16736-144">Daily Usage</span></span>

<span data-ttu-id="16736-145">O relatório de uso diário permite que um administrador identifique os períodos de pico do consumo durante um dia.</span><span class="sxs-lookup"><span data-stu-id="16736-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="16736-146">Além do uso, também podemos capturar comentários gerais sobre o usuário e comentários sobre esse dia.</span><span class="sxs-lookup"><span data-stu-id="16736-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="16736-148">O relatório de uso diário exibe a quantidade de recursos de áudio, vídeo e de tela do dia selecionado com a capacidade adicional de diferenciar entre conectividade interna e externa.</span><span class="sxs-lookup"><span data-stu-id="16736-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="16736-149">Uma divisão de conferência e ponto a ponto para ponto imediatamente à direita da caixa de total de modalidade.</span><span class="sxs-lookup"><span data-stu-id="16736-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="16736-150">O canto superior direito do relatório fornece uma lista de conferências com a identificação e os participantes associados do dia.</span><span class="sxs-lookup"><span data-stu-id="16736-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="16736-151">A lista de conferências também fornece um detalhamento adicional para o relatório de detalhes da conferência.</span><span class="sxs-lookup"><span data-stu-id="16736-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="16736-152">SUBSTITUIR GRÁFICO</span><span class="sxs-lookup"><span data-stu-id="16736-152">REPLACE GRAPHIC</span></span>

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="16736-154">O gráfico de barras na área central permite que o usuário identifique os períodos de pico de consumo durante um dia.</span><span class="sxs-lookup"><span data-stu-id="16736-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="16736-155">Os usuários podem fazer buscas detalhadas na hora representada no gráfico, que apresentará o relatório da lista de usuários da hora.</span><span class="sxs-lookup"><span data-stu-id="16736-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="16736-156">À direita do gráfico de barras, o feedback do usuário é apresentado em um formato visual.</span><span class="sxs-lookup"><span data-stu-id="16736-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="16736-157">Embora os problemas do usuário possam ser subjetivos, ele fornece informações que podem ser usadas para identificar possíveis problemas.</span><span class="sxs-lookup"><span data-stu-id="16736-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="16736-158">A tabela inferior fornece um intervalo de métricas para o dia.</span><span class="sxs-lookup"><span data-stu-id="16736-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="16736-159">Porcentagens insatisfatórias juntamente com as tarifas de falha podem oferecer aos administradores possíveis áreas de melhoria.</span><span class="sxs-lookup"><span data-stu-id="16736-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="16736-160">Cada hora também pode ser selecionada individualmente, como mostrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="16736-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="16736-161">Esses dados podem ser usados para identificar regiões com problemas durante os períodos de pico de consumo.</span><span class="sxs-lookup"><span data-stu-id="16736-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="16736-162">Clique na coluna desse dia para exibir as métricas dessa hora.</span><span class="sxs-lookup"><span data-stu-id="16736-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="16736-163">![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="16736-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="16736-164">A tabela abaixo do gráfico mostrará as métricas dessa hora.</span><span class="sxs-lookup"><span data-stu-id="16736-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="16736-165">Isso pode ser classificado por qualquer cabeçalho de coluna; no entanto, ficamos interessados em encontrar áreas problemáticas.</span><span class="sxs-lookup"><span data-stu-id="16736-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="16736-167">Vemos que a região IND está apresentando um desempenho de vídeo ruim em conferências durante este período.</span><span class="sxs-lookup"><span data-stu-id="16736-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="16736-168">Subsequentemente, os relatórios do CQD QER da Microsoft podem ser usados para restringir o local problemático, pois o período de região e de tempo foi identificado.</span><span class="sxs-lookup"><span data-stu-id="16736-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="16736-169">Detalhes da conferência</span><span class="sxs-lookup"><span data-stu-id="16736-169">Conference Details</span></span>

<span data-ttu-id="16736-170">O relatório de detalhes da conferência fornece informações adicionais para reuniões, a partir de uma lista de participantes, para os tipos de mídia usados durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="16736-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="16736-171">Clique com o botão direito do mouse em uma conferência na barra de participantes na página de uso diário para fazer uma busca detalhada nos detalhes da conferência.</span><span class="sxs-lookup"><span data-stu-id="16736-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report24.png)

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="16736-174">Podemos ver os participantes da conferência, bem como todas as informações pertinentes à perda de pacotes e à tremulação, para auxiliar com possíveis esforços de solução de problemas na tabela inferior.</span><span class="sxs-lookup"><span data-stu-id="16736-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="16736-176">Detalhes de áudio regional</span><span class="sxs-lookup"><span data-stu-id="16736-176">Regional Audio Details</span></span>

<span data-ttu-id="16736-177">O detalhamento de dados de áudio regional mostra especificamente o uso de minutos de áudio para a região selecionada.</span><span class="sxs-lookup"><span data-stu-id="16736-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="16736-178">Os usuários com acesso a CQD podem ver tendências de uso para áudio P2P e de conferência dentro da região selecionada.</span><span class="sxs-lookup"><span data-stu-id="16736-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="16736-179">Na página de Resumo de contagem de chamadas, faça drill-through como região específica na tabela.</span><span class="sxs-lookup"><span data-stu-id="16736-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="16736-180">![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="16736-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="16736-181">Selecione a linha com a região à qual informações adicionais são necessárias.</span><span class="sxs-lookup"><span data-stu-id="16736-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="16736-182">![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="16736-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="16736-183">As tendências de dados mostram um número significativo de minutos sendo usados na rede interna, com a conferência que supera o uso ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="16736-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="16736-184">![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="16736-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="16736-185">A tendência de áudio regional pode ser usada para mostrar como os usuários são afetados por influências externas do mundo.</span><span class="sxs-lookup"><span data-stu-id="16736-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="16736-186">Especificamente, no momento, esperamos ver o uso externo das regiões da EMEA e da Ásia-Pacífico para aumentar com as pessoas sendo solicitadas a trabalhar remotamente.</span><span class="sxs-lookup"><span data-stu-id="16736-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="16736-187">Lista de usuários</span><span class="sxs-lookup"><span data-stu-id="16736-187">User List</span></span>

<span data-ttu-id="16736-188">A lista suspensa de lista de usuários fornece, como pode esperar, informações específicas do usuário para uma hora específica selecionada pela pessoa que está visualizando o relatório.</span><span class="sxs-lookup"><span data-stu-id="16736-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="16736-189">O relatório lista de usuários pode ser acessado por meio de uma busca detalhada no gráfico de tendências horárias no relatório de uso diário.</span><span class="sxs-lookup"><span data-stu-id="16736-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="16736-190">Clique com o botão direito do mouse na hora de informações adicionais são necessárias e selecione Drill through e lista de usuários, conforme mostrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="16736-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="16736-192">O relatório lista de usuários mostra conectividade interna/externa por meio do gráfico de rosca na parte central superior da página.</span><span class="sxs-lookup"><span data-stu-id="16736-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="16736-193">Podemos ver que há uma grande quantidade de participação de fora da rede corporativa na imagem abaixo.</span><span class="sxs-lookup"><span data-stu-id="16736-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="16736-194">O canto superior direito do gráfico mostra o número de chamadas feitas por cada usuário dentro dessa hora.</span><span class="sxs-lookup"><span data-stu-id="16736-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![Captura de tela: relatórios de utilização do teams](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="16736-196">A tabela inferior fornece informações detalhadas para as sessões que cada usuário participou durante essa hora.</span><span class="sxs-lookup"><span data-stu-id="16736-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="16736-197">A coluna tipo de falha é útil para determinar o que causou uma chamada para soltar.</span><span class="sxs-lookup"><span data-stu-id="16736-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="16736-198">As colunas capturar e renderizar dispositivos são úteis para identificar o motivo pelo qual uma chamada foi reportada com má qualidade.</span><span class="sxs-lookup"><span data-stu-id="16736-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="16736-199">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="16736-199">Related topics</span></span>

[<span data-ttu-id="16736-200">Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas</span><span class="sxs-lookup"><span data-stu-id="16736-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="16736-201">Classificação de fluxo no painel de qualidade da chamada</span><span class="sxs-lookup"><span data-stu-id="16736-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="16736-202">Configurar a Análise de Chamada do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="16736-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="16736-203">Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada</span><span class="sxs-lookup"><span data-stu-id="16736-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="16736-204">Análise de Chamada e Painel de Qualidade de Chamadas</span><span class="sxs-lookup"><span data-stu-id="16736-204">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

[<span data-ttu-id="16736-205">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="16736-205">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
 