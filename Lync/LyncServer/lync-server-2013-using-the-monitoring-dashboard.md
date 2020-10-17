---
title: 'Lync Server 2013: usando o painel de monitoramento'
description: 'Lync Server 2013: usando o painel de monitoramento.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8a68fa1e55b7d0b8305c53802ddabaa904fa214
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556037"
---
# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="e45a7-103">Usando o painel de monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e45a7-103">Using the Monitoring Dashboard in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e45a7-104">_**Última modificação do tópico:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="e45a7-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="e45a7-105">O painel de monitoramento fornece aos administradores uma visão geral rápida da integridade do sistema do Microsoft Lync Server 2013 e do uso do sistema.</span><span class="sxs-lookup"><span data-stu-id="e45a7-105">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="e45a7-106">O painel é projetado para mostrar um modo de exibição de agregação de métricas de sistema principal e fazer isso, exibindo:</span><span class="sxs-lookup"><span data-stu-id="e45a7-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="e45a7-107">Totais para o dia atual.</span><span class="sxs-lookup"><span data-stu-id="e45a7-107">Totals for the current day.</span></span> <span data-ttu-id="e45a7-108">Observe que os valores mostrados para o dia atual representam os dados gravados da meia-noite até a hora atual (com base na hora local do servidor de relatórios).</span><span class="sxs-lookup"><span data-stu-id="e45a7-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="e45a7-109">Isso significa que você normalmente estará exibindo dados por um dia parcial e não por um período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="e45a7-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="e45a7-110">Por exemplo, se a hora local do servidor for 8:00 AM, você verá oito horas de dados, pois há oito horas entre meia-noite e a hora atual de 8:00 AM.</span><span class="sxs-lookup"><span data-stu-id="e45a7-110">For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="e45a7-111">Totais para a semana e totais de tendência das últimas seis semanas.</span><span class="sxs-lookup"><span data-stu-id="e45a7-111">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="e45a7-112">Totais para o mês e os totais de tendência dos últimos seis meses (apenas para uso do sistema).</span><span class="sxs-lookup"><span data-stu-id="e45a7-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="e45a7-113">Observe que você pode usar o cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) para retornar a URL usada para acessar os relatórios de monitoramento do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="e45a7-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="e45a7-114">Por padrão, o painel de monitoramento mostra dados para as seguintes métricas da semana atual (e os totais de tendência das seis semanas anteriores):</span><span class="sxs-lookup"><span data-stu-id="e45a7-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="e45a7-115">Métricas de uso do sistema</span><span class="sxs-lookup"><span data-stu-id="e45a7-115">System Usage Metrics</span></span>

<span data-ttu-id="e45a7-116">**Registro**</span><span class="sxs-lookup"><span data-stu-id="e45a7-116">**Registration**</span></span>

  - <span data-ttu-id="e45a7-117">Logons de usuário exclusivos</span><span class="sxs-lookup"><span data-stu-id="e45a7-117">Unique user logons</span></span>

<span data-ttu-id="e45a7-118">**Ponto a ponto**</span><span class="sxs-lookup"><span data-stu-id="e45a7-118">**Peer-to-peer**</span></span>

  - <span data-ttu-id="e45a7-119">Total de sessões</span><span class="sxs-lookup"><span data-stu-id="e45a7-119">Total sessions</span></span>

  - <span data-ttu-id="e45a7-120">Sessões de IM</span><span class="sxs-lookup"><span data-stu-id="e45a7-120">IM sessions</span></span>

  - <span data-ttu-id="e45a7-121">Sessões de áudio</span><span class="sxs-lookup"><span data-stu-id="e45a7-121">Audio sessions</span></span>

  - <span data-ttu-id="e45a7-122">Sessões de vídeo</span><span class="sxs-lookup"><span data-stu-id="e45a7-122">Video sessions</span></span>

  - <span data-ttu-id="e45a7-123">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="e45a7-123">Application sharing</span></span>

  - <span data-ttu-id="e45a7-124">Total de minutos de sessão de áudio</span><span class="sxs-lookup"><span data-stu-id="e45a7-124">Total audio session minutes</span></span>

  - <span data-ttu-id="e45a7-125">Média de minutos de sessão de áudio</span><span class="sxs-lookup"><span data-stu-id="e45a7-125">Avg. audio session minutes</span></span>

<span data-ttu-id="e45a7-126">**Conferência**</span><span class="sxs-lookup"><span data-stu-id="e45a7-126">**Conference**</span></span>

  - <span data-ttu-id="e45a7-127">Total de conferências</span><span class="sxs-lookup"><span data-stu-id="e45a7-127">Total conferences</span></span>

  - <span data-ttu-id="e45a7-128">Conferências de IM</span><span class="sxs-lookup"><span data-stu-id="e45a7-128">IM conferences</span></span>

  - <span data-ttu-id="e45a7-129">Conferências A/V</span><span class="sxs-lookup"><span data-stu-id="e45a7-129">A/V conferences</span></span>

  - <span data-ttu-id="e45a7-130">Conferências de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="e45a7-130">Application sharing conferences</span></span>

  - <span data-ttu-id="e45a7-131">Webconferências</span><span class="sxs-lookup"><span data-stu-id="e45a7-131">Web conferences</span></span>

  - <span data-ttu-id="e45a7-132">Total de organizadores</span><span class="sxs-lookup"><span data-stu-id="e45a7-132">Total organizers</span></span>

  - <span data-ttu-id="e45a7-133">Total de minutos da conferência A/V</span><span class="sxs-lookup"><span data-stu-id="e45a7-133">Total A/V conference minutes</span></span>

  - <span data-ttu-id="e45a7-134">Contadores. Minutos de conferência A/V</span><span class="sxs-lookup"><span data-stu-id="e45a7-134">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="e45a7-135">Total de conferências PSTN</span><span class="sxs-lookup"><span data-stu-id="e45a7-135">Total PSTN conferences</span></span>

  - <span data-ttu-id="e45a7-136">Total de participantes PSTN</span><span class="sxs-lookup"><span data-stu-id="e45a7-136">Total PSTN participants</span></span>

  - <span data-ttu-id="e45a7-137">Total de minutos de participantes PSTN</span><span class="sxs-lookup"><span data-stu-id="e45a7-137">Total PSTN participant minutes</span></span>

<span data-ttu-id="e45a7-138">Além das métricas de uso do sistema, as métricas a seguir exibem o total do dia atual e dos seis dias anteriores (se você selecionar **exibição Semanal**) ou para a semana atual e as últimas seis semanas se você selecionar **exibição mensal**.</span><span class="sxs-lookup"><span data-stu-id="e45a7-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="e45a7-139">Per-User diagnóstico de chamadas</span><span class="sxs-lookup"><span data-stu-id="e45a7-139">Per-User Call Diagnostics</span></span>

<span data-ttu-id="e45a7-140">**Usuários com falhas de chamada**</span><span class="sxs-lookup"><span data-stu-id="e45a7-140">**Users with call failures**</span></span>

  - <span data-ttu-id="e45a7-141">Total de usuários com falhas de chamada</span><span class="sxs-lookup"><span data-stu-id="e45a7-141">Total users with call failures</span></span>

  - <span data-ttu-id="e45a7-142">Organizadores de conferência com falhas de chamada</span><span class="sxs-lookup"><span data-stu-id="e45a7-142">Conference organizers with call failures</span></span>

<span data-ttu-id="e45a7-143">**Usuários com chamadas de baixa qualidade**</span><span class="sxs-lookup"><span data-stu-id="e45a7-143">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="e45a7-144">Total de usuários com chamadas de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="e45a7-144">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="e45a7-145">Diagnóstico de chamada</span><span class="sxs-lookup"><span data-stu-id="e45a7-145">Call Diagnostics</span></span>

<span data-ttu-id="e45a7-146">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="e45a7-146">Peer-to-peer</span></span>

  - <span data-ttu-id="e45a7-147">Total de falhas</span><span class="sxs-lookup"><span data-stu-id="e45a7-147">Total failures</span></span>

  - <span data-ttu-id="e45a7-148">Taxa de falha geral</span><span class="sxs-lookup"><span data-stu-id="e45a7-148">Overall failure rate</span></span>

  - <span data-ttu-id="e45a7-149">Taxa de falha de IM</span><span class="sxs-lookup"><span data-stu-id="e45a7-149">IM failure rate</span></span>

  - <span data-ttu-id="e45a7-150">Taxa de falha de áudio</span><span class="sxs-lookup"><span data-stu-id="e45a7-150">Audio failure rate</span></span>

  - <span data-ttu-id="e45a7-151">Taxa de falha de compartilhamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="e45a7-151">Application sharing failure rate</span></span>

<span data-ttu-id="e45a7-152">Conferência</span><span class="sxs-lookup"><span data-stu-id="e45a7-152">Conference</span></span>

  - <span data-ttu-id="e45a7-153">Total de falhas</span><span class="sxs-lookup"><span data-stu-id="e45a7-153">Total failures</span></span>

  - <span data-ttu-id="e45a7-154">Taxa de falha geral</span><span class="sxs-lookup"><span data-stu-id="e45a7-154">Overall failure rate</span></span>

  - <span data-ttu-id="e45a7-155">Taxa de falha de IM</span><span class="sxs-lookup"><span data-stu-id="e45a7-155">IM failure rate</span></span>

  - <span data-ttu-id="e45a7-156">Taxa de falha de A/V</span><span class="sxs-lookup"><span data-stu-id="e45a7-156">A/V failure rate</span></span>

  - <span data-ttu-id="e45a7-157">Taxa de falha de compartilhamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="e45a7-157">Application sharing failure rate</span></span>

<span data-ttu-id="e45a7-158">Principais cinco servidores por sessões com falha</span><span class="sxs-lookup"><span data-stu-id="e45a7-158">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="e45a7-159">Diagnóstico de qualidade de mídia</span><span class="sxs-lookup"><span data-stu-id="e45a7-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="e45a7-160">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="e45a7-160">Peer-to-peer</span></span>

  - <span data-ttu-id="e45a7-161">Total de chamadas de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="e45a7-161">Total poor quality calls</span></span>

  - <span data-ttu-id="e45a7-162">Porcentagem de chamada de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="e45a7-162">Poor quality call percentage</span></span>

  - <span data-ttu-id="e45a7-163">Chamadas PSTN com baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="e45a7-163">PSTN calls with poor quality</span></span>

<span data-ttu-id="e45a7-164">Conferência</span><span class="sxs-lookup"><span data-stu-id="e45a7-164">Conference</span></span>

  - <span data-ttu-id="e45a7-165">Total de chamadas de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="e45a7-165">Total poor quality calls</span></span>

  - <span data-ttu-id="e45a7-166">Porcentagem de chamada de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="e45a7-166">Poor quality call percentage</span></span>

  - <span data-ttu-id="e45a7-167">Chamadas PSTN com baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="e45a7-167">PSTN calls with poor quality</span></span>

<span data-ttu-id="e45a7-168">Principais servidores por porcentagem de chamadas de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="e45a7-168">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="e45a7-169">Trabalhar com o painel de monitoramento</span><span class="sxs-lookup"><span data-stu-id="e45a7-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="e45a7-170">Como observado, os totais padrão são mostrados para a semana atual e os valores de tendência são mostrados nas últimas seis semanas.</span><span class="sxs-lookup"><span data-stu-id="e45a7-170">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="e45a7-171">Se você preferir ver os totais para o mês atual (bem como os valores de tendência dos últimos seis meses), clique no link de **exibição mensal** no canto superior direito do painel.</span><span class="sxs-lookup"><span data-stu-id="e45a7-171">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="e45a7-172">Se você optar por exibir os totais mensais, o texto do link será alterado para **modo de exibição Semanal**.</span><span class="sxs-lookup"><span data-stu-id="e45a7-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="e45a7-173">Você pode alternar de volta para o modo de exibição Semanal clicando nesse link.</span><span class="sxs-lookup"><span data-stu-id="e45a7-173">You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="e45a7-174">O painel de monitoramento restringe você a observar os totais da semana atual (ou mês) e os valores de tendência das últimas seis semanas (ou meses).</span><span class="sxs-lookup"><span data-stu-id="e45a7-174">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="e45a7-175">Não é possível alterar essas datas e horas.</span><span class="sxs-lookup"><span data-stu-id="e45a7-175">You cannot change these dates and times.</span></span> <span data-ttu-id="e45a7-176">Por exemplo, você não pode usar o painel para exibir totais de relatório para o período de tempo que começa nove meses atrás.</span><span class="sxs-lookup"><span data-stu-id="e45a7-176">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="e45a7-177">Os valores mostrados nas colunas **esta semana**, **este mês**ou **hoje** o vinculam a informações mais detalhadas sobre o item.</span><span class="sxs-lookup"><span data-stu-id="e45a7-177">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="e45a7-178">Lembre-se de que o nome da coluna e os valores exibidos nessa coluna geralmente diferem dependendo da métrica escolhida e dependendo se você selecionou o modo de exibição semanal ou mensal.</span><span class="sxs-lookup"><span data-stu-id="e45a7-178">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="e45a7-179">Por exemplo, se você clicar nos totais mostrados para a métrica de **logons de usuário exclusivo** , verá o **relatório de registro de usuário** para o período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="e45a7-179">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="e45a7-180">Você pode retornar ao painel de monitoramento a qualquer momento clicando em **painel**.</span><span class="sxs-lookup"><span data-stu-id="e45a7-180">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="e45a7-181">Você também pode acessar a página inicial de relatórios do Monitoring Server clicando no link <STRONG>relatórios</STRONG> no canto superior direito do painel.</span><span class="sxs-lookup"><span data-stu-id="e45a7-181">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="e45a7-182">A coluna **tendência** exibe um gráfico de linhas simples que mostra os totais das últimas seis semanas (ou, dependendo da métrica e do intervalo de tempo, dos últimos seis dias ou dos últimos seis meses).</span><span class="sxs-lookup"><span data-stu-id="e45a7-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="e45a7-183">Esses gráficos de linhas simples exibem um ponto de dados não rotulado para cada período de tempo (por exemplo, um ponto de dados não rotulado para cada uma das últimas seis semanas).</span><span class="sxs-lookup"><span data-stu-id="e45a7-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="e45a7-184">No entanto, você pode recuperar os valores reais desses gráficos segurando o ponteiro do mouse sobre o gráfico.</span><span class="sxs-lookup"><span data-stu-id="e45a7-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="e45a7-185">Nesse caso, uma dica de ferramenta mostra os valores máximo e mínimo no gráfico.</span><span class="sxs-lookup"><span data-stu-id="e45a7-185">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="e45a7-186">Exportando dados do painel de monitoramento</span><span class="sxs-lookup"><span data-stu-id="e45a7-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="e45a7-187">O painel de monitoramento oferece várias maneiras de exportar o modo de exibição atual do painel.</span><span class="sxs-lookup"><span data-stu-id="e45a7-187">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="e45a7-188">Na barra de ferramentas painel, você verá um ícone parecido com um disquete com uma seta verde anexada.</span><span class="sxs-lookup"><span data-stu-id="e45a7-188">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="e45a7-189">Se você clicar nesse ícone, uma lista suspensa aparecerá oferecendo os seguintes formatos de exportação de dados:</span><span class="sxs-lookup"><span data-stu-id="e45a7-189">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="e45a7-190">Arquivo XML com dados de relatório</span><span class="sxs-lookup"><span data-stu-id="e45a7-190">XML file with report data</span></span>

  - <span data-ttu-id="e45a7-191">CSV (delimitado por vírgula)</span><span class="sxs-lookup"><span data-stu-id="e45a7-191">CSV (comma delimited)</span></span>

  - <span data-ttu-id="e45a7-192">PDF</span><span class="sxs-lookup"><span data-stu-id="e45a7-192">PDF</span></span>

  - <span data-ttu-id="e45a7-193">MHTML (arquivo da web)</span><span class="sxs-lookup"><span data-stu-id="e45a7-193">MHTML (web archive)</span></span>

  - <span data-ttu-id="e45a7-194">Excel</span><span class="sxs-lookup"><span data-stu-id="e45a7-194">Excel</span></span>

  - <span data-ttu-id="e45a7-195">Arquivo TIFF</span><span class="sxs-lookup"><span data-stu-id="e45a7-195">TIFF file</span></span>

  - <span data-ttu-id="e45a7-196">Word</span><span class="sxs-lookup"><span data-stu-id="e45a7-196">Word</span></span>

<span data-ttu-id="e45a7-197">Para exportar o modo de exibição atual do painel (e seus valores), clique na opção Exportar desejado.</span><span class="sxs-lookup"><span data-stu-id="e45a7-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="e45a7-198">O Lync Server 2013 gera um relatório no formato especificado e, em seguida, oferece a opção de abrir esse relatório ou salvá-lo.</span><span class="sxs-lookup"><span data-stu-id="e45a7-198">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="e45a7-199">Observe que, por padrão, o Lync Server títulos o **painel de monitoramento** de relatórios e o salva na pasta downloads.</span><span class="sxs-lookup"><span data-stu-id="e45a7-199">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="e45a7-200">Para dar um nome diferente ao relatório ou para armazená-lo em uma pasta diferente, clique na seta ao lado do botão **salvar** e clique em **salvar como**.</span><span class="sxs-lookup"><span data-stu-id="e45a7-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="e45a7-201">Se você estiver bem no **painel de monitoramento** de nome e com o relatório salvo na pasta downloads, basta clicar no botão **salvar** .</span><span class="sxs-lookup"><span data-stu-id="e45a7-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="e45a7-202">É possível que, quando você tentar exportar os dados do painel, uma caixa de diálogo de **alerta de segurança** seja exibida junto com a mensagem "as configurações atuais não permitem o download desse arquivo."</span><span class="sxs-lookup"><span data-stu-id="e45a7-202">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="e45a7-203">Se isso ocorrer, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e45a7-203">If that occurs, do the following:</span></span>

  - <span data-ttu-id="e45a7-204">No Internet Explorer, selecione **Opções da Internet**.</span><span class="sxs-lookup"><span data-stu-id="e45a7-204">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="e45a7-205">Na caixa de diálogo **Opções da Internet** , na guia **segurança** , clique em **sites confiáveis** e em **sites**.</span><span class="sxs-lookup"><span data-stu-id="e45a7-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="e45a7-206">Na caixa de diálogo **sites confiáveis** , clique em **Adicionar** para adicionar o Lync Server 2013 que está executando o Lync Server 2013 Reports para as coleções de sites confiáveis.</span><span class="sxs-lookup"><span data-stu-id="e45a7-206">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="e45a7-207">Clique em **fechar** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e45a7-207">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="e45a7-208">Em seguida, será necessário atualizar o painel de monitoramento antes que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="e45a7-208">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="e45a7-209">Para fazer isso, pressione F5 ou clique no ícone **Atualizar** na barra de ferramentas do painel.</span><span class="sxs-lookup"><span data-stu-id="e45a7-209">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="e45a7-210">(O ícone de **atualização** é um círculo com um par de setas verdes.)</span><span class="sxs-lookup"><span data-stu-id="e45a7-210">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="e45a7-211">Você também pode criar uma planilha do Excel que inclui o Live Data feeds, que inclui links para os dados mais recentes do painel de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="e45a7-211">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="e45a7-212">Para criar um arquivo de feed de dados dinâmicos, clique no ícone de **exportação laranja para alimentação de dados** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="e45a7-212">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="e45a7-213">Se preferir imprimir o painel atual, clique no ícone da impressora na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="e45a7-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

