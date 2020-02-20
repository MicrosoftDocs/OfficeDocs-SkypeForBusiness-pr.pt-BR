---
title: 'Lync Server 2013: relatório de tempo de ingresso em conferência'
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
ms.openlocfilehash: e11932d1f63e6d756b0a3a5ba1eb7b33498dac61
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="2cb21-102">Relatório de tempo de ingresso em conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2cb21-102">Conference Join Time Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cb21-103">_**Última modificação do tópico:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="2cb21-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="2cb21-p101">O Sumário de Tempo de Ingresso em Conferência permite que você determine quanto tempo demora para que seus usuários ingressem em uma conferência. Um relatório mostra o tempo médio de ingresso (em milissegundos), e também oferece um detalhamento que permite que você saiba quantos usuários foram capazes de se juntar a uma conferência em 2 segundos ou menos, quantos usuários necessitaram de 2 a 5 segundos para ingressar em uma conferência, etc.</span><span class="sxs-lookup"><span data-stu-id="2cb21-p101">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference. The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="2cb21-106">Acessando o Relatório de Tempo de Ingresso em Conferência</span><span class="sxs-lookup"><span data-stu-id="2cb21-106">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="2cb21-107">O Relatório de Tempo de Ingresso em Conferência é acessado através da página inicial dos Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="2cb21-107">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2cb21-108">Filtros</span><span class="sxs-lookup"><span data-stu-id="2cb21-108">Filters</span></span>

<span data-ttu-id="2cb21-p102">Os filtros oferecem uma forma de retornar um conjunto de dados mais direcionado ou exibir os dados devolvidos em formas diferentes. A tabela a seguir lista os filtros que você pode usar com o Relatórios de Tempo de Ingresso em Conferência.</span><span class="sxs-lookup"><span data-stu-id="2cb21-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="2cb21-111">Filtros de Relatório de Tempo de Ingresso em Conferência</span><span class="sxs-lookup"><span data-stu-id="2cb21-111">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cb21-112">Nome</span><span class="sxs-lookup"><span data-stu-id="2cb21-112">Name</span></span></th>
<th><span data-ttu-id="2cb21-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="2cb21-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cb21-114"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-p103">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="2cb21-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2cb21-117">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="2cb21-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2cb21-p104">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="2cb21-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2cb21-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2cb21-120">7/7/2012</span></span></p>
<p><span data-ttu-id="2cb21-121">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="2cb21-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2cb21-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2cb21-122">7/3/2012</span></span></p>
<p><span data-ttu-id="2cb21-123">As semanas sempre são de Domingo a Sábado.</span><span class="sxs-lookup"><span data-stu-id="2cb21-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb21-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-p105">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="2cb21-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2cb21-127">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="2cb21-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2cb21-p106">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="2cb21-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2cb21-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2cb21-130">7/7/2012</span></span></p>
<p><span data-ttu-id="2cb21-131">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="2cb21-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2cb21-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2cb21-132">7/3/2012</span></span></p>
<p><span data-ttu-id="2cb21-133">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="2cb21-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb21-134"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-p107">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="2cb21-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cb21-137">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="2cb21-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2cb21-138">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="2cb21-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2cb21-139">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="2cb21-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2cb21-140">Mensalmente (é possível exibir no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="2cb21-140">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="2cb21-p108">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com a data de início 07.07.12 e uma data de término de 28.02.12, os dados serão exibidos para os dias 07.08.12 12:00 AM até 07.09.12 12:00 AM (ou seja, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="2cb21-p108">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb21-143"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-143"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-p109">FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em <strong>[Tudo]</strong> para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2cb21-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb21-147"><strong>Sessões de conferência</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-147"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-p110">Tipo de sessão. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="2cb21-p110">Type of session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cb21-150">Todos os</span><span class="sxs-lookup"><span data-stu-id="2cb21-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="2cb21-151">Sessões de foco (o foco é a política central e o Gerenciador de estado para reuniões online e coordena todos os aspectos de uma conferência</span><span class="sxs-lookup"><span data-stu-id="2cb21-151">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="2cb21-152">Compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="2cb21-152">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="2cb21-153">Conferências A/V</span><span class="sxs-lookup"><span data-stu-id="2cb21-153">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="2cb21-p111">Caso selecione [Todos], o tempo total de ingresso em conferência será exibido no topo do relatório. Observe que estes totais são apenas para conferências que foram agendadas usando o Microsoft Exchange ou o Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="2cb21-p111">If you select [All], the total conference join time will be displayed at the top of the report. Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2cb21-156">Métricas</span><span class="sxs-lookup"><span data-stu-id="2cb21-156">Metrics</span></span>

<span data-ttu-id="2cb21-157">A tabela a seguir lista as informações fornecidas no Relatório de Tempo de Ingresso em Conferência.</span><span class="sxs-lookup"><span data-stu-id="2cb21-157">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="2cb21-158">Métricas do Relatório de Tempo de Ingresso em Conferência</span><span class="sxs-lookup"><span data-stu-id="2cb21-158">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cb21-159">Nome</span><span class="sxs-lookup"><span data-stu-id="2cb21-159">Name</span></span></th>
<th><span data-ttu-id="2cb21-160">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="2cb21-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2cb21-161">Descrição</span><span class="sxs-lookup"><span data-stu-id="2cb21-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cb21-162"><strong>Data</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-162"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="2cb21-163">O título para essa métrica irá variar dependendo do Intervalo selecionado.</span><span class="sxs-lookup"><span data-stu-id="2cb21-163">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="2cb21-164">Não</span><span class="sxs-lookup"><span data-stu-id="2cb21-164">No</span></span></p></td>
<td><p><span data-ttu-id="2cb21-165">Data e horário em que aconteceu a conferência.</span><span class="sxs-lookup"><span data-stu-id="2cb21-165">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb21-166"><strong>Total de sessões</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-166"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-167">Não</span><span class="sxs-lookup"><span data-stu-id="2cb21-167">No</span></span></p></td>
<td><p><span data-ttu-id="2cb21-168">Número total de sessões, incluindo sessões bem-sucedidas, com falha (tanto falhas esperadas quanto inesperadas) e sessões não categorizadas.</span><span class="sxs-lookup"><span data-stu-id="2cb21-168">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb21-169"><strong>Média (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-169"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-170">Não</span><span class="sxs-lookup"><span data-stu-id="2cb21-170">No</span></span></p></td>
<td><p><span data-ttu-id="2cb21-171">Média de tempo (em milissegundos) que demorou para que os participantes ingressassem na conferência.</span><span class="sxs-lookup"><span data-stu-id="2cb21-171">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb21-172"><strong>Sessões &lt; de 2 segundos, volume</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-172"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-173">Não</span><span class="sxs-lookup"><span data-stu-id="2cb21-173">No</span></span></p></td>
<td><p><span data-ttu-id="2cb21-174">Número de participantes que conseguiram ingressar na conferência em menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="2cb21-174">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb21-175"><strong>Sessões &lt; 2 segundos, porcentagem</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-175"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-176">Não</span><span class="sxs-lookup"><span data-stu-id="2cb21-176">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb21-177"><strong>Sessões de 2 a 5 segundos, Volume</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-177"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-178">Não</span><span class="sxs-lookup"><span data-stu-id="2cb21-178">No</span></span></p></td>
<td><p><span data-ttu-id="2cb21-179">Número de participantes que demoraram de 2 a 5 segundos para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="2cb21-179">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb21-180"><strong>Sessões de 2 a 5 segundos, Porcentagem</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-180"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-181">Não</span><span class="sxs-lookup"><span data-stu-id="2cb21-181">No</span></span></p></td>
<td><p><span data-ttu-id="2cb21-182">Porcentagem do total de participantes da chamada demoraram entre 2 a 5 segundos para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="2cb21-182">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb21-183"><strong>Sessões de 5 a 10 segundos, Volume</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-183"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-184">Não</span><span class="sxs-lookup"><span data-stu-id="2cb21-184">No</span></span></p></td>
<td><p><span data-ttu-id="2cb21-185">Número de participantes que demoraram entre 5 a 10 segundos para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="2cb21-185">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb21-186"><strong>Sessões de 5 a 10 segundos, Porcentagem</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-186"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-187">Não</span><span class="sxs-lookup"><span data-stu-id="2cb21-187">No</span></span></p></td>
<td><p><span data-ttu-id="2cb21-188">Porcentagem do total de participantes de chamadas que demoraram entre 5 a 10 segundos para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="2cb21-188">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cb21-189"><strong>Sessões &gt; de 10 segundos, volume</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-189"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-190">Não</span><span class="sxs-lookup"><span data-stu-id="2cb21-190">No</span></span></p></td>
<td><p><span data-ttu-id="2cb21-191">Número de participantes que precisaram de mais de 10 segundos para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="2cb21-191">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cb21-192"><strong>Sessões &gt; de 10 segundos, porcentagem</strong></span><span class="sxs-lookup"><span data-stu-id="2cb21-192"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2cb21-193">Não</span><span class="sxs-lookup"><span data-stu-id="2cb21-193">No</span></span></p></td>
<td><p><span data-ttu-id="2cb21-194">Porcentagem do total de participantes de chamadas que precisaram de mais de 10 segundos para ingressar na conferência.</span><span class="sxs-lookup"><span data-stu-id="2cb21-194">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

