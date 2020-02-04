---
title: 'Lync Server 2013: relatório de diagnóstico de conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69c63e710463a37eecbb7d20edbe5999d0fbb55f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="5fbf7-102">Relatório de diagnóstico de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fbf7-102">Conference Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fbf7-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="5fbf7-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="5fbf7-104">O Relatório de Diagnóstico de Conferência oferece informações sobre o êxito e a falha de todas as sessões de conferência.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-104">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions.</span></span> <span data-ttu-id="5fbf7-105">Observe que o Microsoft Lync Server distingue entre os diferentes tipos de falha:</span><span class="sxs-lookup"><span data-stu-id="5fbf7-105">Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="5fbf7-p102">**Falha esperada**. Uma falha esperada normalmente é uma falha apenas no sentido mais técnico. Por exemplo, suponhamos que alguém inicie uma conferência, mas desligue antes que alguém possa ingressar. Tecnicamente, é uma falha: a conferência foi iniciada, mas não foi concluída. No entanto, essa é uma falha que você poderia esperar que acontecesse: se o organizador cancela a conferência antes que alguém possa ingressar, não se poderia esperar que essa conferência fosse concluída.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p102">**Expected failure**. An expected failure is typically a failure only in the most technical sense. For example, suppose someone starts a conference but hangs up before anyone can join. Technically that's a failure: the conference was initiated, but not completed. However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="5fbf7-p103">**Falha inesperada**. Uma falha inesperada é exatamente o que o nome diz: um erro que, baseado nas circunstâncias, você não esperaria que ocorresse. Por exemplo, suponhamos que uma conferência não tenha acontecido porque a política de reunião do organizador não pôde ser recuperada. Isso é um erro inesperado: afinal, sempre deve ser possível recuperar a política de reunião de um usuário.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p103">**Unexpected failure**. An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur. For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved. That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="5fbf7-p104">Observe que a soma das métricas de Êxitos, Falhas esperadas e Falhas inesperadas podem não resultar na métrica de Total de sessões. Por exemplo, você pode ver os seguintes valores no Relatório:</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fbf7-117">Êxitos</span><span class="sxs-lookup"><span data-stu-id="5fbf7-117">Successes</span></span></th>
<th><span data-ttu-id="5fbf7-118">Falhas esperadas</span><span class="sxs-lookup"><span data-stu-id="5fbf7-118">Expected failures</span></span></th>
<th><span data-ttu-id="5fbf7-119">Falhas inesperadas</span><span class="sxs-lookup"><span data-stu-id="5fbf7-119">Unexpected failures</span></span></th>
<th><span data-ttu-id="5fbf7-120">Total de sessões</span><span class="sxs-lookup"><span data-stu-id="5fbf7-120">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fbf7-121">2024</span><span class="sxs-lookup"><span data-stu-id="5fbf7-121">2024</span></span></p></td>
<td><p><span data-ttu-id="5fbf7-122">469</span><span class="sxs-lookup"><span data-stu-id="5fbf7-122">469</span></span></p></td>
<td><p><span data-ttu-id="5fbf7-123">16</span><span class="sxs-lookup"><span data-stu-id="5fbf7-123">16</span></span></p></td>
<td><p><span data-ttu-id="5fbf7-124">2521</span><span class="sxs-lookup"><span data-stu-id="5fbf7-124">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5fbf7-125">Somando 2024 + 469 + 16, você obtém um total de 2.509 sessões e, no entanto, a coluna de Total de sessões mostra um total de 2.521 sessões.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-125">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="5fbf7-126">As 12 sessões que estão "faltando" são sessões que o sistema não conseguiu categorizar como êxito ou falha.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-126">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="5fbf7-127">Isso, às vezes, é o caso quando um produto de terceiros introduz um novo código de diagnóstico desconhecido para monitorar o servidor.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-127">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="5fbf7-128">Quando isso acontece, as chamadas efetuadas com o produto e o relatório desse código de diagnóstico nem sempre podem ser categorizados como Êxito, Falha esperada ou Falha inesperada.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-128">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="5fbf7-129">Acessando o Relatório de Diagnóstico de Conferência</span><span class="sxs-lookup"><span data-stu-id="5fbf7-129">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="5fbf7-130">O Relatório de Diagnóstico de Conferência é acessado na página inicial de Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-130">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="5fbf7-131">Você pode acessar o [relatório de distribuição de falha no Lync Server 2013](lync-server-2013-failure-distribution-report.md) clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="5fbf7-131">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="5fbf7-132">Volume de falhas inesperadas</span><span class="sxs-lookup"><span data-stu-id="5fbf7-132">Unexpected failure volume</span></span>

  - <span data-ttu-id="5fbf7-133">Volume de falhas esperadas</span><span class="sxs-lookup"><span data-stu-id="5fbf7-133">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="5fbf7-134">Como usar o Relatório de Diagnóstico de Conferência da melhor maneira possível</span><span class="sxs-lookup"><span data-stu-id="5fbf7-134">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="5fbf7-135">O Relatório de Diagnóstico de Conferência inclui uma série de gráficos.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-135">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="5fbf7-136">Cada uma das colunas exibidas no gráfico é, na verdade, um hiperlink.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-136">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="5fbf7-137">Se você clicar em uma coluna, fará uma busca detalhada no [relatório de distribuição de falha no Lync Server 2013](lync-server-2013-failure-distribution-report.md) para esse período de tempo e esse tipo de conferência.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-137">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="5fbf7-138">Filtros</span><span class="sxs-lookup"><span data-stu-id="5fbf7-138">Filters</span></span>

<span data-ttu-id="5fbf7-p108">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Diagnóstico de Conferência permite que você filtre coisas como o tipo de conferência que está sendo conduzida (por exemplo, uma conferência baseada em Foco) ou pelo Servidor de Borda usado na conferência. Também é possível escolher como os dados devem ser agrupados. Nesse caso, as conferências são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference. You can also choose how data should be grouped. In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="5fbf7-143">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Diagnóstico de Conferência.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-143">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="5fbf7-144">Filtros do Relatório de Diagnóstico de Conferência</span><span class="sxs-lookup"><span data-stu-id="5fbf7-144">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fbf7-145">Nome</span><span class="sxs-lookup"><span data-stu-id="5fbf7-145">Name</span></span></th>
<th><span data-ttu-id="5fbf7-146">Descrição</span><span class="sxs-lookup"><span data-stu-id="5fbf7-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fbf7-147"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="5fbf7-147"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="5fbf7-p109">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="5fbf7-150">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="5fbf7-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5fbf7-p110">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5fbf7-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5fbf7-153">7/7/2012</span></span></p>
<p><span data-ttu-id="5fbf7-154">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="5fbf7-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5fbf7-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5fbf7-155">7/3/2012</span></span></p>
<p><span data-ttu-id="5fbf7-156">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fbf7-157"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="5fbf7-157"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="5fbf7-p111">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="5fbf7-160">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="5fbf7-160">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5fbf7-p112">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5fbf7-163">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5fbf7-163">7/7/2012</span></span></p>
<p><span data-ttu-id="5fbf7-164">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="5fbf7-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5fbf7-165">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5fbf7-165">7/3/2012</span></span></p>
<p><span data-ttu-id="5fbf7-166">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fbf7-167"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="5fbf7-167"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="5fbf7-p113">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5fbf7-170">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="5fbf7-170">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5fbf7-171">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="5fbf7-171">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5fbf7-172">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="5fbf7-172">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5fbf7-173">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="5fbf7-173">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="5fbf7-174">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-174">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="5fbf7-175">Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/7/2012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/2012 12:00 AM a 9/7/2012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</span><span class="sxs-lookup"><span data-stu-id="5fbf7-175">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fbf7-176"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5fbf7-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5fbf7-p115">FQDN (Nome de domínio totalmente qualificado) do pool de Registradores Avançados ou Servidores de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Tudo]</strong> para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fbf7-180"><strong>Sessões de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="5fbf7-180"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="5fbf7-p116">Indica o tipo de sessão de conferência. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p116">Indicates the type of conferencing session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5fbf7-183">[Todos]</span><span class="sxs-lookup"><span data-stu-id="5fbf7-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="5fbf7-184">Sessões de foco</span><span class="sxs-lookup"><span data-stu-id="5fbf7-184">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="5fbf7-185">Todas as sessões MCU</span><span class="sxs-lookup"><span data-stu-id="5fbf7-185">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="5fbf7-186">Conferência de IM</span><span class="sxs-lookup"><span data-stu-id="5fbf7-186">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="5fbf7-187">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="5fbf7-187">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="5fbf7-188">Conferência de A/V</span><span class="sxs-lookup"><span data-stu-id="5fbf7-188">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="5fbf7-189">Métricas</span><span class="sxs-lookup"><span data-stu-id="5fbf7-189">Metrics</span></span>

<span data-ttu-id="5fbf7-190">A tabela a seguir lista as informações fornecidas no Relatório de Diagnóstico de Conferência para cada tipo de sessão de conferência.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-190">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="5fbf7-191">Métricas do Relatório de Diagnóstico de Conferência</span><span class="sxs-lookup"><span data-stu-id="5fbf7-191">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fbf7-192">Nome</span><span class="sxs-lookup"><span data-stu-id="5fbf7-192">Name</span></span></th>
<th><span data-ttu-id="5fbf7-193">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="5fbf7-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5fbf7-194">Descrição</span><span class="sxs-lookup"><span data-stu-id="5fbf7-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fbf7-195"><strong>Volume de sucesso</strong></span><span class="sxs-lookup"><span data-stu-id="5fbf7-195"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="5fbf7-196">Não</span><span class="sxs-lookup"><span data-stu-id="5fbf7-196">No</span></span></p></td>
<td><p><span data-ttu-id="5fbf7-197">Número total de conferências bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-197">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fbf7-198"><strong>Porcentagem de sucesso</strong></span><span class="sxs-lookup"><span data-stu-id="5fbf7-198"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="5fbf7-199">Não</span><span class="sxs-lookup"><span data-stu-id="5fbf7-199">No</span></span></p></td>
<td><p><span data-ttu-id="5fbf7-p117">Percentual de conferências concluídas com problemas consideráveis. Calculado dividindo o Volume de sucesso pelo Total de sessões.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p117">Percentage of conferences that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fbf7-202"><strong>Volume de falha esperado</strong></span><span class="sxs-lookup"><span data-stu-id="5fbf7-202"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="5fbf7-203">Não</span><span class="sxs-lookup"><span data-stu-id="5fbf7-203">No</span></span></p></td>
<td><p><span data-ttu-id="5fbf7-204">Número total de conferências em que &quot;ocorreu uma&quot; falha esperada.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-204">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="5fbf7-p118">Uma falha esperada é quando se sabe que a falha ocorrerá. Por exemplo, se um usuário tiver definido seu status como Não perturbe, é esperado que qualquer chamada para esse usuário falhe.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fbf7-207"><strong>Percentual de falhas esperadas</strong></span><span class="sxs-lookup"><span data-stu-id="5fbf7-207"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="5fbf7-208">Não</span><span class="sxs-lookup"><span data-stu-id="5fbf7-208">No</span></span></p></td>
<td><p><span data-ttu-id="5fbf7-p119">Percentual de conferências que enfrentaram um erro esperado. Calculado pela divisão do Volume de falha esperado pelo Total de sessões.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p119">Percentage of conferences that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fbf7-211"><strong>Volume de falha inesperado</strong></span><span class="sxs-lookup"><span data-stu-id="5fbf7-211"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="5fbf7-212">Não</span><span class="sxs-lookup"><span data-stu-id="5fbf7-212">No</span></span></p></td>
<td><p><span data-ttu-id="5fbf7-213">Número total de conferências em que &quot;ocorreu uma&quot; falha inesperada.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-213">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="5fbf7-p120">Uma falha inesperada é uma falha que ocorre no que aparenta ser um sistema íntegro. Por exemplo, uma chamada não deve ser encerrada se o chamador for colocado em espera. Se isso ocorrer, isso seria sinalizado como uma falha inesperada.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fbf7-217"><strong>Percentual de falhas inesperadas</strong></span><span class="sxs-lookup"><span data-stu-id="5fbf7-217"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="5fbf7-218">Não</span><span class="sxs-lookup"><span data-stu-id="5fbf7-218">No</span></span></p></td>
<td><p><span data-ttu-id="5fbf7-p121">Percentual de conferências que enfrentaram um erro esperado. Calculado pela divisão do Volume de falha inesperado pelo Total de sessões.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-p121">Percentage of conferences that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fbf7-221"><strong>Total de sessões</strong></span><span class="sxs-lookup"><span data-stu-id="5fbf7-221"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="5fbf7-222">Não</span><span class="sxs-lookup"><span data-stu-id="5fbf7-222">No</span></span></p></td>
<td><p><span data-ttu-id="5fbf7-223">Número total de conferências, incluindo conferências bem-sucedidas, conferências com falha (falhas esperadas e inesperadas) e conferências não categorizadas.</span><span class="sxs-lookup"><span data-stu-id="5fbf7-223">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

