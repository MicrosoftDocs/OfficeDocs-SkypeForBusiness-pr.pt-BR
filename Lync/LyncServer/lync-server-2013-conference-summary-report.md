---
title: 'Lync Server 2013: relatório de resumo da conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68858d56c47953a99928a59e5f83485ba9d305cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="8479e-102">Relatório de Resumo de conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8479e-102">Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8479e-103">_**Tópico da última modificação:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="8479e-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="8479e-104">O Relatório de Resumo de Conferências traz uma visão geral de suas sessões de conferência online.</span><span class="sxs-lookup"><span data-stu-id="8479e-104">The Conference Summary Report provides an overall view of your online conferencing sessions.</span></span> <span data-ttu-id="8479e-105">Geralmente, uma conferência envolve mais de 2 usuários e requer o uso de serviços de conferência do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8479e-105">A conference typically involves more than 2 users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="8479e-106">Por comparação, uma sessão ponto a ponto geralmente envolve apenas 2 usuários e não requer o uso de serviços de conferência do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8479e-106">By comparison, a peer-to-peer session typically involves just 2 users and does not require the use of Lync Server's conferencing services.</span></span> <span data-ttu-id="8479e-107">As atividades ponto a ponto são relatadas no [relatório de Resumo de atividades ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span><span class="sxs-lookup"><span data-stu-id="8479e-107">Peer-to-peer activities are reported on the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span></span>

<span data-ttu-id="8479e-108">O relatório de Resumo de conferências não só informa quantas conferências foram mantidas durante um determinado período (por hora, diária, semanal, mensal), mas também informa o número total de pessoas que participaram de todas as conferências e o número total de conferências exclusivas organizadores.</span><span class="sxs-lookup"><span data-stu-id="8479e-108">The Conference Summary Report not only tells you how many conferences were held during a given time period (hourly, daily, weekly, monthly) but also tells you the total number of people who took part in those conferences, and the total number of unique conference organizers.</span></span>

<span data-ttu-id="8479e-109">Um organizador "exclusivo" é qualquer pessoa que agenda pelo menos uma conferência.</span><span class="sxs-lookup"><span data-stu-id="8479e-109">A "unique” organizer is anyone who schedules at least one conference.</span></span> <span data-ttu-id="8479e-110">Por exemplo, se Pilar Ackerman agendar uma conferência, ela será contabilizada como um organizador exclusivo.</span><span class="sxs-lookup"><span data-stu-id="8479e-110">For example, if Pilar Ackerman schedules one conference she counts as one unique organizer.</span></span> <span data-ttu-id="8479e-111">Se Ken Myer agendar 148 conferências, ele também será contabilizado como um único organizador exclusivo.</span><span class="sxs-lookup"><span data-stu-id="8479e-111">If Ken Myer schedules 148 conferences he, too counts as one unique organizer.</span></span> <span data-ttu-id="8479e-112">Por exemplo, a tabela a seguir mostra 8 conferências agendadas, mas apenas três organizadores exclusivos (Ken Myer, pilar Alverca e David ahs).</span><span class="sxs-lookup"><span data-stu-id="8479e-112">For example, the table below shows 8 conferences scheduled, but just three unique organizers (Ken Myer, Pilar Ackerman, and David Ahs).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8479e-113">Organizador da conferência</span><span class="sxs-lookup"><span data-stu-id="8479e-113">Conference Organizer</span></span></th>
<th><span data-ttu-id="8479e-114">Data da conferência</span><span class="sxs-lookup"><span data-stu-id="8479e-114">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8479e-115">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="8479e-115">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="8479e-116">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="8479e-116">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8479e-117">David Ahs</span><span class="sxs-lookup"><span data-stu-id="8479e-117">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="8479e-118">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="8479e-118">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8479e-119">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="8479e-119">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="8479e-120">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="8479e-120">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8479e-121">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="8479e-121">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="8479e-122">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="8479e-122">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8479e-123">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="8479e-123">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="8479e-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8479e-124">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8479e-125">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="8479e-125">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="8479e-126">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="8479e-126">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8479e-127">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="8479e-127">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="8479e-128">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="8479e-128">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8479e-129">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="8479e-129">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="8479e-130">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="8479e-130">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8479e-131">O Relatório de Resumo de Conferências também indica quantas conferências incluíram áudio e/ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="8479e-131">The Conference Summary Report also indicates how many conferences included audio and/or video.</span></span>

<div>

## <a name="accessing-the-conference-summary-report"></a><span data-ttu-id="8479e-132">Acessando o Relatório de Resumo de Conferências</span><span class="sxs-lookup"><span data-stu-id="8479e-132">Accessing the Conference Summary Report</span></span>

<span data-ttu-id="8479e-p103">O Relatório de Resumo de Conferências pode ser acessado na home page Relatórios de Monitoramento. Você pode filtrar pelo Relatório de Atividade de Conferência clicando em uma das métricas a seguir:</span><span class="sxs-lookup"><span data-stu-id="8479e-p103">The Conference Summary Report is accessed from the Monitoring Reports home page. You can drill down to the Conference Activity report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="8479e-135">Total de conferências</span><span class="sxs-lookup"><span data-stu-id="8479e-135">Total conferences</span></span>

  - <span data-ttu-id="8479e-136">Total de participantes</span><span class="sxs-lookup"><span data-stu-id="8479e-136">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a><span data-ttu-id="8479e-137">Usando o Relatório de Resumo de Conferências da melhor maneira possível</span><span class="sxs-lookup"><span data-stu-id="8479e-137">Making the Best Use of the Conference Summary Report</span></span>

<span data-ttu-id="8479e-138">Os valores totais para a maioria das métricas usadas no relatório de Resumo de conferências podem ser encontrados na parte inferior do relatório; Role para baixo para ver valores como o número total de conferências mantidas durante o período de tempo especificado e o número total de pessoas que participaram dessas conferências.</span><span class="sxs-lookup"><span data-stu-id="8479e-138">Total values for most of the metrics used on the Conference Summary Report can be found at the bottom of the report; scroll down to see values such as the total number of conferences held during the specified time period, and the total number of people who participated in those conferences.</span></span> <span data-ttu-id="8479e-139">Uma métrica que não está totalizada na parte inferior do relatório é o total de organizadores de conferências exclusivos.</span><span class="sxs-lookup"><span data-stu-id="8479e-139">One metric that is not totaled at the bottom of the report is Total unique conference organizers.</span></span> <span data-ttu-id="8479e-140">Por que não?</span><span class="sxs-lookup"><span data-stu-id="8479e-140">Why not?</span></span> <span data-ttu-id="8479e-141">Aqui está um motivo.</span><span class="sxs-lookup"><span data-stu-id="8479e-141">Here’s one reason.</span></span> <span data-ttu-id="8479e-142">Suponha que você esteja olhando para o valor de dados de um mês.</span><span class="sxs-lookup"><span data-stu-id="8479e-142">Suppose you are looking at a month's worth of data.</span></span> <span data-ttu-id="8479e-143">No dia 1, você tinha 34 organizadores de conferência exclusivos; no dia 2, você tinha 27 organizadores de conferências exclusivos.</span><span class="sxs-lookup"><span data-stu-id="8479e-143">On day 1 you had 34 unique conference organizers; on day 2 you had 27 unique conference organizers.</span></span> <span data-ttu-id="8479e-144">Isso significa que você tinha 61 organizadores de conferência exclusivos para estes dois dias?</span><span class="sxs-lookup"><span data-stu-id="8479e-144">Does that mean you had 61 unique conference organizers for those two days?</span></span> <span data-ttu-id="8479e-145">Não necessariamente.</span><span class="sxs-lookup"><span data-stu-id="8479e-145">Not necessarily.</span></span> <span data-ttu-id="8479e-146">Afinal, todas as 27 pessoas que organizaram conferências no dia 2 podem estar entre as pessoas do 34 que organizaram conferências no dia 1.</span><span class="sxs-lookup"><span data-stu-id="8479e-146">After all, all 27 people who organized conferences on day 2 might be among the 34 people who organized conferences on day 1.</span></span> <span data-ttu-id="8479e-147">Por exemplo, neste relatório simples, observe que Ken Myer e pilar Alverca conferências agendadas no 7/7/2012 e no 7/2/2012:</span><span class="sxs-lookup"><span data-stu-id="8479e-147">For example, in this simple report, note that Ken Myer and Pilar Ackerman scheduled conferences both on 7/7/2012 and on 7/2/2012:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8479e-148">Organizador da conferência</span><span class="sxs-lookup"><span data-stu-id="8479e-148">Conference Organizer</span></span></th>
<th><span data-ttu-id="8479e-149">Data da conferência</span><span class="sxs-lookup"><span data-stu-id="8479e-149">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8479e-150">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="8479e-150">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="8479e-151">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="8479e-151">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8479e-152">David Ahs</span><span class="sxs-lookup"><span data-stu-id="8479e-152">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="8479e-153">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="8479e-153">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8479e-154">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="8479e-154">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="8479e-155">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="8479e-155">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8479e-156">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="8479e-156">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="8479e-157">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="8479e-157">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8479e-158">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="8479e-158">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="8479e-159">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8479e-159">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8479e-160">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="8479e-160">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="8479e-161">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="8479e-161">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8479e-162">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="8479e-162">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="8479e-163">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="8479e-163">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8479e-164">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="8479e-164">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="8479e-165">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="8479e-165">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8479e-166">Para ter uma ideia melhor do número total de usuários exclusivos que organizaram conferências, altere o intervalo de tempo. Por exemplo, exiba os dados por mês e não por dia.</span><span class="sxs-lookup"><span data-stu-id="8479e-166">To get a better idea of the total number of unique users who organized conferences, change your time interval; for example, look at the data by month instead of by day.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8479e-167">Filtros</span><span class="sxs-lookup"><span data-stu-id="8479e-167">Filters</span></span>

<span data-ttu-id="8479e-p105">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de diferentes maneiras. Por exemplo, o Relatório de Resumo de Conferências permite que você escolha como os dados devem ser agrupados. Nesse caso, conferências agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="8479e-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Summary Report enables you to choose how data should be grouped. In this case, conferences grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="8479e-171">A tabela a seguir lista os filtros que você pode usar com o Relatório de Resumo de Conferências.</span><span class="sxs-lookup"><span data-stu-id="8479e-171">The following table lists the filters that you can use with the Conference Summary Report.</span></span>

### <a name="conference-summary-report-filters"></a><span data-ttu-id="8479e-172">Filtros do Relatório de Resumo de Conferências</span><span class="sxs-lookup"><span data-stu-id="8479e-172">Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8479e-173">Nome</span><span class="sxs-lookup"><span data-stu-id="8479e-173">Name</span></span></th>
<th><span data-ttu-id="8479e-174">Descrição</span><span class="sxs-lookup"><span data-stu-id="8479e-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8479e-175"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-175"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8479e-p106">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="8479e-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8479e-178">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8479e-178">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8479e-p107">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="8479e-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8479e-181">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8479e-181">7/7/2012</span></span></p>
<p><span data-ttu-id="8479e-182">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="8479e-182">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8479e-183">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8479e-183">7/3/2012</span></span></p>
<p><span data-ttu-id="8479e-184">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="8479e-184">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8479e-185"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-185"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8479e-p108">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="8479e-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8479e-188">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8479e-188">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8479e-p109">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="8479e-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8479e-191">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8479e-191">7/7/2012</span></span></p>
<p><span data-ttu-id="8479e-192">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="8479e-192">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8479e-193">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8479e-193">7/3/2012</span></span></p>
<p><span data-ttu-id="8479e-194">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="8479e-194">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8479e-195"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-195"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="8479e-p110">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="8479e-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8479e-198">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="8479e-198">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8479e-199">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="8479e-199">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8479e-200">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="8479e-200">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8479e-201">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="8479e-201">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="8479e-202">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, apenas o número máximo de valores (começando pela data de início) será exibido.</span><span class="sxs-lookup"><span data-stu-id="8479e-202">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="8479e-203">Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/7/2012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/2012 12:00 AM a 9/7/2012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</span><span class="sxs-lookup"><span data-stu-id="8479e-203">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="8479e-204">Métricas</span><span class="sxs-lookup"><span data-stu-id="8479e-204">Metrics</span></span>

<span data-ttu-id="8479e-205">A tabela a seguir as informações fornecidas pelo Relatório de Resumo de Conferências.</span><span class="sxs-lookup"><span data-stu-id="8479e-205">The following table the information provided by the Conferences Summary Report.</span></span>

### <a name="conference-summary-report-metrics"></a><span data-ttu-id="8479e-206">Métricas do Relatório de Resumo de Conferências</span><span class="sxs-lookup"><span data-stu-id="8479e-206">Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8479e-207">Nome</span><span class="sxs-lookup"><span data-stu-id="8479e-207">Name</span></span></th>
<th><span data-ttu-id="8479e-208">Você pode classificar este item?</span><span class="sxs-lookup"><span data-stu-id="8479e-208">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8479e-209">Descrição</span><span class="sxs-lookup"><span data-stu-id="8479e-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8479e-210"><strong>Por hora</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-210"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="8479e-211"><strong>Diário</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-211"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="8479e-212"><strong>Semanal</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-212"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="8479e-213"><strong>Mensal</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-213"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="8479e-214">Não</span><span class="sxs-lookup"><span data-stu-id="8479e-214">No</span></span></p></td>
<td><p><span data-ttu-id="8479e-215">Indica o intervalo de tempo selecionado na barra de ferramentas de filtro.</span><span class="sxs-lookup"><span data-stu-id="8479e-215">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="8479e-216">Quando aplicável, é possível clicar em determinado intervalo de tempo para exibir informações detalhadas sobre ele.</span><span class="sxs-lookup"><span data-stu-id="8479e-216">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="8479e-217">Por exemplo, se você estiver usando o intervalo diário e clicar em 7/7/2012, verá um detalhamento por hora da atividade de registro do usuário para essa data.</span><span class="sxs-lookup"><span data-stu-id="8479e-217">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8479e-218"><strong>Conferências totais</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-218"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="8479e-219">Não</span><span class="sxs-lookup"><span data-stu-id="8479e-219">No</span></span></p></td>
<td><p><span data-ttu-id="8479e-p113">Número total de conferências (independentemente do tipo de conferência) que foram mantidas. Quando você clica nesse item, o relatório mostra o Relatório de Resumo de Conferências para o período de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="8479e-p113">Total number of conferences (regardless of conference type) that were held. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8479e-222"><strong>Total de participantes</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-222"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="8479e-223">Não</span><span class="sxs-lookup"><span data-stu-id="8479e-223">No</span></span></p></td>
<td><p><span data-ttu-id="8479e-p114">Número total de pessoas que participaram nas conferências. Quando você clica nesse item, o relatório mostra o Relatório de Resumo de Conferências para o período de tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="8479e-p114">Total number of people who took part in the conferences. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8479e-226"><strong>Média de participantes por conferência</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-226"><strong>Average participants per conference</strong></span></span></p></td>
<td><p><span data-ttu-id="8479e-227">Não</span><span class="sxs-lookup"><span data-stu-id="8479e-227">No</span></span></p></td>
<td><p><span data-ttu-id="8479e-p115">Número médio de pessoas que participaram de uma determinada conferência. É determinado dividindo o total de conferências pelo total de participantes.</span><span class="sxs-lookup"><span data-stu-id="8479e-p115">Average number of people who took part in a given conference. Determined by dividing the total conferences by the total participants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8479e-230"><strong>Total de conferências A/V</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-230"><strong>Total A/V conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="8479e-231">Não</span><span class="sxs-lookup"><span data-stu-id="8479e-231">No</span></span></p></td>
<td><p><span data-ttu-id="8479e-232">Número total de conferências com áudio ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="8479e-232">Total number of conferences that included audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8479e-233"><strong>Total de minutos de conferências de A/V</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-233"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="8479e-234">Não</span><span class="sxs-lookup"><span data-stu-id="8479e-234">No</span></span></p></td>
<td><p><span data-ttu-id="8479e-235">Número total de minutos para a conferência de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="8479e-235">Total number of minutes devoted to audio/video conferencing.</span></span></p>
<p><span data-ttu-id="8479e-236">A métrica de minutos total de conferência a/V resume todos os tipos de áudio/conferência Visual, incluindo: conferências A/V; Conferências de mensagens instantâneas; conferências de compartilhamento de aplicativos; conferências de dados; e conferências PSTN.</span><span class="sxs-lookup"><span data-stu-id="8479e-236">The Total A/V conference minutes metric summarizes all the audio/visual conference types, including: A/V conferences; IM conferences; app sharing conferences; data conferences; and PSTN conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8479e-237"><strong>Total de minutos de participantes de conferências de A/V</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-237"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="8479e-238">Não</span><span class="sxs-lookup"><span data-stu-id="8479e-238">No</span></span></p></td>
<td><p><span data-ttu-id="8479e-p116">Número total de minutos do participante na conferência de áudio/vídeo. Por exemplo, suponha que um usuário gaste cinco minutos em uma conferência de áudio/vídeo e um segundo usuário gaste três minutos nessa mesma conferência. O que soma um total de oito minutos de participantes: cinco minutos mais três minutos.</span><span class="sxs-lookup"><span data-stu-id="8479e-p116">Total number of participant minutes devoted to audio/video conferencing. For example, suppose one user spends 5 minutes in an audio/video conference and a second user spends 3 minutes in that same conference. That makes a total of 8 participant minutes: 5 minutes plus 3 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8479e-242"><strong>Média de minutos da conferência A/V</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-242"><strong>Average A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="8479e-243">Não</span><span class="sxs-lookup"><span data-stu-id="8479e-243">No</span></span></p></td>
<td><p><span data-ttu-id="8479e-244">Número médio de minutos por conferência de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="8479e-244">Average number of minutes per audio/video conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8479e-245"><strong>Número total de organizadores exclusivos de conferências</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-245"><strong>Total number of unique organizers of conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="8479e-246">Não</span><span class="sxs-lookup"><span data-stu-id="8479e-246">No</span></span></p></td>
<td><p><span data-ttu-id="8479e-p117">Número total de usuários que organizaram pelo menos uma conferência. Os usuários que organizaram mais de uma conferência são contados como um organizador exclusivo, assim como os usuários que só organizaram uma única conferência.</span><span class="sxs-lookup"><span data-stu-id="8479e-p117">Total number of users who organized at least one conference. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8479e-249"><strong>Total de mensagens de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="8479e-249"><strong>Total conference messages</strong></span></span></p></td>
<td><p><span data-ttu-id="8479e-250">Não</span><span class="sxs-lookup"><span data-stu-id="8479e-250">No</span></span></p></td>
<td><p><span data-ttu-id="8479e-251">Número total de mensagens instantâneas enviadas durante as conferências.</span><span class="sxs-lookup"><span data-stu-id="8479e-251">Total number of instant messages sent during the conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

