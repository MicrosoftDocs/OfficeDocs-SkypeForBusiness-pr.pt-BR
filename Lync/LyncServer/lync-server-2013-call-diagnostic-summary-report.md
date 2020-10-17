---
title: 'Lync Server 2013: relatório de Resumo de diagnóstico de chamadas'
description: 'Lync Server 2013: relatório de Resumo de diagnóstico de chamadas.'
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
ms.openlocfilehash: b444a176c06974a9eb9827006e078c17b54047a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561697"
---
# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="bc749-103">Relatório de Resumo de diagnóstico de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc749-103">Call Diagnostic Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc749-104">_**Última modificação do tópico:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="bc749-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="bc749-p101">O Relatório de Resumo de Diagnóstico de Chamadas fornece uma visão geral de sessões peer-to-peer e de conferências que falharam. O relatório mostra a taxa de falha geral para os dois tipos de sessão, e detalha as informações de falha por tipo de modalidade de sessão:</span><span class="sxs-lookup"><span data-stu-id="bc749-p101">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions. The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="bc749-107">Mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="bc749-107">Instant messaging</span></span>

  - <span data-ttu-id="bc749-108">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="bc749-108">Application sharing</span></span>

  - <span data-ttu-id="bc749-109">Transferência de arquivo</span><span class="sxs-lookup"><span data-stu-id="bc749-109">File transfer</span></span>

  - <span data-ttu-id="bc749-110">Áudio</span><span class="sxs-lookup"><span data-stu-id="bc749-110">Audio</span></span>

  - <span data-ttu-id="bc749-111">Vídeo</span><span class="sxs-lookup"><span data-stu-id="bc749-111">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="bc749-112">Como acessar o Relatório de resumo de diagnóstico de chamadas</span><span class="sxs-lookup"><span data-stu-id="bc749-112">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="bc749-113">O Relatório de resumo de diagnóstico de chamadas é acessado a partir da página inicial dos Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="bc749-113">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="bc749-114">No relatório de Resumo de diagnóstico de chamadas, você pode acessar o [relatório de diagnóstico de atividades ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) clicando na métrica de taxa de falha na seção Resumo de sessão ponto a ponto do relatório.</span><span class="sxs-lookup"><span data-stu-id="bc749-114">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="bc749-115">Você também pode acessar o [relatório de diagnóstico de conferência no Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) clicando em qualquer uma das seguintes métricas de conferência:</span><span class="sxs-lookup"><span data-stu-id="bc749-115">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="bc749-116">Taxa de falha de sessão geral</span><span class="sxs-lookup"><span data-stu-id="bc749-116">Overall session failure rate</span></span>

  - <span data-ttu-id="bc749-117">Taxa de falha de foco</span><span class="sxs-lookup"><span data-stu-id="bc749-117">Focus failure rate</span></span>

  - <span data-ttu-id="bc749-118">Taxa de falha de MCU</span><span class="sxs-lookup"><span data-stu-id="bc749-118">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="bc749-119">Como usar melhor o Relatório de resumo de diagnóstico de chamadas</span><span class="sxs-lookup"><span data-stu-id="bc749-119">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="bc749-120">O relatório de Resumo de diagnóstico de chamada inclui gráficos que comparam taxas de falha para as várias modalidades usadas no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc749-120">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="bc749-121">Na verdade, as colunas nesses gráficos são hotlinks; por exemplo, se você clicar na coluna mensagens instantâneas para sessões ponto a ponto, fará uma busca detalhada em uma instância do relatório de [diagnóstico de atividades ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), um relatório que fornece detalhes adicionais sobre todas as sessões de mensagens instantâneas incluídas no relatório de Resumo de diagnóstico de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bc749-121">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="bc749-122">Filtros</span><span class="sxs-lookup"><span data-stu-id="bc749-122">Filters</span></span>

<span data-ttu-id="bc749-p104">Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Resumo de Diagnóstico de Chamadas permite filtrar por informações como pool do Registrador Avançado ou Servidor de Borda usado na sessão. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="bc749-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="bc749-127">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Diagnóstico de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="bc749-127">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="bc749-128">Filtros do Relatório de Resumo de Diagnóstico de Chamadas</span><span class="sxs-lookup"><span data-stu-id="bc749-128">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc749-129">Nome</span><span class="sxs-lookup"><span data-stu-id="bc749-129">Name</span></span></th>
<th><span data-ttu-id="bc749-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="bc749-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc749-131"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="bc749-131"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="bc749-p105">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="bc749-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="bc749-134">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="bc749-134">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="bc749-p106">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="bc749-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="bc749-137">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="bc749-137">7/7/2012</span></span></p>
<p><span data-ttu-id="bc749-138">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="bc749-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="bc749-139">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="bc749-139">7/3/2012</span></span></p>
<p><span data-ttu-id="bc749-140">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="bc749-140">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc749-141"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="bc749-141"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="bc749-p107">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="bc749-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="bc749-144">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="bc749-144">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="bc749-p108">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="bc749-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="bc749-147">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="bc749-147">7/7/2012</span></span></p>
<p><span data-ttu-id="bc749-148">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="bc749-148">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="bc749-149">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="bc749-149">7/3/2012</span></span></p>
<p><span data-ttu-id="bc749-150">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="bc749-150">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc749-151"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="bc749-151"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="bc749-p109">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="bc749-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc749-154">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="bc749-154">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="bc749-155">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="bc749-155">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="bc749-156">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="bc749-156">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="bc749-157">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="bc749-157">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="bc749-p110">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com a data de início 07.07.12 e uma data de término de 28.02.12, os dados serão exibidos para os dias 07.08.12 12:00 AM até 07.09.12 12:00 AM (ou seja, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="bc749-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc749-160"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="bc749-160"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="bc749-p111">Nome de domínio totalmente qualificado (FQDN) do pool do Registrador Avançado ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Todos]</strong> para exibir dados para todos os pools. Esta lista suspensa é preenchida automaticamente, com base nos registros do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bc749-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="bc749-164">Métricas para Sessões Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="bc749-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="bc749-165">A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Diagnóstico de Chamadas para sessões ponto a ponto (ou seja, sessões envolvendo somente dois participantes).</span><span class="sxs-lookup"><span data-stu-id="bc749-165">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="bc749-166">Métricas para Sessões Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="bc749-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc749-167">Nome</span><span class="sxs-lookup"><span data-stu-id="bc749-167">Name</span></span></th>
<th><span data-ttu-id="bc749-168">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="bc749-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bc749-169">Descrição</span><span class="sxs-lookup"><span data-stu-id="bc749-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc749-170"><strong>Sessões totais</strong></span><span class="sxs-lookup"><span data-stu-id="bc749-170"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="bc749-171">Não</span><span class="sxs-lookup"><span data-stu-id="bc749-171">No</span></span></p></td>
<td><p><span data-ttu-id="bc749-172">Número total de sessões ponto a ponto conduzidas.</span><span class="sxs-lookup"><span data-stu-id="bc749-172">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc749-173"><strong>Taxa de falha</strong></span><span class="sxs-lookup"><span data-stu-id="bc749-173"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="bc749-174">Não</span><span class="sxs-lookup"><span data-stu-id="bc749-174">No</span></span></p></td>
<td><p><span data-ttu-id="bc749-p112">Percentual de sessões ponto a ponto que falharam. Ao clicar neste item, o relatório exibe o relatório de Diagnóstico de Atividades Ponto a Ponto, que mostra informações mais detalhadas sobre as sessões ponto a ponto com falha.</span><span class="sxs-lookup"><span data-stu-id="bc749-p112">Percentage of peer-to-peer sessions that failed. When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="bc749-177">Métricas para Sessões de Conferência</span><span class="sxs-lookup"><span data-stu-id="bc749-177">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="bc749-178">A tabela a seguir lista as informações fornecidas pelo Relatório de Diagnóstico de Chamadas para sessões de conferência (ou seja, sessões envolvendo três ou mais participantes).</span><span class="sxs-lookup"><span data-stu-id="bc749-178">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="bc749-179">Métricas para Sessões de Conferência</span><span class="sxs-lookup"><span data-stu-id="bc749-179">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc749-180">Nome</span><span class="sxs-lookup"><span data-stu-id="bc749-180">Name</span></span></th>
<th><span data-ttu-id="bc749-181">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="bc749-181">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bc749-182">Descrição</span><span class="sxs-lookup"><span data-stu-id="bc749-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc749-183"><strong>Total de conferências</strong></span><span class="sxs-lookup"><span data-stu-id="bc749-183"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="bc749-184">Não</span><span class="sxs-lookup"><span data-stu-id="bc749-184">No</span></span></p></td>
<td><p><span data-ttu-id="bc749-185">Número total de conferências conduzidas.</span><span class="sxs-lookup"><span data-stu-id="bc749-185">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc749-186"><strong>Sessões de conferência totais</strong></span><span class="sxs-lookup"><span data-stu-id="bc749-186"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="bc749-187">Não</span><span class="sxs-lookup"><span data-stu-id="bc749-187">No</span></span></p></td>
<td><p><span data-ttu-id="bc749-188">Número total de sessões de conferência conduzidas.</span><span class="sxs-lookup"><span data-stu-id="bc749-188">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc749-189"><strong>Taxa de falha de sessão geral</strong></span><span class="sxs-lookup"><span data-stu-id="bc749-189"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="bc749-190">Não</span><span class="sxs-lookup"><span data-stu-id="bc749-190">No</span></span></p></td>
<td><p><span data-ttu-id="bc749-191">Percentual de sessões de conferência totais que falharam.</span><span class="sxs-lookup"><span data-stu-id="bc749-191">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc749-192"><strong>Sessões de Foco</strong></span><span class="sxs-lookup"><span data-stu-id="bc749-192"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="bc749-193">Não</span><span class="sxs-lookup"><span data-stu-id="bc749-193">No</span></span></p></td>
<td><p><span data-ttu-id="bc749-194">Número total de sessões de conferência baseadas em Foco que falharam.</span><span class="sxs-lookup"><span data-stu-id="bc749-194">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc749-195"><strong>Taxa de falha de Foco</strong></span><span class="sxs-lookup"><span data-stu-id="bc749-195"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="bc749-196">Não</span><span class="sxs-lookup"><span data-stu-id="bc749-196">No</span></span></p></td>
<td><p><span data-ttu-id="bc749-197">Percentual de sessões de conferência baseadas em Foco que falharam.</span><span class="sxs-lookup"><span data-stu-id="bc749-197">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc749-198"><strong>Sessões MCU</strong></span><span class="sxs-lookup"><span data-stu-id="bc749-198"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="bc749-199">Não</span><span class="sxs-lookup"><span data-stu-id="bc749-199">No</span></span></p></td>
<td><p><span data-ttu-id="bc749-200">Número total de conferências baseadas em servidor (anteriormente conhecidas como Unidade de Controle de Multipontos ou MCU) que falharam.</span><span class="sxs-lookup"><span data-stu-id="bc749-200">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc749-201"><strong>Taxa de falha de MCU</strong></span><span class="sxs-lookup"><span data-stu-id="bc749-201"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="bc749-202">Não</span><span class="sxs-lookup"><span data-stu-id="bc749-202">No</span></span></p></td>
<td><p><span data-ttu-id="bc749-203">Percentual de conferências baseadas em servidor (anteriormente conhecidas como Unidade de Controle de Multipontos ou MCU) que falharam.</span><span class="sxs-lookup"><span data-stu-id="bc749-203">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

