---
title: 'Lync Server 2013: usando o painel Monitoramento'
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
ms.openlocfilehash: 929d0fbc650a7b067d86738e5ded176a15c511f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="acb7b-102">Usando o painel Monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acb7b-102">Using the Monitoring Dashboard in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acb7b-103">_**Tópico da última modificação:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="acb7b-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="acb7b-104">O painel Monitoramento fornece aos administradores uma rápida visão geral da integridade do sistema do Microsoft Lync Server 2013 e do uso do sistema.</span><span class="sxs-lookup"><span data-stu-id="acb7b-104">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="acb7b-105">O Painel foi projetado para fornecer uma exibição agregada das principais métricas do sistema e para fazer isso exibindo:</span><span class="sxs-lookup"><span data-stu-id="acb7b-105">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="acb7b-p102">Os totais para o dia atual. Observe que os valores mostrados para o dia atual representam dados que foram gravados da meia-noite até a hora atual (com base na hora local do servidor de relatório). Isso significa que você geralmente estará vendo dados referentes a um dia parcial, não a um período de 24 horas. Por exemplo, se a hora local do servidor for 8:00 da manhã, você verá oito horas de dados porque há oito horas entre meia-noite e a hora atual de 8:00 da manhã.</span><span class="sxs-lookup"><span data-stu-id="acb7b-p102">Totals for the current day. Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server). That means that you will typically be viewing data for a partial day and not for a 24-hour period. For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="acb7b-110">Totais para a semana e totais de tendência das últimas seis semanas.</span><span class="sxs-lookup"><span data-stu-id="acb7b-110">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="acb7b-111">Totais para o mês e os totais de tendência dos últimos seis meses (apenas para uso do sistema).</span><span class="sxs-lookup"><span data-stu-id="acb7b-111">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="acb7b-112">Observe que você pode usar o cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) para retornar a URL usada para acessar os relatórios de monitoramento do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="acb7b-112">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="acb7b-113">Por padrão, o Painel de Monitoramento mostra dados para as seguintes métricas da semana atual (e os totais de tendência das seis semanas anteriores):</span><span class="sxs-lookup"><span data-stu-id="acb7b-113">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="acb7b-114">Métricas de uso do sistema</span><span class="sxs-lookup"><span data-stu-id="acb7b-114">System Usage Metrics</span></span>

<span data-ttu-id="acb7b-115">**Registro**</span><span class="sxs-lookup"><span data-stu-id="acb7b-115">**Registration**</span></span>

  - <span data-ttu-id="acb7b-116">Logons de usuário exclusivos</span><span class="sxs-lookup"><span data-stu-id="acb7b-116">Unique user logons</span></span>

<span data-ttu-id="acb7b-117">**Ponto a ponto**</span><span class="sxs-lookup"><span data-stu-id="acb7b-117">**Peer-to-peer**</span></span>

  - <span data-ttu-id="acb7b-118">Total de sessões</span><span class="sxs-lookup"><span data-stu-id="acb7b-118">Total sessions</span></span>

  - <span data-ttu-id="acb7b-119">Sessões de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="acb7b-119">IM sessions</span></span>

  - <span data-ttu-id="acb7b-120">Sessões de áudio</span><span class="sxs-lookup"><span data-stu-id="acb7b-120">Audio sessions</span></span>

  - <span data-ttu-id="acb7b-121">Sessões de vídeo</span><span class="sxs-lookup"><span data-stu-id="acb7b-121">Video sessions</span></span>

  - <span data-ttu-id="acb7b-122">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="acb7b-122">Application sharing</span></span>

  - <span data-ttu-id="acb7b-123">Total de minutos da sessão de áudio</span><span class="sxs-lookup"><span data-stu-id="acb7b-123">Total audio session minutes</span></span>

  - <span data-ttu-id="acb7b-124">Média de minutos da sessão de áudio</span><span class="sxs-lookup"><span data-stu-id="acb7b-124">Avg. audio session minutes</span></span>

<span data-ttu-id="acb7b-125">**Conferência**</span><span class="sxs-lookup"><span data-stu-id="acb7b-125">**Conference**</span></span>

  - <span data-ttu-id="acb7b-126">Total de conferências</span><span class="sxs-lookup"><span data-stu-id="acb7b-126">Total conferences</span></span>

  - <span data-ttu-id="acb7b-127">Conferências de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="acb7b-127">IM conferences</span></span>

  - <span data-ttu-id="acb7b-128">Conferências A/V</span><span class="sxs-lookup"><span data-stu-id="acb7b-128">A/V conferences</span></span>

  - <span data-ttu-id="acb7b-129">Conferências de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="acb7b-129">Application sharing conferences</span></span>

  - <span data-ttu-id="acb7b-130">Webconferências</span><span class="sxs-lookup"><span data-stu-id="acb7b-130">Web conferences</span></span>

  - <span data-ttu-id="acb7b-131">Total de organizadores</span><span class="sxs-lookup"><span data-stu-id="acb7b-131">Total organizers</span></span>

  - <span data-ttu-id="acb7b-132">Total de minutos da conferência A/V</span><span class="sxs-lookup"><span data-stu-id="acb7b-132">Total A/V conference minutes</span></span>

  - <span data-ttu-id="acb7b-133">Média de minutos da conferência A/V</span><span class="sxs-lookup"><span data-stu-id="acb7b-133">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="acb7b-134">Total de conferências PSTN</span><span class="sxs-lookup"><span data-stu-id="acb7b-134">Total PSTN conferences</span></span>

  - <span data-ttu-id="acb7b-135">Total de participantes PSTN</span><span class="sxs-lookup"><span data-stu-id="acb7b-135">Total PSTN participants</span></span>

  - <span data-ttu-id="acb7b-136">Total de minutos dos participantes PSTN</span><span class="sxs-lookup"><span data-stu-id="acb7b-136">Total PSTN participant minutes</span></span>

<span data-ttu-id="acb7b-137">Além das métricas de Uso do Sistema, as seguintes métricas exibem o total para o dia atual e os seis dias anteriores (se você selecionar **Exibição Semanal**) ou para a semana atual e as últimas seis semanas se você selecionar **Exibição Mensal**.</span><span class="sxs-lookup"><span data-stu-id="acb7b-137">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="acb7b-138">Diagnóstico de chamada por usuário</span><span class="sxs-lookup"><span data-stu-id="acb7b-138">Per-User Call Diagnostics</span></span>

<span data-ttu-id="acb7b-139">**Usuários com falhas na chamada**</span><span class="sxs-lookup"><span data-stu-id="acb7b-139">**Users with call failures**</span></span>

  - <span data-ttu-id="acb7b-140">Total de usuários com falhas de chamada</span><span class="sxs-lookup"><span data-stu-id="acb7b-140">Total users with call failures</span></span>

  - <span data-ttu-id="acb7b-141">Organizadores de conferência com falhas de chamada</span><span class="sxs-lookup"><span data-stu-id="acb7b-141">Conference organizers with call failures</span></span>

<span data-ttu-id="acb7b-142">**Usuários com chamadas com qualidade ruim**</span><span class="sxs-lookup"><span data-stu-id="acb7b-142">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="acb7b-143">Total de usuários com chamadas de baixa qualidade</span><span class="sxs-lookup"><span data-stu-id="acb7b-143">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="acb7b-144">Diagnóstico de Chamadas</span><span class="sxs-lookup"><span data-stu-id="acb7b-144">Call Diagnostics</span></span>

<span data-ttu-id="acb7b-145">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="acb7b-145">Peer-to-peer</span></span>

  - <span data-ttu-id="acb7b-146">Total de falhas</span><span class="sxs-lookup"><span data-stu-id="acb7b-146">Total failures</span></span>

  - <span data-ttu-id="acb7b-147">Taxa de falha geral</span><span class="sxs-lookup"><span data-stu-id="acb7b-147">Overall failure rate</span></span>

  - <span data-ttu-id="acb7b-148">Taxa de falha de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="acb7b-148">IM failure rate</span></span>

  - <span data-ttu-id="acb7b-149">Taxa de falha de áudio</span><span class="sxs-lookup"><span data-stu-id="acb7b-149">Audio failure rate</span></span>

  - <span data-ttu-id="acb7b-150">Taxa de falha de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="acb7b-150">Application sharing failure rate</span></span>

<span data-ttu-id="acb7b-151">Conferência</span><span class="sxs-lookup"><span data-stu-id="acb7b-151">Conference</span></span>

  - <span data-ttu-id="acb7b-152">Total de falhas</span><span class="sxs-lookup"><span data-stu-id="acb7b-152">Total failures</span></span>

  - <span data-ttu-id="acb7b-153">Taxa de falha geral</span><span class="sxs-lookup"><span data-stu-id="acb7b-153">Overall failure rate</span></span>

  - <span data-ttu-id="acb7b-154">Taxa de falha de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="acb7b-154">IM failure rate</span></span>

  - <span data-ttu-id="acb7b-155">Taxa de falha de A/V</span><span class="sxs-lookup"><span data-stu-id="acb7b-155">A/V failure rate</span></span>

  - <span data-ttu-id="acb7b-156">Taxa de falha de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="acb7b-156">Application sharing failure rate</span></span>

<span data-ttu-id="acb7b-157">Principais cinco servidores por sessões de falha</span><span class="sxs-lookup"><span data-stu-id="acb7b-157">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="acb7b-158">Diagnóstico de Qualidade de Mídia</span><span class="sxs-lookup"><span data-stu-id="acb7b-158">Media Quality Diagnostics</span></span>

<span data-ttu-id="acb7b-159">Ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="acb7b-159">Peer-to-peer</span></span>

  - <span data-ttu-id="acb7b-160">Total de chamadas com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="acb7b-160">Total poor quality calls</span></span>

  - <span data-ttu-id="acb7b-161">Percentual de chamadas com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="acb7b-161">Poor quality call percentage</span></span>

  - <span data-ttu-id="acb7b-162">Chamadas PSTN com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="acb7b-162">PSTN calls with poor quality</span></span>

<span data-ttu-id="acb7b-163">Conferência</span><span class="sxs-lookup"><span data-stu-id="acb7b-163">Conference</span></span>

  - <span data-ttu-id="acb7b-164">Total de chamadas com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="acb7b-164">Total poor quality calls</span></span>

  - <span data-ttu-id="acb7b-165">Percentual de chamadas com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="acb7b-165">Poor quality call percentage</span></span>

  - <span data-ttu-id="acb7b-166">Chamadas PSTN com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="acb7b-166">PSTN calls with poor quality</span></span>

<span data-ttu-id="acb7b-167">Piores servidores por percentual de chamadas com qualidade ruim</span><span class="sxs-lookup"><span data-stu-id="acb7b-167">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="acb7b-168">Trabalhando com o Painel de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="acb7b-168">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="acb7b-p103">Conforme observado, os totais padrões são mostrados para a semana atual e os valores de tendência são mostrados para as últimas seis semanas. Se você prefere ver os totais para o mês atual (assim como os valores de tendência para os últimos seis meses), clique no link **Exibição Mensal** no canto superior direito do painel. Se você decidir exibir os totais mensais, o texto do link irá mudar para **Exibição Semanal**. É possível voltar para a exibição semanal clicando neste link.</span><span class="sxs-lookup"><span data-stu-id="acb7b-p103">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks. If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard. If you decide to view monthly totals, the link text will change to **Weekly View**. You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="acb7b-p104">O Painel de Monitoramento restringe a exibição dos totais para a semana (ou mês) atual e os valores de tendência das últimas seis semanas (ou meses). Não é possível alterar essas datas e horas. Por exemplo, não é possível usar o Painel para ver os totais do relatório para o período que inicia nove meses atrás.</span><span class="sxs-lookup"><span data-stu-id="acb7b-p104">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months). You cannot change these dates and times. For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="acb7b-p105">Os valores mostrados nas colunas **Esta semana**, **Este mês** ou **Hoje** vinculam você às informações mais detalhadas sobre o item. Lembre-se de que o nome da coluna e os valores exibidos nesta coluna frequentemente são diferentes dependendo da métrica escolhida e dependendo se você selecionou exibição semanal ou mensal. Por exemplo, se você clicar nos totais exibidos para a métrica **Logons de usuário exclusivos**, você verá o **Relatório de Registro do Usuário** para o período especificado. É possível retornar para o Painel de Monitoramento a qualquer momento clicando em **Painel**.</span><span class="sxs-lookup"><span data-stu-id="acb7b-p105">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item. Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view. For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period. You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="acb7b-180">Você também pode acessar a Home Page de relatórios do Monitoring Server clicando no link <STRONG>relatórios</STRONG> no canto superior direito do painel.</span><span class="sxs-lookup"><span data-stu-id="acb7b-180">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="acb7b-181">A coluna **Tendência** exibe um gráfico de linha simples que mostra os totais das últimas seis semanas (ou, dependendo da métrica e do intervalo de tempo, os últimos seis dias ou últimos seis meses).</span><span class="sxs-lookup"><span data-stu-id="acb7b-181">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="acb7b-182">Esses gráficos de linha simples mostram um ponto de dados não rotulado para cada período (por exemplo, um ponto de dados não rotulado para cada uma das últimas seis semanas).</span><span class="sxs-lookup"><span data-stu-id="acb7b-182">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="acb7b-183">No entanto, é possível recuperar os valores reais desses gráficos mantendo o ponteiro do mouse sobre o gráfico.</span><span class="sxs-lookup"><span data-stu-id="acb7b-183">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="acb7b-184">Nesse caso, uma dica de ferramenta mostra os valores máximo e mínimo no gráfico.</span><span class="sxs-lookup"><span data-stu-id="acb7b-184">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="acb7b-185">Exportando dados do Painel de Monitoramento</span><span class="sxs-lookup"><span data-stu-id="acb7b-185">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="acb7b-p107">O Painel de Monitoramento oferece várias formas de exportar a exibição do painel atual. Na barra de ferramentas do Painel, você verá um ícone semelhante a um disquete com uma seta verde anexada. Se você clicar nesse ícone, uma lista suspensa aparecerá oferecendo os seguintes formatos de exportação de dados:</span><span class="sxs-lookup"><span data-stu-id="acb7b-p107">The Monitoring Dashboard provides a number of ways to export the current dashboard view. On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it. If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="acb7b-189">Arquivo XML com dados do relatório</span><span class="sxs-lookup"><span data-stu-id="acb7b-189">XML file with report data</span></span>

  - <span data-ttu-id="acb7b-190">CSV (delimitado por vírgula)</span><span class="sxs-lookup"><span data-stu-id="acb7b-190">CSV (comma delimited)</span></span>

  - <span data-ttu-id="acb7b-191">PDF</span><span class="sxs-lookup"><span data-stu-id="acb7b-191">PDF</span></span>

  - <span data-ttu-id="acb7b-192">MHTML (arquivo Web)</span><span class="sxs-lookup"><span data-stu-id="acb7b-192">MHTML (web archive)</span></span>

  - <span data-ttu-id="acb7b-193">Excel</span><span class="sxs-lookup"><span data-stu-id="acb7b-193">Excel</span></span>

  - <span data-ttu-id="acb7b-194">Arquivo TIFF</span><span class="sxs-lookup"><span data-stu-id="acb7b-194">TIFF file</span></span>

  - <span data-ttu-id="acb7b-195">Word</span><span class="sxs-lookup"><span data-stu-id="acb7b-195">Word</span></span>

<span data-ttu-id="acb7b-196">Para exportar a exibição do painel atual (e seus valores), clique na opção de exportação desejada.</span><span class="sxs-lookup"><span data-stu-id="acb7b-196">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="acb7b-197">O Lync Server 2013 gera um relatório no formato especificado e oferece a opção de abrir esse relatório ou salvá-lo.</span><span class="sxs-lookup"><span data-stu-id="acb7b-197">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="acb7b-198">Observe que, por padrão, o Lync Server títulos o **painel Monitoramento** de relatórios e salva-o na pasta downloads.</span><span class="sxs-lookup"><span data-stu-id="acb7b-198">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="acb7b-199">Para dar um nome diferente ou armazená-lo em uma pasta diferente, clique na seta ao lado do botão **Salvar** e clique em **Salvar Como**.</span><span class="sxs-lookup"><span data-stu-id="acb7b-199">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="acb7b-200">Se você concorda com o nome **Painel de Monitoramento** e em salvar na pasta Downloads, basta clicar no botão **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="acb7b-200">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="acb7b-p109">É possível que, ao tentar exportar os dados do painel, uma caixa de diálogo **Alerta de Segurança** seja exibida junto com a mensagem "Suas configurações atuais não permitem que este arquivo seja baixado". Se isso ocorrer, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="acb7b-p109">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded." If that occurs, do the following:</span></span>

  - <span data-ttu-id="acb7b-203">No Internet Explorer, selecione **Opções de Internet**.</span><span class="sxs-lookup"><span data-stu-id="acb7b-203">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="acb7b-204">Na caixa de diálogo **Opções de Internet**, na guia **Segurança**, clique em **Sites confiáveis** e em **Sites**.</span><span class="sxs-lookup"><span data-stu-id="acb7b-204">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="acb7b-205">Na caixa de diálogo **sites confiáveis** , clique em **Adicionar** para adicionar o Lync Server 2013 que está executando relatórios do Lync Server 2013 para os conjuntos de sites confiáveis.</span><span class="sxs-lookup"><span data-stu-id="acb7b-205">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="acb7b-206">Clique em **Fechar** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="acb7b-206">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="acb7b-p110">Você precisará atualizar o Painel de Monitoramento para que as alterações tenham efeito. Para fazer isso, pressione F5 ou clique no ícone **Atualizar** na barra de ferramentas do Painel. (O ícone **Atualizar** é um círculo com um par de setas verdes.)</span><span class="sxs-lookup"><span data-stu-id="acb7b-p110">You will then need to refresh the Monitoring Dashboard before the changes take effect. To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar. (The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="acb7b-p111">Também é possível criar uma planilha do Excel que inclui feeds de dados ao vivo, incluindo links para os dados do Painel de Monitoramento. Para criar um arquivo de feed de dados ao vivo, clique no ícone laranja **Exportar para Feed de Dados** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="acb7b-p111">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data. To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="acb7b-212">Se você prefere imprimir o Painel atual, clique no ícone da impressora na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="acb7b-212">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

