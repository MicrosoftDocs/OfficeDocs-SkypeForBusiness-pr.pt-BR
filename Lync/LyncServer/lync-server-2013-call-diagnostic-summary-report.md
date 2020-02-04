---
title: 'Lync Server 2013: relatório de Resumo de diagnóstico de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0228af8690fe7170fc4fd77e72f67f6cb3adc08c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="8e2ab-102">Relatório de resumo do diagnóstico de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e2ab-102">Call Diagnostic Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e2ab-103">_**Tópico da última modificação:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="8e2ab-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="8e2ab-p101">O Relatório de Resumo de Diagnóstico de Chamadas fornece uma visão geral de sessões peer-to-peer e de conferências que falharam. O relatório mostra a taxa de falha geral para os dois tipos de sessão, e detalha as informações de falha por tipo de modalidade de sessão:</span><span class="sxs-lookup"><span data-stu-id="8e2ab-p101">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions. The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="8e2ab-106">Mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="8e2ab-106">Instant messaging</span></span>

  - <span data-ttu-id="8e2ab-107">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="8e2ab-107">Application sharing</span></span>

  - <span data-ttu-id="8e2ab-108">Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="8e2ab-108">File transfer</span></span>

  - <span data-ttu-id="8e2ab-109">Áudio</span><span class="sxs-lookup"><span data-stu-id="8e2ab-109">Audio</span></span>

  - <span data-ttu-id="8e2ab-110">Vídeo</span><span class="sxs-lookup"><span data-stu-id="8e2ab-110">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="8e2ab-111">Como acessar o Relatório de resumo de diagnóstico de chamadas</span><span class="sxs-lookup"><span data-stu-id="8e2ab-111">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="8e2ab-112">O Relatório de resumo de diagnóstico de chamadas é acessado na página inicial dos Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="8e2ab-113">No relatório de resumo do diagnóstico de chamadas, você pode acessar o [relatório de diagnóstico de atividades ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) clicando na métrica de taxa de falha na seção Resumo de sessão ponto a ponto do relatório.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-113">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="8e2ab-114">Você também pode acessar o [relatório de diagnóstico de conferência no Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) clicando em qualquer uma das seguintes métricas de conferência:</span><span class="sxs-lookup"><span data-stu-id="8e2ab-114">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="8e2ab-115">Taxa de falha de sessão geral</span><span class="sxs-lookup"><span data-stu-id="8e2ab-115">Overall session failure rate</span></span>

  - <span data-ttu-id="8e2ab-116">Taxa de falha de foco</span><span class="sxs-lookup"><span data-stu-id="8e2ab-116">Focus failure rate</span></span>

  - <span data-ttu-id="8e2ab-117">Taxa de falha de MCU</span><span class="sxs-lookup"><span data-stu-id="8e2ab-117">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="8e2ab-118">Como usar melhor o Relatório de resumo de diagnóstico de chamadas</span><span class="sxs-lookup"><span data-stu-id="8e2ab-118">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="8e2ab-119">O relatório de resumo do diagnóstico de chamadas inclui gráficos que comparam as tarifas de falha para as diversas modalidades usadas no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-119">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="8e2ab-120">As colunas nestes gráficos são na verdade hotlinks; por exemplo, se você clicar na coluna mensagens instantâneas para sessões ponto a ponto, fará Drill down até uma instância do [relatório de diagnóstico de atividade ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), um relatório que fornece mais detalhes sobre todas as sessões de mensagens instantâneas incluídas no relatório de resumo do diagnóstico de chamadas.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-120">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8e2ab-121">Filtros</span><span class="sxs-lookup"><span data-stu-id="8e2ab-121">Filters</span></span>

<span data-ttu-id="8e2ab-p104">Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Resumo de Diagnóstico de Chamadas permite filtrar por informações como pool do Registrador Avançado ou Servidor de Borda usado na sessão. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="8e2ab-126">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Diagnóstico de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-126">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="8e2ab-127">Filtros do Relatório de Resumo de Diagnóstico de Chamadas</span><span class="sxs-lookup"><span data-stu-id="8e2ab-127">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e2ab-128">Nome</span><span class="sxs-lookup"><span data-stu-id="8e2ab-128">Name</span></span></th>
<th><span data-ttu-id="8e2ab-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="8e2ab-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e2ab-130"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="8e2ab-130"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8e2ab-p105">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="8e2ab-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8e2ab-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8e2ab-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8e2ab-p106">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="8e2ab-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8e2ab-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8e2ab-136">7/7/2012</span></span></p>
<p><span data-ttu-id="8e2ab-137">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="8e2ab-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8e2ab-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8e2ab-138">7/3/2012</span></span></p>
<p><span data-ttu-id="8e2ab-139">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e2ab-140"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="8e2ab-140"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8e2ab-p107">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="8e2ab-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8e2ab-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8e2ab-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8e2ab-p108">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="8e2ab-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8e2ab-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8e2ab-146">7/7/2012</span></span></p>
<p><span data-ttu-id="8e2ab-147">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="8e2ab-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8e2ab-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8e2ab-148">7/3/2012</span></span></p>
<p><span data-ttu-id="8e2ab-149">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e2ab-150"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="8e2ab-150"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="8e2ab-p109">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="8e2ab-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8e2ab-153">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="8e2ab-153">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8e2ab-154">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="8e2ab-154">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8e2ab-155">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="8e2ab-155">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8e2ab-156">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="8e2ab-156">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="8e2ab-157">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-157">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="8e2ab-158">Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/7/2012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/2012 12:00 AM a 9/7/2012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</span><span class="sxs-lookup"><span data-stu-id="8e2ab-158">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e2ab-159"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="8e2ab-159"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="8e2ab-p111">FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Tudo]</strong> para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="8e2ab-163">Métricas para sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="8e2ab-163">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="8e2ab-164">A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Diagnóstico de Chamadas para sessões ponto a ponto (ou seja, sessões envolvendo somente dois participantes).</span><span class="sxs-lookup"><span data-stu-id="8e2ab-164">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="8e2ab-165">Métricas para sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="8e2ab-165">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e2ab-166">Nome</span><span class="sxs-lookup"><span data-stu-id="8e2ab-166">Name</span></span></th>
<th><span data-ttu-id="8e2ab-167">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="8e2ab-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8e2ab-168">Descrição</span><span class="sxs-lookup"><span data-stu-id="8e2ab-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e2ab-169"><strong>Total de sessões</strong></span><span class="sxs-lookup"><span data-stu-id="8e2ab-169"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8e2ab-170">Não</span><span class="sxs-lookup"><span data-stu-id="8e2ab-170">No</span></span></p></td>
<td><p><span data-ttu-id="8e2ab-171">Número total de sessões ponto a ponto conduzidas.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-171">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e2ab-172"><strong>Taxa de falha</strong></span><span class="sxs-lookup"><span data-stu-id="8e2ab-172"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="8e2ab-173">Não</span><span class="sxs-lookup"><span data-stu-id="8e2ab-173">No</span></span></p></td>
<td><p><span data-ttu-id="8e2ab-p112">Percentual de sessões ponto a ponto que falharam. Ao clicar neste item, o relatório exibe o relatório de Diagnóstico de Atividades Ponto a Ponto, que mostra informações mais detalhadas sobre as sessões ponto a ponto com falha.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-p112">Percentage of peer-to-peer sessions that failed. When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="8e2ab-176">Métricas para sessões de conferência</span><span class="sxs-lookup"><span data-stu-id="8e2ab-176">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="8e2ab-177">A tabela a seguir lista as informações fornecidas pelo Relatório de Diagnóstico de Chamadas para sessões de conferência (ou seja, sessões envolvendo três ou mais participantes).</span><span class="sxs-lookup"><span data-stu-id="8e2ab-177">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="8e2ab-178">Métricas para sessões de conferência</span><span class="sxs-lookup"><span data-stu-id="8e2ab-178">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e2ab-179">Nome</span><span class="sxs-lookup"><span data-stu-id="8e2ab-179">Name</span></span></th>
<th><span data-ttu-id="8e2ab-180">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="8e2ab-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8e2ab-181">Descrição</span><span class="sxs-lookup"><span data-stu-id="8e2ab-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e2ab-182"><strong>Conferências totais</strong></span><span class="sxs-lookup"><span data-stu-id="8e2ab-182"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="8e2ab-183">Não</span><span class="sxs-lookup"><span data-stu-id="8e2ab-183">No</span></span></p></td>
<td><p><span data-ttu-id="8e2ab-184">Número total de conferências conduzidas.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-184">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e2ab-185"><strong>Sessões de conferência totais</strong></span><span class="sxs-lookup"><span data-stu-id="8e2ab-185"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8e2ab-186">Não</span><span class="sxs-lookup"><span data-stu-id="8e2ab-186">No</span></span></p></td>
<td><p><span data-ttu-id="8e2ab-187">Número total de sessões de conferência conduzidas.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-187">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e2ab-188"><strong>Taxa de falha de sessão geral</strong></span><span class="sxs-lookup"><span data-stu-id="8e2ab-188"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="8e2ab-189">Não</span><span class="sxs-lookup"><span data-stu-id="8e2ab-189">No</span></span></p></td>
<td><p><span data-ttu-id="8e2ab-190">Percentual de sessões de conferência totais que falharam.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-190">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e2ab-191"><strong>Sessões de foco</strong></span><span class="sxs-lookup"><span data-stu-id="8e2ab-191"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8e2ab-192">Não</span><span class="sxs-lookup"><span data-stu-id="8e2ab-192">No</span></span></p></td>
<td><p><span data-ttu-id="8e2ab-193">Número total de sessões de conferência baseadas em Foco que falharam.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-193">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e2ab-194"><strong>Taxa de falha de foco</strong></span><span class="sxs-lookup"><span data-stu-id="8e2ab-194"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="8e2ab-195">Não</span><span class="sxs-lookup"><span data-stu-id="8e2ab-195">No</span></span></p></td>
<td><p><span data-ttu-id="8e2ab-196">Percentual de sessões de conferência baseadas em Foco que falharam.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-196">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e2ab-197"><strong>Sessões MCU</strong></span><span class="sxs-lookup"><span data-stu-id="8e2ab-197"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8e2ab-198">Não</span><span class="sxs-lookup"><span data-stu-id="8e2ab-198">No</span></span></p></td>
<td><p><span data-ttu-id="8e2ab-199">Número total de conferências baseadas em servidor (anteriormente conhecidas como Unidade de Controle de Multipontos ou MCU) que falharam.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-199">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e2ab-200"><strong>Taxa de falha de MCU</strong></span><span class="sxs-lookup"><span data-stu-id="8e2ab-200"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="8e2ab-201">Não</span><span class="sxs-lookup"><span data-stu-id="8e2ab-201">No</span></span></p></td>
<td><p><span data-ttu-id="8e2ab-202">Percentual de conferências baseadas em servidor (anteriormente conhecidas como Unidade de Controle de Multipontos ou MCU) que falharam.</span><span class="sxs-lookup"><span data-stu-id="8e2ab-202">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

