---
title: 'Lync Server 2013: relatório de atividade de conferência'
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
ms.openlocfilehash: c098bc3a1c8b937b72707c76a3943866ad7b9fbb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="1fb8c-102">Relatório de atividade de conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fb8c-102">Conference Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fb8c-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1fb8c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1fb8c-104">O Relatório de Atividade de Conferência torna fácil responder perguntas como estas: quantas conferências estão sendo realizadas diariamente e quando estas conferências são realizadas?</span><span class="sxs-lookup"><span data-stu-id="1fb8c-104">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="1fb8c-105">Informações como estas são úteis não apenas em seu próprio direito, mas também como uma ferramenta de resolução de problemas.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-105">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="1fb8c-106">Por exemplo, vamos supor que os usuários estão reclamando que a rede parece particularmente lenta no meio do dia.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-106">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="1fb8c-107">Uma rápida descrição dos relatórios de atividade de conferência pode sugerir um possível motivo: muito mais conferências estão sendo agendadas entre as horas de 10:00 AM e 2:00 PM em qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-107">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="1fb8c-108">Se a rede lenta está causando problemas, é possível incentivar os usuários a reprogramar algumas de suas conferências durante horários com menos tráfego durante o dia.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-108">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="1fb8c-109">Acessando o Relatório de Atividade da Conferência</span><span class="sxs-lookup"><span data-stu-id="1fb8c-109">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="1fb8c-110">O relatório atividade de conferência é acessado do [relatório Resumo de conferências no Lync Server 2013](lync-server-2013-conference-summary-report.md) clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="1fb8c-110">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="1fb8c-111">Total de conferências</span><span class="sxs-lookup"><span data-stu-id="1fb8c-111">Total conferences</span></span>

  - <span data-ttu-id="1fb8c-112">Total de participantes</span><span class="sxs-lookup"><span data-stu-id="1fb8c-112">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="1fb8c-113">Fazendo o melhor uso do Relatório de Atividade de Conferência</span><span class="sxs-lookup"><span data-stu-id="1fb8c-113">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="1fb8c-p102">Por padrão, o Relatório de Atividade de Conferência mostra o número total de conferências para um determinado período de tempo (por exemplo, o número total de conferências por dia ou o número total de conferências por hora do dia). No entanto, é possível escolher exibir o número total de participantes neste período de tempo ou o número total de participantes em minutos. Para fazer isso, clique no botão Exibir/Ocultar parâmetros para exibir as opções de filtragem e selecione um dos seguintes na lista suspensa Relatar por:</span><span class="sxs-lookup"><span data-stu-id="1fb8c-p102">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day). However, you can also choose to display the total number of participants for that time period or the total number of participant minutes. To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="1fb8c-117">Contagem de participantes</span><span class="sxs-lookup"><span data-stu-id="1fb8c-117">Participant count</span></span>

  - <span data-ttu-id="1fb8c-118">Minutos dos participantes</span><span class="sxs-lookup"><span data-stu-id="1fb8c-118">Participant minutes</span></span>

  - <span data-ttu-id="1fb8c-119">Contagem de conferência</span><span class="sxs-lookup"><span data-stu-id="1fb8c-119">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1fb8c-120">Filtros</span><span class="sxs-lookup"><span data-stu-id="1fb8c-120">Filters</span></span>

<span data-ttu-id="1fb8c-p103">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. A tabela a seguir lista os filtros que você pode usar com o Relatório de Atividades de Conferência.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="1fb8c-123">Filtros de relatório de atividade de conferência</span><span class="sxs-lookup"><span data-stu-id="1fb8c-123">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fb8c-124">Nome</span><span class="sxs-lookup"><span data-stu-id="1fb8c-124">Name</span></span></th>
<th><span data-ttu-id="1fb8c-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="1fb8c-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fb8c-126"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="1fb8c-126"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb8c-p104">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="1fb8c-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1fb8c-129">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1fb8c-129">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1fb8c-p105">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="1fb8c-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1fb8c-132">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1fb8c-132">7/7/2012</span></span></p>
<p><span data-ttu-id="1fb8c-133">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="1fb8c-133">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1fb8c-134">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1fb8c-134">7/3/2012</span></span></p>
<p><span data-ttu-id="1fb8c-135">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-135">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb8c-136"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="1fb8c-136"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb8c-p106">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="1fb8c-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1fb8c-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1fb8c-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1fb8c-p107">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="1fb8c-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1fb8c-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1fb8c-142">7/7/2012</span></span></p>
<p><span data-ttu-id="1fb8c-143">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="1fb8c-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1fb8c-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1fb8c-144">7/3/2012</span></span></p>
<p><span data-ttu-id="1fb8c-145">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb8c-146"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="1fb8c-146"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb8c-p108">Intervalo de tempo. Selecione qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="1fb8c-p108">Time interval. Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1fb8c-149">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="1fb8c-149">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1fb8c-150">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="1fb8c-150">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1fb8c-151">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="1fb8c-151">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1fb8c-152">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="1fb8c-152">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="1fb8c-153">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-153">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="1fb8c-154">Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/7/2012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/2012 12:00 AM a 9/7/2012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</span><span class="sxs-lookup"><span data-stu-id="1fb8c-154">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb8c-155"><strong>Relatar por</strong></span><span class="sxs-lookup"><span data-stu-id="1fb8c-155"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb8c-p110">Indica os valores a serem usados no relatório. Você pode selecionar um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="1fb8c-p110">Indicates the values to be used in the report. You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1fb8c-158">Contagem de participantes</span><span class="sxs-lookup"><span data-stu-id="1fb8c-158">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="1fb8c-159">Minutos dos participantes</span><span class="sxs-lookup"><span data-stu-id="1fb8c-159">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="1fb8c-160">Contagem de conferência</span><span class="sxs-lookup"><span data-stu-id="1fb8c-160">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="1fb8c-161">Métricas para conferências por pool</span><span class="sxs-lookup"><span data-stu-id="1fb8c-161">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="1fb8c-162">A tabela a seguir lista as informações no Relatório de Atividade de Conferência para cada pool.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-162">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="1fb8c-163">Métricas para conferências por pool</span><span class="sxs-lookup"><span data-stu-id="1fb8c-163">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fb8c-164">Nome</span><span class="sxs-lookup"><span data-stu-id="1fb8c-164">Name</span></span></th>
<th><span data-ttu-id="1fb8c-165">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="1fb8c-165">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1fb8c-166">Descrição</span><span class="sxs-lookup"><span data-stu-id="1fb8c-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fb8c-167"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="1fb8c-167"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb8c-168">Não</span><span class="sxs-lookup"><span data-stu-id="1fb8c-168">No</span></span></p></td>
<td><p><span data-ttu-id="1fb8c-169">Nome do pool do Registrador ou Servidor de Borda usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-169">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb8c-170"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="1fb8c-170"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb8c-171">Não</span><span class="sxs-lookup"><span data-stu-id="1fb8c-171">No</span></span></p></td>
<td><p><span data-ttu-id="1fb8c-172">Data e hora de quando a conferência foi realizada.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-172">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb8c-173"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="1fb8c-173"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb8c-174">Não</span><span class="sxs-lookup"><span data-stu-id="1fb8c-174">No</span></span></p></td>
<td><p><span data-ttu-id="1fb8c-175">Contagem total de participantes, minutos totais de participantes ou contagem total da conferência.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-175">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="1fb8c-176">Métricas para conferência por tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="1fb8c-176">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="1fb8c-177">A tabela a seguir lista as informações no relatório de atividade de conferência para cada tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-177">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="1fb8c-178">Métricas para conferência por tipo de servidor</span><span class="sxs-lookup"><span data-stu-id="1fb8c-178">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fb8c-179">Nome</span><span class="sxs-lookup"><span data-stu-id="1fb8c-179">Name</span></span></th>
<th><span data-ttu-id="1fb8c-180">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="1fb8c-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1fb8c-181">Descrição</span><span class="sxs-lookup"><span data-stu-id="1fb8c-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fb8c-182"><strong>Tipo de servidor de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="1fb8c-182"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb8c-183">Não</span><span class="sxs-lookup"><span data-stu-id="1fb8c-183">No</span></span></p></td>
<td><p><span data-ttu-id="1fb8c-184">Tipo de servidor usado na conferência, geralmente um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="1fb8c-184">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1fb8c-185">Servidor de conferência da Web</span><span class="sxs-lookup"><span data-stu-id="1fb8c-185">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="1fb8c-186">Servidor de conferência de IM</span><span class="sxs-lookup"><span data-stu-id="1fb8c-186">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="1fb8c-187">Servidor de conferência com telefonia</span><span class="sxs-lookup"><span data-stu-id="1fb8c-187">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="1fb8c-188">Servidor de conferência de AV</span><span class="sxs-lookup"><span data-stu-id="1fb8c-188">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="1fb8c-189">Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="1fb8c-189">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fb8c-190"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="1fb8c-190"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb8c-191">Não</span><span class="sxs-lookup"><span data-stu-id="1fb8c-191">No</span></span></p></td>
<td><p><span data-ttu-id="1fb8c-192">Data e hora de quando a conferência foi realizada.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-192">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fb8c-193"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="1fb8c-193"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="1fb8c-194">Não</span><span class="sxs-lookup"><span data-stu-id="1fb8c-194">No</span></span></p></td>
<td><p><span data-ttu-id="1fb8c-195">Contagem total de participantes, minutos totais de participantes ou contagem total da conferência.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-195">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

