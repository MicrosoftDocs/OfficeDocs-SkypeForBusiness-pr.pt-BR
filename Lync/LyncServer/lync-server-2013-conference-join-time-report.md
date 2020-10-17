---
title: 'Lync Server 2013: relatório de tempo de ingresso em conferência'
description: 'Lync Server 2013: relatório de tempo de ingresso em conferência.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd4aa5d21a8109a323bb953c7196f43715d51413
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542787"
---
# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="0530e-103">Relatório de tempo de ingresso em conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0530e-103">Conference Join Time Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0530e-104">_**Última modificação do tópico:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="0530e-104">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="0530e-p101">O Sumário de Tempo de Ingresso em Conferência permite que você determine quanto tempo demora para que seus usuários ingressem em uma conferência. Um relatório mostra o tempo médio de ingresso (em milissegundos), e também oferece um detalhamento que permite que você saiba quantos usuários foram capazes de se juntar a uma conferência em 2 segundos ou menos, quantos usuários necessitaram de 2 a 5 segundos para ingressar em uma conferência, etc.</span><span class="sxs-lookup"><span data-stu-id="0530e-p101">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference. The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="0530e-107">Acessando o Relatório de Tempo de Ingresso em Conferência</span><span class="sxs-lookup"><span data-stu-id="0530e-107">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="0530e-108">O Relatório de Tempo de Ingresso em Conferência é acessado através da página inicial dos Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="0530e-108">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0530e-109">Filtros</span><span class="sxs-lookup"><span data-stu-id="0530e-109">Filters</span></span>

<span data-ttu-id="0530e-p102">Os filtros oferecem uma forma de retornar um conjunto de dados mais direcionado ou exibir os dados devolvidos em formas diferentes. A tabela a seguir lista os filtros que você pode usar com o Relatórios de Tempo de Ingresso em Conferência.</span><span class="sxs-lookup"><span data-stu-id="0530e-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="0530e-112">Filtros de Relatório de Tempo de Ingresso em Conferência</span><span class="sxs-lookup"><span data-stu-id="0530e-112">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0530e-113">Nome</span><span class="sxs-lookup"><span data-stu-id="0530e-113">Name</span></span></th>
<th><span data-ttu-id="0530e-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="0530e-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0530e-115"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-115"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-p103">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="0530e-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0530e-118">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="0530e-118">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0530e-p104">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="0530e-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0530e-121">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0530e-121">7/7/2012</span></span></p>
<p><span data-ttu-id="0530e-122">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="0530e-122">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0530e-123">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0530e-123">7/3/2012</span></span></p>
<p><span data-ttu-id="0530e-124">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="0530e-124">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0530e-125"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-125"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-p105">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="0530e-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0530e-128">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="0530e-128">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0530e-p106">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="0530e-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0530e-131">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0530e-131">7/7/2012</span></span></p>
<p><span data-ttu-id="0530e-132">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="0530e-132">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0530e-133">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0530e-133">7/3/2012</span></span></p>
<p><span data-ttu-id="0530e-134">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="0530e-134">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0530e-135"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-135"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-p107">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="0530e-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0530e-138">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="0530e-138">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0530e-139">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="0530e-139">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0530e-140">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="0530e-140">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0530e-141">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="0530e-141">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="0530e-p108">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com a data de início 07.07.12 e uma data de término de 28.02.12, os dados serão exibidos para os dias 07.08.12 12:00 AM até 07.09.12 12:00 AM (ou seja, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="0530e-p108">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0530e-144"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-144"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-p109">FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Tudo]</strong> para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0530e-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0530e-148"><strong>Sessões de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-148"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-p110">Tipo de sessão. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="0530e-p110">Type of session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="0530e-151">Todos os</span><span class="sxs-lookup"><span data-stu-id="0530e-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="0530e-152">Sessões de foco (o foco é a política central e o Gerenciador de estado para reuniões online e coordena todos os aspectos de uma conferência</span><span class="sxs-lookup"><span data-stu-id="0530e-152">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="0530e-153">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="0530e-153">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="0530e-154">Conferências A/V</span><span class="sxs-lookup"><span data-stu-id="0530e-154">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="0530e-p111">Caso selecione [Todos], o tempo total de ingresso em conferência será exibido no topo do relatório. Observe que estes totais são apenas para conferências que foram agendadas usando o Microsoft Exchange ou o Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="0530e-p111">If you select [All], the total conference join time will be displayed at the top of the report. Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="0530e-157">Métrica</span><span class="sxs-lookup"><span data-stu-id="0530e-157">Metrics</span></span>

<span data-ttu-id="0530e-158">A tabela a seguir lista as informações fornecidas no Relatório de Tempo de Ingresso em Conferência.</span><span class="sxs-lookup"><span data-stu-id="0530e-158">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="0530e-159">Métricas do Relatório de Tempo de Ingresso em Conferência</span><span class="sxs-lookup"><span data-stu-id="0530e-159">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0530e-160">Nome</span><span class="sxs-lookup"><span data-stu-id="0530e-160">Name</span></span></th>
<th><span data-ttu-id="0530e-161">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="0530e-161">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0530e-162">Descrição</span><span class="sxs-lookup"><span data-stu-id="0530e-162">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0530e-163"><strong>Data</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-163"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="0530e-164">O título para essa métrica irá variar dependendo do Intervalo selecionado.</span><span class="sxs-lookup"><span data-stu-id="0530e-164">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="0530e-165">Não</span><span class="sxs-lookup"><span data-stu-id="0530e-165">No</span></span></p></td>
<td><p><span data-ttu-id="0530e-166">Data e horário em que aconteceu a conferência.</span><span class="sxs-lookup"><span data-stu-id="0530e-166">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0530e-167"><strong>Total de sessões</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-167"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-168">Não</span><span class="sxs-lookup"><span data-stu-id="0530e-168">No</span></span></p></td>
<td><p><span data-ttu-id="0530e-169">Número total de sessões, incluindo sessões bem-sucedidas, com falha (tanto falhas esperadas quanto inesperadas) e sessões não categorizadas.</span><span class="sxs-lookup"><span data-stu-id="0530e-169">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0530e-170"><strong>Média (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-170"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-171">Não</span><span class="sxs-lookup"><span data-stu-id="0530e-171">No</span></span></p></td>
<td><p><span data-ttu-id="0530e-172">Média de tempo (em milissegundos) que demorou para que os participantes ingressassem na conferência.</span><span class="sxs-lookup"><span data-stu-id="0530e-172">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0530e-173"><strong>Sessões &lt; de 2 segundos, volume</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-173"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-174">Não</span><span class="sxs-lookup"><span data-stu-id="0530e-174">No</span></span></p></td>
<td><p><span data-ttu-id="0530e-175">Número de participantes que conseguiram ingressar na conferência em menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="0530e-175">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0530e-176"><strong>Sessões &lt; 2 segundos, porcentagem</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-176"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-177">Não</span><span class="sxs-lookup"><span data-stu-id="0530e-177">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0530e-178"><strong>Sessões de 2 a 5 segundos, Volume</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-178"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-179">Não</span><span class="sxs-lookup"><span data-stu-id="0530e-179">No</span></span></p></td>
<td><p><span data-ttu-id="0530e-180">Número de participantes que demoraram de 2 a 5 segundos para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="0530e-180">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0530e-181"><strong>Sessões de 2 a 5 segundos, Porcentagem</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-181"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-182">Não</span><span class="sxs-lookup"><span data-stu-id="0530e-182">No</span></span></p></td>
<td><p><span data-ttu-id="0530e-183">Porcentagem do total de participantes da chamada demoraram entre 2 a 5 segundos para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="0530e-183">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0530e-184"><strong>Sessões de 5 a 10 segundos, Volume</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-184"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-185">Não</span><span class="sxs-lookup"><span data-stu-id="0530e-185">No</span></span></p></td>
<td><p><span data-ttu-id="0530e-186">Número de participantes que demoraram entre 5 a 10 segundos para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="0530e-186">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0530e-187"><strong>Sessões de 5 a 10 segundos, Porcentagem</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-187"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-188">Não</span><span class="sxs-lookup"><span data-stu-id="0530e-188">No</span></span></p></td>
<td><p><span data-ttu-id="0530e-189">Porcentagem do total de participantes de chamadas que demoraram entre 5 a 10 segundos para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="0530e-189">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0530e-190"><strong>Sessões &gt; de 10 segundos, volume</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-190"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-191">Não</span><span class="sxs-lookup"><span data-stu-id="0530e-191">No</span></span></p></td>
<td><p><span data-ttu-id="0530e-192">Número de participantes que precisaram de mais de 10 segundos para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="0530e-192">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0530e-193"><strong>Sessões &gt; de 10 segundos, porcentagem</strong></span><span class="sxs-lookup"><span data-stu-id="0530e-193"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0530e-194">Não</span><span class="sxs-lookup"><span data-stu-id="0530e-194">No</span></span></p></td>
<td><p><span data-ttu-id="0530e-195">Porcentagem do total de participantes de chamadas que precisaram de mais de 10 segundos para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="0530e-195">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

