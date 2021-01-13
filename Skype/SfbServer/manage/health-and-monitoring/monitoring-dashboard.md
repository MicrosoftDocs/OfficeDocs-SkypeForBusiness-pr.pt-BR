---
title: Usando o Painel de Monitoramento no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Resumo: saiba mais sobre o Painel de Monitoramento no Skype for Business Server.'
ms.openlocfilehash: 98a96b8a513bad485a25aff76a69d787fb3079b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827781"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="b01f7-103">Usando o Painel de Monitoramento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b01f7-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="b01f7-104">**Resumo:** Saiba mais sobre o Painel de Monitoramento no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b01f7-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="b01f7-105">O Painel de Monitoramento fornece aos administradores uma visão geral rápida da saúde e do uso do sistema do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b01f7-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="b01f7-106">O Painel foi projetado para mostrar uma visão agregada das principais métricas do sistema e para fazer isso exibindo:</span><span class="sxs-lookup"><span data-stu-id="b01f7-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="b01f7-107">Totais do dia atual.</span><span class="sxs-lookup"><span data-stu-id="b01f7-107">Totals for the current day.</span></span> <span data-ttu-id="b01f7-108">Observe que os valores mostrados para o dia atual representam dados que foram gravados da meia-noite até a hora atual (com base na hora local do servidor de relatórios).</span><span class="sxs-lookup"><span data-stu-id="b01f7-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="b01f7-109">Isso significa que você geralmente exibirá dados para um dia parcial e não para um período de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="b01f7-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="b01f7-110">Por exemplo, se a hora local do servidor for 8:00, você verá oito horas de dados porque há oito horas entre meia-noite e a hora atual de 8:00 AM.</span><span class="sxs-lookup"><span data-stu-id="b01f7-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="b01f7-111">Totais da semana e totais de tendência das últimas seis semanas.</span><span class="sxs-lookup"><span data-stu-id="b01f7-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="b01f7-112">Totais do mês e totais de tendência dos últimos seis meses (somente para uso do sistema).</span><span class="sxs-lookup"><span data-stu-id="b01f7-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="b01f7-113">Observe que você pode usar o cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) para retornar a URL usada para acessar os Relatórios de Monitoramento do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="b01f7-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```PowerShell
Get-CsReportingConfiguration
```

<span data-ttu-id="b01f7-114">Por padrão, o Painel de Monitoramento mostra dados para as seguintes métricas da semana atual (e os totais de tendência das seis semanas anteriores):</span><span class="sxs-lookup"><span data-stu-id="b01f7-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="b01f7-115">Métricas de uso do sistema</span><span class="sxs-lookup"><span data-stu-id="b01f7-115">System Usage Metrics</span></span>

 <span data-ttu-id="b01f7-116">**Registro**</span><span class="sxs-lookup"><span data-stu-id="b01f7-116">**Registration**</span></span>
  
- <span data-ttu-id="b01f7-117">Logons de usuário exclusivos</span><span class="sxs-lookup"><span data-stu-id="b01f7-117">Unique user logons</span></span>
    
  <span data-ttu-id="b01f7-118">**Ponto a ponto**</span><span class="sxs-lookup"><span data-stu-id="b01f7-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="b01f7-119">Total de sessões</span><span class="sxs-lookup"><span data-stu-id="b01f7-119">Total sessions</span></span>
    
- <span data-ttu-id="b01f7-120">Sessões de IM</span><span class="sxs-lookup"><span data-stu-id="b01f7-120">IM sessions</span></span>
    
- <span data-ttu-id="b01f7-121">Sessões de áudio</span><span class="sxs-lookup"><span data-stu-id="b01f7-121">Audio sessions</span></span>
    
- <span data-ttu-id="b01f7-122">Sessões de vídeo</span><span class="sxs-lookup"><span data-stu-id="b01f7-122">Video sessions</span></span>
    
- <span data-ttu-id="b01f7-123">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="b01f7-123">Application sharing</span></span>
    
- <span data-ttu-id="b01f7-124">Total de minutos de sessão de áudio</span><span class="sxs-lookup"><span data-stu-id="b01f7-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="b01f7-125">Avg. minutos de sessão de áudio</span><span class="sxs-lookup"><span data-stu-id="b01f7-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="b01f7-126">**Conferência**</span><span class="sxs-lookup"><span data-stu-id="b01f7-126">**Conference**</span></span>
  
- <span data-ttu-id="b01f7-127">Total de conferências</span><span class="sxs-lookup"><span data-stu-id="b01f7-127">Total conferences</span></span>
    
- <span data-ttu-id="b01f7-128">Conferências de IM</span><span class="sxs-lookup"><span data-stu-id="b01f7-128">IM conferences</span></span>
    
- <span data-ttu-id="b01f7-129">Conferências A/V</span><span class="sxs-lookup"><span data-stu-id="b01f7-129">A/V conferences</span></span>
    
- <span data-ttu-id="b01f7-130">Conferências de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="b01f7-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="b01f7-131">Webconferência</span><span class="sxs-lookup"><span data-stu-id="b01f7-131">Web conferences</span></span>
    
- <span data-ttu-id="b01f7-132">Total de organizadores</span><span class="sxs-lookup"><span data-stu-id="b01f7-132">Total organizers</span></span>
    
- <span data-ttu-id="b01f7-133">Total de minutos da conferência A/V</span><span class="sxs-lookup"><span data-stu-id="b01f7-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="b01f7-134">Avg. Minutos de conferência A/V</span><span class="sxs-lookup"><span data-stu-id="b01f7-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="b01f7-135">Total de conferências PSTN</span><span class="sxs-lookup"><span data-stu-id="b01f7-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="b01f7-136">Total de participantes PSTN</span><span class="sxs-lookup"><span data-stu-id="b01f7-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="b01f7-137">Total de minutos de participantes PSTN</span><span class="sxs-lookup"><span data-stu-id="b01f7-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="b01f7-138">Além das métricas de Uso do Sistema, as métricas a seguir exibem o total do dia atual e dos seis dias anteriores (se você selecionar Exibição **Semanal)** ou para a semana atual e as últimas seis semanas se você selecionar Exibição Mensal **.**</span><span class="sxs-lookup"><span data-stu-id="b01f7-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="b01f7-139">Per-User Diagnóstico de Chamada</span><span class="sxs-lookup"><span data-stu-id="b01f7-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="b01f7-140">**Usuários com falhas de chamada**</span><span class="sxs-lookup"><span data-stu-id="b01f7-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="b01f7-141">Total de usuários com falhas de chamada</span><span class="sxs-lookup"><span data-stu-id="b01f7-141">Total users with call failures</span></span>
    
- <span data-ttu-id="b01f7-142">Organizadores de conferência com falhas de chamada</span><span class="sxs-lookup"><span data-stu-id="b01f7-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="b01f7-143">**Usuários com chamadas de baixa qualidade**</span><span class="sxs-lookup"><span data-stu-id="b01f7-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="b01f7-144">Total de usuários com chamadas de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="b01f7-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="b01f7-145">Diagnóstico de Chamada</span><span class="sxs-lookup"><span data-stu-id="b01f7-145">Call Diagnostics</span></span>

<span data-ttu-id="b01f7-146">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="b01f7-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="b01f7-147">Total de falhas</span><span class="sxs-lookup"><span data-stu-id="b01f7-147">Total failures</span></span>
    
- <span data-ttu-id="b01f7-148">Taxa de falha geral</span><span class="sxs-lookup"><span data-stu-id="b01f7-148">Overall failure rate</span></span>
    
- <span data-ttu-id="b01f7-149">Taxa de falha de IM</span><span class="sxs-lookup"><span data-stu-id="b01f7-149">IM failure rate</span></span>
    
- <span data-ttu-id="b01f7-150">Taxa de falha de áudio</span><span class="sxs-lookup"><span data-stu-id="b01f7-150">Audio failure rate</span></span>
    
- <span data-ttu-id="b01f7-151">Taxa de falha de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="b01f7-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="b01f7-152">Conferência</span><span class="sxs-lookup"><span data-stu-id="b01f7-152">Conference</span></span>
  
- <span data-ttu-id="b01f7-153">Total de falhas</span><span class="sxs-lookup"><span data-stu-id="b01f7-153">Total failures</span></span>
    
- <span data-ttu-id="b01f7-154">Taxa de falha geral</span><span class="sxs-lookup"><span data-stu-id="b01f7-154">Overall failure rate</span></span>
    
- <span data-ttu-id="b01f7-155">Taxa de falha de IM</span><span class="sxs-lookup"><span data-stu-id="b01f7-155">IM failure rate</span></span>
    
- <span data-ttu-id="b01f7-156">Taxa de falha de A/V</span><span class="sxs-lookup"><span data-stu-id="b01f7-156">A/V failure rate</span></span>
    
- <span data-ttu-id="b01f7-157">Taxa de falha de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="b01f7-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="b01f7-158">Cinco principais servidores por sessões com falha</span><span class="sxs-lookup"><span data-stu-id="b01f7-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="b01f7-159">Diagnóstico de Qualidade de Mídia</span><span class="sxs-lookup"><span data-stu-id="b01f7-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="b01f7-160">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="b01f7-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="b01f7-161">Total de chamadas de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="b01f7-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="b01f7-162">Percentual de chamada de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="b01f7-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="b01f7-163">Chamadas PSTN com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="b01f7-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="b01f7-164">Conferência</span><span class="sxs-lookup"><span data-stu-id="b01f7-164">Conference</span></span>
  
- <span data-ttu-id="b01f7-165">Total de chamadas de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="b01f7-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="b01f7-166">Percentual de chamada de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="b01f7-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="b01f7-167">Chamadas PSTN com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="b01f7-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="b01f7-168">Principais servidores por percentual de chamada de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="b01f7-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="b01f7-169">Trabalhando com o Painel de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="b01f7-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="b01f7-170">Conforme indicado, os totais padrão são mostrados para a semana atual e os valores de tendência são mostrados nas últimas seis semanas.</span><span class="sxs-lookup"><span data-stu-id="b01f7-170">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="b01f7-171">Se você preferir ver os totais do mês atual (bem como os valores de tendência dos últimos seis meses), clique no **link** Exibição Mensal no canto superior direito do painel.</span><span class="sxs-lookup"><span data-stu-id="b01f7-171">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="b01f7-172">Se você decidir exibir totais mensais, o texto do link mudará para **Exibição Semanal.**</span><span class="sxs-lookup"><span data-stu-id="b01f7-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="b01f7-173">Você pode voltar para a exibição semanal clicando nesse link.</span><span class="sxs-lookup"><span data-stu-id="b01f7-173">You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="b01f7-174">O Painel de Monitoramento restringe a análise dos totais da semana (ou mês) atual e dos valores de tendência das últimas seis semanas (ou meses).</span><span class="sxs-lookup"><span data-stu-id="b01f7-174">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="b01f7-175">Você não pode alterar essas datas e horas.</span><span class="sxs-lookup"><span data-stu-id="b01f7-175">You cannot change these dates and times.</span></span> <span data-ttu-id="b01f7-176">Por exemplo, você não pode usar o Painel para exibir os totais de relatório para o período de tempo que começa há nove meses.</span><span class="sxs-lookup"><span data-stu-id="b01f7-176">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="b01f7-177">Os valores mostrados nas **colunas Esta semana**, **Este mês** ou **Hoje** vinculam você a informações mais detalhadas sobre o item.</span><span class="sxs-lookup"><span data-stu-id="b01f7-177">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="b01f7-178">Tenha em mente que o nome da coluna e os valores exibidos nessa coluna geralmente serão diferentes dependendo da métrica escolhida e dependendo se você selecionou a exibição semanal ou a exibição mensal.</span><span class="sxs-lookup"><span data-stu-id="b01f7-178">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="b01f7-179">Por exemplo, se você clicar nos totais mostrados para  a métrica de **logons** de usuário exclusivos, você verá o Relatório de Registro de Usuário para o período de tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="b01f7-179">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="b01f7-180">Você pode retornar ao Painel de Monitoramento a qualquer momento clicando no **Painel.**</span><span class="sxs-lookup"><span data-stu-id="b01f7-180">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="b01f7-181">Você também pode acessar a home page Relatórios do Monitoring Server clicando no link **Relatórios** no canto superior direito do Painel.</span><span class="sxs-lookup"><span data-stu-id="b01f7-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="b01f7-182">A **coluna Tendência** exibe um gráfico de linha simples que mostra os totais das últimas seis semanas (ou, dependendo da métrica e do intervalo de tempo, dos últimos seis dias ou dos últimos seis meses).</span><span class="sxs-lookup"><span data-stu-id="b01f7-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="b01f7-183">Esses gráficos de linha simples exibem um ponto de dados sem rótulo para cada período de tempo (por exemplo, um ponto de dados sem rótulo para cada uma das últimas seis semanas).</span><span class="sxs-lookup"><span data-stu-id="b01f7-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="b01f7-184">No entanto, você pode recuperar valores reais para esses gráficos segurando o ponteiro do mouse sobre o gráfico.</span><span class="sxs-lookup"><span data-stu-id="b01f7-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="b01f7-185">Nesse caso, uma dica de ferramenta mostra os valores máximo e mínimo no gráfico.</span><span class="sxs-lookup"><span data-stu-id="b01f7-185">In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="b01f7-186">Exportando dados do Painel de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="b01f7-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="b01f7-187">O Painel de Monitoramento oferece várias maneiras de exportar o modo de exibição de painel atual.</span><span class="sxs-lookup"><span data-stu-id="b01f7-187">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="b01f7-188">Na barra de ferramentas Painel, você verá um ícone que se parece com um disquete com uma seta verde anexada a ele.</span><span class="sxs-lookup"><span data-stu-id="b01f7-188">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="b01f7-189">Se você clicar nesse ícone, uma listada será exibida, dando a você os seguintes formatos de exportação de dados:</span><span class="sxs-lookup"><span data-stu-id="b01f7-189">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="b01f7-190">Arquivo XML com dados de relatório</span><span class="sxs-lookup"><span data-stu-id="b01f7-190">XML file with report data</span></span>
    
- <span data-ttu-id="b01f7-191">CSV (delimitado por vírgula)</span><span class="sxs-lookup"><span data-stu-id="b01f7-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="b01f7-192">PDF</span><span class="sxs-lookup"><span data-stu-id="b01f7-192">PDF</span></span>
    
- <span data-ttu-id="b01f7-193">MHTML (arquivo da web)</span><span class="sxs-lookup"><span data-stu-id="b01f7-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="b01f7-194">Excel</span><span class="sxs-lookup"><span data-stu-id="b01f7-194">Excel</span></span>
    
- <span data-ttu-id="b01f7-195">Arquivo TIFF</span><span class="sxs-lookup"><span data-stu-id="b01f7-195">TIFF file</span></span>
    
- <span data-ttu-id="b01f7-196">Word</span><span class="sxs-lookup"><span data-stu-id="b01f7-196">Word</span></span>
    
<span data-ttu-id="b01f7-197">Para exportar a exibição do painel atual (e seus valores), clique na opção de exportação desejada.</span><span class="sxs-lookup"><span data-stu-id="b01f7-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="b01f7-198">O Skype for Business Server gera um relatório no formato especificado e dá a você a opção de abrir ou salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="b01f7-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="b01f7-199">Observe que, por padrão, o Skype  for Business Server chama o Painel de Monitoramento do relatório e o salva na pasta Downloads.</span><span class="sxs-lookup"><span data-stu-id="b01f7-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="b01f7-200">Para dar ao relatório um nome diferente ou armazená-lo em  uma pasta diferente, clique na seta ao lado do botão Salvar e clique em **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="b01f7-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="b01f7-201">Se você não tiver problemas com o nome **Painel** de Monitoramento e se o relatório for salvo na pasta Downloads, basta clicar no **botão** Salvar.</span><span class="sxs-lookup"><span data-stu-id="b01f7-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="b01f7-202">É possível que, ao tentar exportar dados do painel, uma caixa de diálogo Alerta de Segurança apareça junto com **a** mensagem "Suas configurações atuais não permitem que este arquivo seja baixado".</span><span class="sxs-lookup"><span data-stu-id="b01f7-202">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="b01f7-203">Se isso ocorrer, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b01f7-203">If that occurs, do the following:</span></span>
  
- <span data-ttu-id="b01f7-204">No Internet Explorer, selecione **Opções da Internet.**</span><span class="sxs-lookup"><span data-stu-id="b01f7-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="b01f7-205">Na caixa de diálogo Opções da **Internet,** **na** guia Segurança, clique em **Sites** Confiáveis e em **Sites.**</span><span class="sxs-lookup"><span data-stu-id="b01f7-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="b01f7-206">Na caixa **de diálogo**  Sites confiáveis, clique em Adicionar para adicionar o Skype for Business Server que está executando os Relatórios do Skype for Business Server aos conjunto de sites confiáveis.</span><span class="sxs-lookup"><span data-stu-id="b01f7-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="b01f7-207">Clique **em Fechar** e em **OK.**</span><span class="sxs-lookup"><span data-stu-id="b01f7-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="b01f7-208">Em seguida, você precisará atualizar o Painel de Monitoramento antes que as alterações entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="b01f7-208">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="b01f7-209">Para fazer isso, pressione F5 ou clique **no** ícone Atualizar na barra de ferramentas Painel.</span><span class="sxs-lookup"><span data-stu-id="b01f7-209">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="b01f7-210">(O **ícone Atualizar** é um círculo com um par de setas verdes.)</span><span class="sxs-lookup"><span data-stu-id="b01f7-210">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="b01f7-211">Você também pode criar uma planilha do Excel que inclua feeds de dados ao vivo, que inclui links para os dados mais recentes do Painel de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="b01f7-211">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="b01f7-212">Para criar um arquivo de feed de dados ao vivo, clique no ícone laranja Exportar para **Feed de** Dados na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="b01f7-212">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="b01f7-213">Se você preferir imprimir o Painel atual, clique no ícone da impressora na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="b01f7-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

