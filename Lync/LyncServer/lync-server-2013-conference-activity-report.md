---
title: 'Lync Server 2013: relatório de atividade de conferência'
description: 'Lync Server 2013: relatório de atividade de conferência.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7a2b23a08970defaec62b98d075ad1167527fd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577647"
---
# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="6875d-103">Relatório de atividade de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6875d-103">Conference Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6875d-104">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="6875d-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6875d-105">O relatório de atividade de conferência facilita a resposta a perguntas como estas: quantas conferências estão sendo mantidas por dia e quando as conferências são mantidas?</span><span class="sxs-lookup"><span data-stu-id="6875d-105">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="6875d-106">As informações, como esta, são úteis não apenas em seu próprio direito, mas também como uma ferramenta de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="6875d-106">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="6875d-107">Por exemplo, suponha que os usuários estão reclamando que a rede parece ser especialmente lenta no meio do dia.</span><span class="sxs-lookup"><span data-stu-id="6875d-107">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="6875d-108">Uma rápida visão geral dos relatórios de atividade de conferência pode sugerir uma possível razão: muito mais conferências estão sendo agendadas entre as horas de 10:00 AM e 2:00 PM em qualquer outro momento.</span><span class="sxs-lookup"><span data-stu-id="6875d-108">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="6875d-109">Se a rede lenta está causando problemas, é possível incentivar os usuários a reagendar algumas de suas conferências durante os horários menos pesados do dia.</span><span class="sxs-lookup"><span data-stu-id="6875d-109">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="6875d-110">Acessar o relatório de atividade de conferência</span><span class="sxs-lookup"><span data-stu-id="6875d-110">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="6875d-111">O relatório de atividade de conferência é acessado a partir do [relatório de Resumo de conferências no Lync Server 2013](lync-server-2013-conference-summary-report.md) clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="6875d-111">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="6875d-112">Total de conferências</span><span class="sxs-lookup"><span data-stu-id="6875d-112">Total conferences</span></span>

  - <span data-ttu-id="6875d-113">Total de participantes</span><span class="sxs-lookup"><span data-stu-id="6875d-113">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="6875d-114">Fazendo o melhor uso do relatório de atividade de conferência</span><span class="sxs-lookup"><span data-stu-id="6875d-114">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="6875d-115">Por padrão, o relatório de atividade de conferência mostra o número total de conferências para o período de tempo especificado (por exemplo, o número total de conferências por dia ou o número total de conferências por hora do dia).</span><span class="sxs-lookup"><span data-stu-id="6875d-115">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day).</span></span> <span data-ttu-id="6875d-116">No entanto, você também pode optar por exibir o número total de participantes desse período de tempo ou o número total de minutos do participante.</span><span class="sxs-lookup"><span data-stu-id="6875d-116">However, you can also choose to display the total number of participants for that time period or the total number of participant minutes.</span></span> <span data-ttu-id="6875d-117">Para fazer isso, clique no botão Mostrar/ocultar parâmetros para exibir as opções de filtragem e selecione uma das seguintes opções na lista suspensa relatório por:</span><span class="sxs-lookup"><span data-stu-id="6875d-117">To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="6875d-118">Contagem de participantes</span><span class="sxs-lookup"><span data-stu-id="6875d-118">Participant count</span></span>

  - <span data-ttu-id="6875d-119">Minutos do participante</span><span class="sxs-lookup"><span data-stu-id="6875d-119">Participant minutes</span></span>

  - <span data-ttu-id="6875d-120">Contagem de conferência</span><span class="sxs-lookup"><span data-stu-id="6875d-120">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="6875d-121">Filtros</span><span class="sxs-lookup"><span data-stu-id="6875d-121">Filters</span></span>

<span data-ttu-id="6875d-122">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras.</span><span class="sxs-lookup"><span data-stu-id="6875d-122">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="6875d-123">A tabela a seguir lista os filtros que podem ser usados com o relatório atividade de conferência.</span><span class="sxs-lookup"><span data-stu-id="6875d-123">The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="6875d-124">Filtros de relatório de atividade de conferência</span><span class="sxs-lookup"><span data-stu-id="6875d-124">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6875d-125">Nome</span><span class="sxs-lookup"><span data-stu-id="6875d-125">Name</span></span></th>
<th><span data-ttu-id="6875d-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="6875d-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6875d-127"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="6875d-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="6875d-p104">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="6875d-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="6875d-130">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="6875d-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6875d-p105">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="6875d-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6875d-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6875d-133">7/7/2012</span></span></p>
<p><span data-ttu-id="6875d-134">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="6875d-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6875d-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6875d-135">7/3/2012</span></span></p>
<p><span data-ttu-id="6875d-136">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="6875d-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6875d-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="6875d-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="6875d-p106">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="6875d-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="6875d-140">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="6875d-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="6875d-p107">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="6875d-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="6875d-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="6875d-143">7/7/2012</span></span></p>
<p><span data-ttu-id="6875d-144">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="6875d-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="6875d-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="6875d-145">7/3/2012</span></span></p>
<p><span data-ttu-id="6875d-146">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="6875d-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6875d-147"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="6875d-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="6875d-148">Intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="6875d-148">Time interval.</span></span> <span data-ttu-id="6875d-149">Selecione qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="6875d-149">Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6875d-150">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="6875d-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6875d-151">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="6875d-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6875d-152">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="6875d-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="6875d-153">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="6875d-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="6875d-p109">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com data de início em 7/7/12 e data de término de 28/2/12, os dados serão exibidos do dia 7/8/12, às 12:00, até o dia 7/9/12, às 12:00 (ou seja, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="6875d-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6875d-156"><strong>Relatório por</strong></span><span class="sxs-lookup"><span data-stu-id="6875d-156"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="6875d-157">Indica os valores a serem usados no relatório.</span><span class="sxs-lookup"><span data-stu-id="6875d-157">Indicates the values to be used in the report.</span></span> <span data-ttu-id="6875d-158">Você pode selecionar um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="6875d-158">You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6875d-159">Contagem de participantes</span><span class="sxs-lookup"><span data-stu-id="6875d-159">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="6875d-160">Minutos do participante</span><span class="sxs-lookup"><span data-stu-id="6875d-160">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="6875d-161">Contagem de conferência</span><span class="sxs-lookup"><span data-stu-id="6875d-161">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="6875d-162">Métricas para conferências por pool</span><span class="sxs-lookup"><span data-stu-id="6875d-162">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="6875d-163">A tabela a seguir lista as informações no relatório de atividade de conferência para cada pool.</span><span class="sxs-lookup"><span data-stu-id="6875d-163">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="6875d-164">Métricas para conferências por pool</span><span class="sxs-lookup"><span data-stu-id="6875d-164">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6875d-165">Nome</span><span class="sxs-lookup"><span data-stu-id="6875d-165">Name</span></span></th>
<th><span data-ttu-id="6875d-166">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="6875d-166">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6875d-167">Descrição</span><span class="sxs-lookup"><span data-stu-id="6875d-167">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6875d-168"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="6875d-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="6875d-169">Não</span><span class="sxs-lookup"><span data-stu-id="6875d-169">No</span></span></p></td>
<td><p><span data-ttu-id="6875d-170">Nome do pool de registradores ou servidor de borda usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="6875d-170">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6875d-171"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="6875d-171"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="6875d-172">Não</span><span class="sxs-lookup"><span data-stu-id="6875d-172">No</span></span></p></td>
<td><p><span data-ttu-id="6875d-173">Data e hora em que a conferência foi realizada.</span><span class="sxs-lookup"><span data-stu-id="6875d-173">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6875d-174"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="6875d-174"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="6875d-175">Não</span><span class="sxs-lookup"><span data-stu-id="6875d-175">No</span></span></p></td>
<td><p><span data-ttu-id="6875d-176">Contagem total de participantes, minutos totais de participantes ou contagem total de conferências.</span><span class="sxs-lookup"><span data-stu-id="6875d-176">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="6875d-177">Métricas para conferências por tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="6875d-177">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="6875d-178">A tabela a seguir lista as informações no relatório de atividade de conferência para cada tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="6875d-178">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="6875d-179">Métricas para conferências por tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="6875d-179">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6875d-180">Nome</span><span class="sxs-lookup"><span data-stu-id="6875d-180">Name</span></span></th>
<th><span data-ttu-id="6875d-181">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="6875d-181">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6875d-182">Descrição</span><span class="sxs-lookup"><span data-stu-id="6875d-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6875d-183"><strong>Tipo de servidor de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="6875d-183"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="6875d-184">Não</span><span class="sxs-lookup"><span data-stu-id="6875d-184">No</span></span></p></td>
<td><p><span data-ttu-id="6875d-185">Tipo de servidor usado na conferência, geralmente um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="6875d-185">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6875d-186">Servidor de Webconferência</span><span class="sxs-lookup"><span data-stu-id="6875d-186">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="6875d-187">Servidor de conferência de IM</span><span class="sxs-lookup"><span data-stu-id="6875d-187">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="6875d-188">Servidor de conferência telefônica</span><span class="sxs-lookup"><span data-stu-id="6875d-188">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="6875d-189">Servidor de conferência AV</span><span class="sxs-lookup"><span data-stu-id="6875d-189">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="6875d-190">Compartilhamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="6875d-190">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6875d-191"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="6875d-191"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="6875d-192">Não</span><span class="sxs-lookup"><span data-stu-id="6875d-192">No</span></span></p></td>
<td><p><span data-ttu-id="6875d-193">Data e hora em que a conferência foi realizada.</span><span class="sxs-lookup"><span data-stu-id="6875d-193">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6875d-194"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="6875d-194"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="6875d-195">Não</span><span class="sxs-lookup"><span data-stu-id="6875d-195">No</span></span></p></td>
<td><p><span data-ttu-id="6875d-196">Contagem total de participantes, minutos totais de participantes ou contagem total de conferências.</span><span class="sxs-lookup"><span data-stu-id="6875d-196">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

