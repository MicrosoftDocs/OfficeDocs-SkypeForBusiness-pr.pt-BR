---
title: 'Lync Server 2013: usando o painel de monitoramento'
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
ms.openlocfilehash: 643cbc55730d8efb1520ed88c40977c90e35f2fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="af9e3-102">Usando o painel de monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af9e3-102">Using the Monitoring Dashboard in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af9e3-103">_**Última modificação do tópico:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="af9e3-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="af9e3-104">O painel de monitoramento fornece aos administradores uma visão geral rápida da integridade do sistema do Microsoft Lync Server 2013 e do uso do sistema.</span><span class="sxs-lookup"><span data-stu-id="af9e3-104">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="af9e3-105">O painel é projetado para mostrar um modo de exibição de agregação de métricas de sistema principal e fazer isso, exibindo:</span><span class="sxs-lookup"><span data-stu-id="af9e3-105">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="af9e3-106">Totais para o dia atual.</span><span class="sxs-lookup"><span data-stu-id="af9e3-106">Totals for the current day.</span></span> <span data-ttu-id="af9e3-107">Observe que os valores mostrados para o dia atual representam os dados gravados da meia-noite até a hora atual (com base na hora local do servidor de relatórios).</span><span class="sxs-lookup"><span data-stu-id="af9e3-107">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="af9e3-108">Isso significa que você normalmente estará exibindo dados por um dia parcial e não por um período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="af9e3-108">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="af9e3-109">Por exemplo, se a hora local do servidor for 8:00 AM, você verá oito horas de dados, pois há oito horas entre meia-noite e a hora atual de 8:00 AM.</span><span class="sxs-lookup"><span data-stu-id="af9e3-109">For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="af9e3-110">Totais para a semana e totais de tendência das últimas seis semanas.</span><span class="sxs-lookup"><span data-stu-id="af9e3-110">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="af9e3-111">Totais para o mês e os totais de tendência dos últimos seis meses (apenas para uso do sistema).</span><span class="sxs-lookup"><span data-stu-id="af9e3-111">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="af9e3-112">Observe que você pode usar o cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) para retornar a URL usada para acessar os relatórios de monitoramento do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="af9e3-112">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="af9e3-113">Por padrão, o painel de monitoramento mostra dados para as seguintes métricas da semana atual (e os totais de tendência das seis semanas anteriores):</span><span class="sxs-lookup"><span data-stu-id="af9e3-113">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="af9e3-114">Métricas de uso do sistema</span><span class="sxs-lookup"><span data-stu-id="af9e3-114">System Usage Metrics</span></span>

<span data-ttu-id="af9e3-115">**Registro**</span><span class="sxs-lookup"><span data-stu-id="af9e3-115">**Registration**</span></span>

  - <span data-ttu-id="af9e3-116">Logons de usuário exclusivos</span><span class="sxs-lookup"><span data-stu-id="af9e3-116">Unique user logons</span></span>

<span data-ttu-id="af9e3-117">**Ponto a ponto**</span><span class="sxs-lookup"><span data-stu-id="af9e3-117">**Peer-to-peer**</span></span>

  - <span data-ttu-id="af9e3-118">Total de sessões</span><span class="sxs-lookup"><span data-stu-id="af9e3-118">Total sessions</span></span>

  - <span data-ttu-id="af9e3-119">Sessões de IM</span><span class="sxs-lookup"><span data-stu-id="af9e3-119">IM sessions</span></span>

  - <span data-ttu-id="af9e3-120">Sessões de áudio</span><span class="sxs-lookup"><span data-stu-id="af9e3-120">Audio sessions</span></span>

  - <span data-ttu-id="af9e3-121">Sessões de vídeo</span><span class="sxs-lookup"><span data-stu-id="af9e3-121">Video sessions</span></span>

  - <span data-ttu-id="af9e3-122">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="af9e3-122">Application sharing</span></span>

  - <span data-ttu-id="af9e3-123">Total de minutos de sessão de áudio</span><span class="sxs-lookup"><span data-stu-id="af9e3-123">Total audio session minutes</span></span>

  - <span data-ttu-id="af9e3-124">Média de minutos de sessão de áudio</span><span class="sxs-lookup"><span data-stu-id="af9e3-124">Avg. audio session minutes</span></span>

<span data-ttu-id="af9e3-125">**Conferência**</span><span class="sxs-lookup"><span data-stu-id="af9e3-125">**Conference**</span></span>

  - <span data-ttu-id="af9e3-126">Total de conferências</span><span class="sxs-lookup"><span data-stu-id="af9e3-126">Total conferences</span></span>

  - <span data-ttu-id="af9e3-127">Conferências de IM</span><span class="sxs-lookup"><span data-stu-id="af9e3-127">IM conferences</span></span>

  - <span data-ttu-id="af9e3-128">Conferências A/V</span><span class="sxs-lookup"><span data-stu-id="af9e3-128">A/V conferences</span></span>

  - <span data-ttu-id="af9e3-129">Conferências de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="af9e3-129">Application sharing conferences</span></span>

  - <span data-ttu-id="af9e3-130">Webconferências</span><span class="sxs-lookup"><span data-stu-id="af9e3-130">Web conferences</span></span>

  - <span data-ttu-id="af9e3-131">Total de organizadores</span><span class="sxs-lookup"><span data-stu-id="af9e3-131">Total organizers</span></span>

  - <span data-ttu-id="af9e3-132">Total de minutos da conferência A/V</span><span class="sxs-lookup"><span data-stu-id="af9e3-132">Total A/V conference minutes</span></span>

  - <span data-ttu-id="af9e3-133">Contadores. Minutos de conferência A/V</span><span class="sxs-lookup"><span data-stu-id="af9e3-133">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="af9e3-134">Total de conferências PSTN</span><span class="sxs-lookup"><span data-stu-id="af9e3-134">Total PSTN conferences</span></span>

  - <span data-ttu-id="af9e3-135">Total de participantes PSTN</span><span class="sxs-lookup"><span data-stu-id="af9e3-135">Total PSTN participants</span></span>

  - <span data-ttu-id="af9e3-136">Total de minutos de participantes PSTN</span><span class="sxs-lookup"><span data-stu-id="af9e3-136">Total PSTN participant minutes</span></span>

<span data-ttu-id="af9e3-137">Além das métricas de uso do sistema, as métricas a seguir exibem o total do dia atual e dos seis dias anteriores (se você selecionar **exibição Semanal**) ou para a semana atual e as últimas seis semanas se você selecionar **exibição mensal**.</span><span class="sxs-lookup"><span data-stu-id="af9e3-137">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="af9e3-138">Diagnóstico de chamada por usuário</span><span class="sxs-lookup"><span data-stu-id="af9e3-138">Per-User Call Diagnostics</span></span>

<span data-ttu-id="af9e3-139">**Usuários com falhas de chamada**</span><span class="sxs-lookup"><span data-stu-id="af9e3-139">**Users with call failures**</span></span>

  - <span data-ttu-id="af9e3-140">Total de usuários com falhas de chamada</span><span class="sxs-lookup"><span data-stu-id="af9e3-140">Total users with call failures</span></span>

  - <span data-ttu-id="af9e3-141">Organizadores de conferência com falhas de chamada</span><span class="sxs-lookup"><span data-stu-id="af9e3-141">Conference organizers with call failures</span></span>

<span data-ttu-id="af9e3-142">**Usuários com chamadas de baixa qualidade**</span><span class="sxs-lookup"><span data-stu-id="af9e3-142">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="af9e3-143">Total de usuários com chamadas de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="af9e3-143">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="af9e3-144">Diagnóstico de chamada</span><span class="sxs-lookup"><span data-stu-id="af9e3-144">Call Diagnostics</span></span>

<span data-ttu-id="af9e3-145">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="af9e3-145">Peer-to-peer</span></span>

  - <span data-ttu-id="af9e3-146">Total de falhas</span><span class="sxs-lookup"><span data-stu-id="af9e3-146">Total failures</span></span>

  - <span data-ttu-id="af9e3-147">Taxa de falha geral</span><span class="sxs-lookup"><span data-stu-id="af9e3-147">Overall failure rate</span></span>

  - <span data-ttu-id="af9e3-148">Taxa de falha de IM</span><span class="sxs-lookup"><span data-stu-id="af9e3-148">IM failure rate</span></span>

  - <span data-ttu-id="af9e3-149">Taxa de falha de áudio</span><span class="sxs-lookup"><span data-stu-id="af9e3-149">Audio failure rate</span></span>

  - <span data-ttu-id="af9e3-150">Taxa de falha de compartilhamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="af9e3-150">Application sharing failure rate</span></span>

<span data-ttu-id="af9e3-151">Conferência</span><span class="sxs-lookup"><span data-stu-id="af9e3-151">Conference</span></span>

  - <span data-ttu-id="af9e3-152">Total de falhas</span><span class="sxs-lookup"><span data-stu-id="af9e3-152">Total failures</span></span>

  - <span data-ttu-id="af9e3-153">Taxa de falha geral</span><span class="sxs-lookup"><span data-stu-id="af9e3-153">Overall failure rate</span></span>

  - <span data-ttu-id="af9e3-154">Taxa de falha de IM</span><span class="sxs-lookup"><span data-stu-id="af9e3-154">IM failure rate</span></span>

  - <span data-ttu-id="af9e3-155">Taxa de falha de A/V</span><span class="sxs-lookup"><span data-stu-id="af9e3-155">A/V failure rate</span></span>

  - <span data-ttu-id="af9e3-156">Taxa de falha de compartilhamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="af9e3-156">Application sharing failure rate</span></span>

<span data-ttu-id="af9e3-157">Principais cinco servidores por sessões com falha</span><span class="sxs-lookup"><span data-stu-id="af9e3-157">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="af9e3-158">Diagnóstico de qualidade de mídia</span><span class="sxs-lookup"><span data-stu-id="af9e3-158">Media Quality Diagnostics</span></span>

<span data-ttu-id="af9e3-159">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="af9e3-159">Peer-to-peer</span></span>

  - <span data-ttu-id="af9e3-160">Total de chamadas de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="af9e3-160">Total poor quality calls</span></span>

  - <span data-ttu-id="af9e3-161">Porcentagem de chamada de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="af9e3-161">Poor quality call percentage</span></span>

  - <span data-ttu-id="af9e3-162">Chamadas PSTN com baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="af9e3-162">PSTN calls with poor quality</span></span>

<span data-ttu-id="af9e3-163">Conferência</span><span class="sxs-lookup"><span data-stu-id="af9e3-163">Conference</span></span>

  - <span data-ttu-id="af9e3-164">Total de chamadas de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="af9e3-164">Total poor quality calls</span></span>

  - <span data-ttu-id="af9e3-165">Porcentagem de chamada de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="af9e3-165">Poor quality call percentage</span></span>

  - <span data-ttu-id="af9e3-166">Chamadas PSTN com baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="af9e3-166">PSTN calls with poor quality</span></span>

<span data-ttu-id="af9e3-167">Principais servidores por porcentagem de chamadas de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="af9e3-167">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="af9e3-168">Trabalhar com o painel de monitoramento</span><span class="sxs-lookup"><span data-stu-id="af9e3-168">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="af9e3-169">Como observado, os totais padrão são mostrados para a semana atual e os valores de tendência são mostrados nas últimas seis semanas.</span><span class="sxs-lookup"><span data-stu-id="af9e3-169">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="af9e3-170">Se você preferir ver os totais para o mês atual (bem como os valores de tendência dos últimos seis meses), clique no link de **exibição mensal** no canto superior direito do painel.</span><span class="sxs-lookup"><span data-stu-id="af9e3-170">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="af9e3-171">Se você optar por exibir os totais mensais, o texto do link será alterado para **modo de exibição Semanal**.</span><span class="sxs-lookup"><span data-stu-id="af9e3-171">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="af9e3-172">Você pode alternar de volta para o modo de exibição Semanal clicando nesse link.</span><span class="sxs-lookup"><span data-stu-id="af9e3-172">You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="af9e3-173">O painel de monitoramento restringe você a observar os totais da semana atual (ou mês) e os valores de tendência das últimas seis semanas (ou meses).</span><span class="sxs-lookup"><span data-stu-id="af9e3-173">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="af9e3-174">Não é possível alterar essas datas e horas.</span><span class="sxs-lookup"><span data-stu-id="af9e3-174">You cannot change these dates and times.</span></span> <span data-ttu-id="af9e3-175">Por exemplo, você não pode usar o painel para exibir totais de relatório para o período de tempo que começa nove meses atrás.</span><span class="sxs-lookup"><span data-stu-id="af9e3-175">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="af9e3-176">Os valores mostrados nas colunas **esta semana**, **este mês**ou **hoje** o vinculam a informações mais detalhadas sobre o item.</span><span class="sxs-lookup"><span data-stu-id="af9e3-176">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="af9e3-177">Lembre-se de que o nome da coluna e os valores exibidos nessa coluna geralmente diferem dependendo da métrica escolhida e dependendo se você selecionou o modo de exibição semanal ou mensal.</span><span class="sxs-lookup"><span data-stu-id="af9e3-177">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="af9e3-178">Por exemplo, se você clicar nos totais mostrados para a métrica de **logons de usuário exclusivo** , verá o **relatório de registro de usuário** para o período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="af9e3-178">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="af9e3-179">Você pode retornar ao painel de monitoramento a qualquer momento clicando em **painel**.</span><span class="sxs-lookup"><span data-stu-id="af9e3-179">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="af9e3-180">Você também pode acessar a página inicial de relatórios do Monitoring Server clicando no link <STRONG>relatórios</STRONG> no canto superior direito do painel.</span><span class="sxs-lookup"><span data-stu-id="af9e3-180">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="af9e3-181">A coluna **tendência** exibe um gráfico de linhas simples que mostra os totais das últimas seis semanas (ou, dependendo da métrica e do intervalo de tempo, dos últimos seis dias ou dos últimos seis meses).</span><span class="sxs-lookup"><span data-stu-id="af9e3-181">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="af9e3-182">Esses gráficos de linhas simples exibem um ponto de dados não rotulado para cada período de tempo (por exemplo, um ponto de dados não rotulado para cada uma das últimas seis semanas).</span><span class="sxs-lookup"><span data-stu-id="af9e3-182">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="af9e3-183">No entanto, você pode recuperar os valores reais desses gráficos segurando o ponteiro do mouse sobre o gráfico.</span><span class="sxs-lookup"><span data-stu-id="af9e3-183">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="af9e3-184">Nesse caso, uma dica de ferramenta mostra os valores máximo e mínimo no gráfico.</span><span class="sxs-lookup"><span data-stu-id="af9e3-184">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="af9e3-185">Exportando dados do painel de monitoramento</span><span class="sxs-lookup"><span data-stu-id="af9e3-185">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="af9e3-186">O painel de monitoramento oferece várias maneiras de exportar o modo de exibição atual do painel.</span><span class="sxs-lookup"><span data-stu-id="af9e3-186">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="af9e3-187">Na barra de ferramentas painel, você verá um ícone parecido com um disquete com uma seta verde anexada.</span><span class="sxs-lookup"><span data-stu-id="af9e3-187">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="af9e3-188">Se você clicar nesse ícone, uma lista suspensa aparecerá oferecendo os seguintes formatos de exportação de dados:</span><span class="sxs-lookup"><span data-stu-id="af9e3-188">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="af9e3-189">Arquivo XML com dados de relatório</span><span class="sxs-lookup"><span data-stu-id="af9e3-189">XML file with report data</span></span>

  - <span data-ttu-id="af9e3-190">CSV (delimitado por vírgula)</span><span class="sxs-lookup"><span data-stu-id="af9e3-190">CSV (comma delimited)</span></span>

  - <span data-ttu-id="af9e3-191">PDF</span><span class="sxs-lookup"><span data-stu-id="af9e3-191">PDF</span></span>

  - <span data-ttu-id="af9e3-192">MHTML (arquivo da web)</span><span class="sxs-lookup"><span data-stu-id="af9e3-192">MHTML (web archive)</span></span>

  - <span data-ttu-id="af9e3-193">Excel</span><span class="sxs-lookup"><span data-stu-id="af9e3-193">Excel</span></span>

  - <span data-ttu-id="af9e3-194">Arquivo TIFF</span><span class="sxs-lookup"><span data-stu-id="af9e3-194">TIFF file</span></span>

  - <span data-ttu-id="af9e3-195">Word</span><span class="sxs-lookup"><span data-stu-id="af9e3-195">Word</span></span>

<span data-ttu-id="af9e3-196">Para exportar o modo de exibição atual do painel (e seus valores), clique na opção Exportar desejado.</span><span class="sxs-lookup"><span data-stu-id="af9e3-196">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="af9e3-197">O Lync Server 2013 gera um relatório no formato especificado e, em seguida, oferece a opção de abrir esse relatório ou salvá-lo.</span><span class="sxs-lookup"><span data-stu-id="af9e3-197">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="af9e3-198">Observe que, por padrão, o Lync Server títulos o **painel de monitoramento** de relatórios e o salva na pasta downloads.</span><span class="sxs-lookup"><span data-stu-id="af9e3-198">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="af9e3-199">Para dar um nome diferente ao relatório ou para armazená-lo em uma pasta diferente, clique na seta ao lado do botão **salvar** e clique em **salvar como**.</span><span class="sxs-lookup"><span data-stu-id="af9e3-199">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="af9e3-200">Se você estiver bem no **painel de monitoramento** de nome e com o relatório salvo na pasta downloads, basta clicar no botão **salvar** .</span><span class="sxs-lookup"><span data-stu-id="af9e3-200">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="af9e3-201">É possível que, quando você tentar exportar os dados do painel, uma caixa de diálogo de **alerta de segurança** seja exibida junto com a mensagem "as configurações atuais não permitem o download desse arquivo."</span><span class="sxs-lookup"><span data-stu-id="af9e3-201">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="af9e3-202">Se isso ocorrer, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="af9e3-202">If that occurs, do the following:</span></span>

  - <span data-ttu-id="af9e3-203">No Internet Explorer, selecione **Opções da Internet**.</span><span class="sxs-lookup"><span data-stu-id="af9e3-203">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="af9e3-204">Na caixa de diálogo **Opções da Internet** , na guia **segurança** , clique em **sites confiáveis** e em **sites**.</span><span class="sxs-lookup"><span data-stu-id="af9e3-204">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="af9e3-205">Na caixa de diálogo **sites confiáveis** , clique em **Adicionar** para adicionar o Lync Server 2013 que está executando o Lync Server 2013 Reports para as coleções de sites confiáveis.</span><span class="sxs-lookup"><span data-stu-id="af9e3-205">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="af9e3-206">Clique em **fechar** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="af9e3-206">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="af9e3-207">Em seguida, será necessário atualizar o painel de monitoramento antes que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="af9e3-207">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="af9e3-208">Para fazer isso, pressione F5 ou clique no ícone **Atualizar** na barra de ferramentas do painel.</span><span class="sxs-lookup"><span data-stu-id="af9e3-208">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="af9e3-209">(O ícone de **atualização** é um círculo com um par de setas verdes.)</span><span class="sxs-lookup"><span data-stu-id="af9e3-209">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="af9e3-210">Você também pode criar uma planilha do Excel que inclui o Live Data feeds, que inclui links para os dados mais recentes do painel de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="af9e3-210">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="af9e3-211">Para criar um arquivo de feed de dados dinâmicos, clique no ícone de **exportação laranja para alimentação de dados** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="af9e3-211">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="af9e3-212">Se preferir imprimir o painel atual, clique no ícone da impressora na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="af9e3-212">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

