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
ms.openlocfilehash: 112a21dbb131e0bd34729584b8fb58399b192f70
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="21b2a-102">Relatório de Resumo de diagnóstico de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21b2a-102">Call Diagnostic Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21b2a-103">_**Última modificação do tópico:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="21b2a-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="21b2a-p101">O Relatório de Resumo de Diagnóstico de Chamadas fornece uma visão geral de sessões peer-to-peer e de conferências que falharam. O relatório mostra a taxa de falha geral para os dois tipos de sessão, e detalha as informações de falha por tipo de modalidade de sessão:</span><span class="sxs-lookup"><span data-stu-id="21b2a-p101">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions. The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="21b2a-106">Mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="21b2a-106">Instant messaging</span></span>

  - <span data-ttu-id="21b2a-107">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="21b2a-107">Application sharing</span></span>

  - <span data-ttu-id="21b2a-108">Transferência de arquivo</span><span class="sxs-lookup"><span data-stu-id="21b2a-108">File transfer</span></span>

  - <span data-ttu-id="21b2a-109">Áudio</span><span class="sxs-lookup"><span data-stu-id="21b2a-109">Audio</span></span>

  - <span data-ttu-id="21b2a-110">Vídeo</span><span class="sxs-lookup"><span data-stu-id="21b2a-110">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="21b2a-111">Como acessar o Relatório de resumo de diagnóstico de chamadas</span><span class="sxs-lookup"><span data-stu-id="21b2a-111">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="21b2a-112">O Relatório de resumo de diagnóstico de chamadas é acessado a partir da página inicial dos Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="21b2a-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="21b2a-113">No relatório de Resumo de diagnóstico de chamadas, você pode acessar o [relatório de diagnóstico de atividades ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) clicando na métrica de taxa de falha na seção Resumo de sessão ponto a ponto do relatório.</span><span class="sxs-lookup"><span data-stu-id="21b2a-113">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="21b2a-114">Você também pode acessar o [relatório de diagnóstico de conferência no Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) clicando em qualquer uma das seguintes métricas de conferência:</span><span class="sxs-lookup"><span data-stu-id="21b2a-114">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="21b2a-115">Taxa de falha de sessão geral</span><span class="sxs-lookup"><span data-stu-id="21b2a-115">Overall session failure rate</span></span>

  - <span data-ttu-id="21b2a-116">Taxa de falha de foco</span><span class="sxs-lookup"><span data-stu-id="21b2a-116">Focus failure rate</span></span>

  - <span data-ttu-id="21b2a-117">Taxa de falha MCU</span><span class="sxs-lookup"><span data-stu-id="21b2a-117">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="21b2a-118">Como usar melhor o Relatório de resumo de diagnóstico de chamadas</span><span class="sxs-lookup"><span data-stu-id="21b2a-118">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="21b2a-119">O relatório de Resumo de diagnóstico de chamada inclui gráficos que comparam taxas de falha para as várias modalidades usadas no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21b2a-119">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="21b2a-120">Na verdade, as colunas nesses gráficos são hotlinks; por exemplo, se você clicar na coluna mensagens instantâneas para sessões ponto a ponto, fará uma busca detalhada em uma instância do relatório de [diagnóstico de atividades ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), um relatório que fornece detalhes adicionais sobre todas as sessões de mensagens instantâneas incluídas no relatório de Resumo de diagnóstico de chamadas.</span><span class="sxs-lookup"><span data-stu-id="21b2a-120">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="21b2a-121">Filtros</span><span class="sxs-lookup"><span data-stu-id="21b2a-121">Filters</span></span>

<span data-ttu-id="21b2a-p104">Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Resumo de Diagnóstico de Chamadas permite filtrar por informações como pool do Registrador Avançado ou Servidor de Borda usado na sessão. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="21b2a-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="21b2a-126">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Diagnóstico de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="21b2a-126">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="21b2a-127">Filtros do Relatório de Resumo de Diagnóstico de Chamadas</span><span class="sxs-lookup"><span data-stu-id="21b2a-127">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21b2a-128">Nome</span><span class="sxs-lookup"><span data-stu-id="21b2a-128">Name</span></span></th>
<th><span data-ttu-id="21b2a-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="21b2a-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21b2a-130"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="21b2a-130"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="21b2a-p105">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="21b2a-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="21b2a-133">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="21b2a-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="21b2a-p106">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="21b2a-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="21b2a-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="21b2a-136">7/7/2012</span></span></p>
<p><span data-ttu-id="21b2a-137">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="21b2a-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="21b2a-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="21b2a-138">7/3/2012</span></span></p>
<p><span data-ttu-id="21b2a-139">As semanas sempre são de Domingo a Sábado.</span><span class="sxs-lookup"><span data-stu-id="21b2a-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21b2a-140"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="21b2a-140"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="21b2a-p107">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="21b2a-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="21b2a-143">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="21b2a-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="21b2a-p108">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="21b2a-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="21b2a-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="21b2a-146">7/7/2012</span></span></p>
<p><span data-ttu-id="21b2a-147">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="21b2a-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="21b2a-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="21b2a-148">7/3/2012</span></span></p>
<p><span data-ttu-id="21b2a-149">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="21b2a-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21b2a-150"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="21b2a-150"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="21b2a-p109">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="21b2a-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="21b2a-153">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="21b2a-153">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="21b2a-154">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="21b2a-154">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="21b2a-155">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="21b2a-155">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="21b2a-156">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="21b2a-156">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="21b2a-p110">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com a data de início 07.07.12 e uma data de término de 28.02.12, os dados serão exibidos para os dias 07.08.12 12:00 AM até 07.09.12 12:00 AM (ou seja, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="21b2a-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21b2a-159"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="21b2a-159"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="21b2a-p111">Nome de domínio totalmente qualificado (FQDN) do pool do Registrador Avançado ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Todos]</strong> para exibir dados para todos os pools. Esta lista suspensa é preenchida automaticamente, com base nos registros do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="21b2a-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="21b2a-163">Métricas para Sessões Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="21b2a-163">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="21b2a-164">A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Diagnóstico de Chamadas para sessões ponto a ponto (ou seja, sessões envolvendo somente dois participantes).</span><span class="sxs-lookup"><span data-stu-id="21b2a-164">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="21b2a-165">Métricas para sessões ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="21b2a-165">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21b2a-166">Nome</span><span class="sxs-lookup"><span data-stu-id="21b2a-166">Name</span></span></th>
<th><span data-ttu-id="21b2a-167">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="21b2a-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="21b2a-168">Descrição</span><span class="sxs-lookup"><span data-stu-id="21b2a-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21b2a-169"><strong>Sessões totais</strong></span><span class="sxs-lookup"><span data-stu-id="21b2a-169"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="21b2a-170">Não</span><span class="sxs-lookup"><span data-stu-id="21b2a-170">No</span></span></p></td>
<td><p><span data-ttu-id="21b2a-171">Número total de sessões ponto a ponto conduzidas.</span><span class="sxs-lookup"><span data-stu-id="21b2a-171">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21b2a-172"><strong>Taxa de falha</strong></span><span class="sxs-lookup"><span data-stu-id="21b2a-172"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="21b2a-173">Não</span><span class="sxs-lookup"><span data-stu-id="21b2a-173">No</span></span></p></td>
<td><p><span data-ttu-id="21b2a-p112">Percentual de sessões ponto a ponto que falharam. Ao clicar neste item, o relatório exibe o relatório de Diagnóstico de Atividades Ponto a Ponto, que mostra informações mais detalhadas sobre as sessões ponto a ponto com falha.</span><span class="sxs-lookup"><span data-stu-id="21b2a-p112">Percentage of peer-to-peer sessions that failed. When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="21b2a-176">Métricas para Sessões de Conferência</span><span class="sxs-lookup"><span data-stu-id="21b2a-176">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="21b2a-177">A tabela a seguir lista as informações fornecidas pelo Relatório de Diagnóstico de Chamadas para sessões de conferência (ou seja, sessões envolvendo três ou mais participantes).</span><span class="sxs-lookup"><span data-stu-id="21b2a-177">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="21b2a-178">Métricas para sessões de conferência</span><span class="sxs-lookup"><span data-stu-id="21b2a-178">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21b2a-179">Nome</span><span class="sxs-lookup"><span data-stu-id="21b2a-179">Name</span></span></th>
<th><span data-ttu-id="21b2a-180">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="21b2a-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="21b2a-181">Descrição</span><span class="sxs-lookup"><span data-stu-id="21b2a-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21b2a-182"><strong>Total de conferências</strong></span><span class="sxs-lookup"><span data-stu-id="21b2a-182"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="21b2a-183">Não</span><span class="sxs-lookup"><span data-stu-id="21b2a-183">No</span></span></p></td>
<td><p><span data-ttu-id="21b2a-184">Número total de conferências conduzidas.</span><span class="sxs-lookup"><span data-stu-id="21b2a-184">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21b2a-185"><strong>Sessões de conferência totais</strong></span><span class="sxs-lookup"><span data-stu-id="21b2a-185"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="21b2a-186">Não</span><span class="sxs-lookup"><span data-stu-id="21b2a-186">No</span></span></p></td>
<td><p><span data-ttu-id="21b2a-187">Número total de sessões de conferência conduzidas.</span><span class="sxs-lookup"><span data-stu-id="21b2a-187">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21b2a-188"><strong>Taxa de falha de sessão geral</strong></span><span class="sxs-lookup"><span data-stu-id="21b2a-188"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="21b2a-189">Não</span><span class="sxs-lookup"><span data-stu-id="21b2a-189">No</span></span></p></td>
<td><p><span data-ttu-id="21b2a-190">Percentual de sessões de conferência totais que falharam.</span><span class="sxs-lookup"><span data-stu-id="21b2a-190">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21b2a-191"><strong>Sessões de Foco</strong></span><span class="sxs-lookup"><span data-stu-id="21b2a-191"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="21b2a-192">Não</span><span class="sxs-lookup"><span data-stu-id="21b2a-192">No</span></span></p></td>
<td><p><span data-ttu-id="21b2a-193">Número total de sessões de conferência baseadas em Foco que falharam.</span><span class="sxs-lookup"><span data-stu-id="21b2a-193">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21b2a-194"><strong>Taxa de falha de Foco</strong></span><span class="sxs-lookup"><span data-stu-id="21b2a-194"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="21b2a-195">Não</span><span class="sxs-lookup"><span data-stu-id="21b2a-195">No</span></span></p></td>
<td><p><span data-ttu-id="21b2a-196">Percentual de sessões de conferência baseadas em Foco que falharam.</span><span class="sxs-lookup"><span data-stu-id="21b2a-196">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21b2a-197"><strong>Sessões MCU</strong></span><span class="sxs-lookup"><span data-stu-id="21b2a-197"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="21b2a-198">Não</span><span class="sxs-lookup"><span data-stu-id="21b2a-198">No</span></span></p></td>
<td><p><span data-ttu-id="21b2a-199">Número total de conferências baseadas em servidor (anteriormente conhecidas como Unidade de Controle de Multipontos ou MCU) que falharam.</span><span class="sxs-lookup"><span data-stu-id="21b2a-199">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21b2a-200"><strong>Taxa de falha de MCU</strong></span><span class="sxs-lookup"><span data-stu-id="21b2a-200"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="21b2a-201">Não</span><span class="sxs-lookup"><span data-stu-id="21b2a-201">No</span></span></p></td>
<td><p><span data-ttu-id="21b2a-202">Percentual de conferências baseadas em servidor (anteriormente conhecidas como Unidade de Controle de Multipontos ou MCU) que falharam.</span><span class="sxs-lookup"><span data-stu-id="21b2a-202">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

