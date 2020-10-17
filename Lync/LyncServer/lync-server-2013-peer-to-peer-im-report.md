---
title: 'Lync Server 2013: relatório de mensagens instantâneas ponto a ponto'
description: 'Lync Server 2013: relatório de mensagens instantâneas ponto a ponto.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eac6291d0f099af8269ed15f7dc8c654ac944ed0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557287"
---
# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="1698c-103">Relatório de mensagens instantâneas ponto a ponto no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1698c-103">Peer-to-Peer IM Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1698c-104">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1698c-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1698c-p101">O Relatório de Mensagens Instantâneas Ponto a Ponto fornece informações de tendência sobre sessões de IM (mensagens instantâneas) ponto a ponto, detalhadas por pool e tipo de autenticação. O relatório pode mostrar o número total de sessões que aconeceram durante o período de tempo especificado (por exemplo, dia por dia ou hora por hora), ou pode mostrar o número total de mensagens instantâneas enviadas durante esse período de tempo.</span><span class="sxs-lookup"><span data-stu-id="1698c-p101">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type. The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="1698c-107">Acessando o Relatório de Mensagens Instantâneas Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="1698c-107">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="1698c-108">Você pode acessar o relatório de mensagens instantâneas ponto a ponto apenas abrindo o [relatório de Resumo de atividades ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) e, em seguida, clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="1698c-108">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="1698c-109">Total de sessões de mensagens instantâneas ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="1698c-109">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="1698c-110">Total de mensagens de IM ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="1698c-110">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="1698c-111">Usando o Relatório de Mensagens Instantâneas Ponto a Ponto da melhor maneira possível</span><span class="sxs-lookup"><span data-stu-id="1698c-111">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="1698c-p102">Por padrão, o Relatório de Mensagens Instantâneas Ponto a Ponto mostra a você a conagem de mensagens por hora (ou dia, dependendo de suas configurações). No entanto, você também pode escolher visualizar o dia por sessões por hora. Para fazer isso, clique em **Ocultar/Exibir Parâmetros** no canto superior direito da janela Relatórios, e então clique em **Contagem de Sessão** a partir da lista **Relatar por**.</span><span class="sxs-lookup"><span data-stu-id="1698c-p102">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings). However, you can also choose to view the day by sessions per hour. To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1698c-115">Filtros</span><span class="sxs-lookup"><span data-stu-id="1698c-115">Filters</span></span>

<span data-ttu-id="1698c-p103">Os filtros fornecem uma maneira de obter um resultado mais refinado de conjunto de dados ou visualizar os dados resultantes de maneiras diferentes. A tabela a seguir lista os filtros que você pode utilizar com o Relatório do Sistema de Mensagens Instantâneas Ponto a Ponto.</span><span class="sxs-lookup"><span data-stu-id="1698c-p103">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="1698c-118">Filtros do Relatório do Sistema de Mensagens Instantâneas Ponto a Ponto</span><span class="sxs-lookup"><span data-stu-id="1698c-118">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1698c-119">Nome</span><span class="sxs-lookup"><span data-stu-id="1698c-119">Name</span></span></th>
<th><span data-ttu-id="1698c-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="1698c-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1698c-121"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="1698c-121"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1698c-p104">Data e hora de início para o intervalo de tempo. Para ver os dados por hora, digite a data e hora de início no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="1698c-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1698c-124">07/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="1698c-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1698c-p105">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="1698c-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1698c-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1698c-127">7/7/2012</span></span></p>
<p><span data-ttu-id="1698c-128">Para visualizar por semana ou por mês, digite uma data qualquer da semana ou mês (não é necessário digitar o primeiro dia da semana ou mês)</span><span class="sxs-lookup"><span data-stu-id="1698c-128">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1698c-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1698c-129">7/3/2012</span></span></p>
<p><span data-ttu-id="1698c-130">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="1698c-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1698c-131"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="1698c-131"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1698c-p106">Data e hora de término para o dia intervalo de tempo. Para ver os dados por hora, digite a data e a hora de término no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="1698c-p106">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1698c-134">07/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="1698c-134">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1698c-p107">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="1698c-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1698c-137">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1698c-137">7/7/2012</span></span></p>
<p><span data-ttu-id="1698c-138">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="1698c-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1698c-139">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1698c-139">7/3/2012</span></span></p>
<p><span data-ttu-id="1698c-140">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="1698c-140">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1698c-141"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="1698c-141"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="1698c-p108">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="1698c-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1698c-144">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="1698c-144">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1698c-145">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="1698c-145">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1698c-146">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="1698c-146">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1698c-147">Mensalmente (exibição de no máximo 12 meses)</span><span class="sxs-lookup"><span data-stu-id="1698c-147">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="1698c-p109">Caso as datas de início e término excedam o número máximo de valores permitidos para o intervalo selecionado, será exibido somente o número máximo de valores (começando a partir da data de inicio). Por exemplo, se você selecionar o intervalo Diariamente com uma data de início em 1/1/2011 e a data de término em 28/02/2012, os dados serão exibidos para dos dias 07/08/2012 12:00 ao 07/09/2012 12:00 (ou seja, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="1698c-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1698c-150"><strong>Relatório por</strong></span><span class="sxs-lookup"><span data-stu-id="1698c-150"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="1698c-p110">Indica os valores a serem usados no relatório. Selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="1698c-p110">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1698c-153">Contagem de sessão</span><span class="sxs-lookup"><span data-stu-id="1698c-153">Session count</span></span></p></li>
<li><p><span data-ttu-id="1698c-154">Contagem de mensagem</span><span class="sxs-lookup"><span data-stu-id="1698c-154">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="1698c-155">Medição da sessão do Sistema de Mensagens Instantâneas Ponto a Ponto por Pool</span><span class="sxs-lookup"><span data-stu-id="1698c-155">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="1698c-156">A tabela a seguir lista as informações fornecidas pelo Relatório do Sistema de Mensagens Instantâneas Ponto a Ponto.</span><span class="sxs-lookup"><span data-stu-id="1698c-156">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="1698c-157">Medição da sessão do Sistema de Mensagens Instantâneas Ponto a Ponto por Pool</span><span class="sxs-lookup"><span data-stu-id="1698c-157">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1698c-158">Nome</span><span class="sxs-lookup"><span data-stu-id="1698c-158">Name</span></span></th>
<th><span data-ttu-id="1698c-159">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="1698c-159">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1698c-160">Descrição</span><span class="sxs-lookup"><span data-stu-id="1698c-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1698c-161"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="1698c-161"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1698c-162">Não</span><span class="sxs-lookup"><span data-stu-id="1698c-162">No</span></span></p></td>
<td><p><span data-ttu-id="1698c-163">Nome do pool de registradores ou servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="1698c-163">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1698c-164"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="1698c-164"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="1698c-165">Não</span><span class="sxs-lookup"><span data-stu-id="1698c-165">No</span></span></p></td>
<td><p><span data-ttu-id="1698c-166">Data e hora em que a sessões ocorreram.</span><span class="sxs-lookup"><span data-stu-id="1698c-166">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1698c-167"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="1698c-167"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="1698c-168">Não</span><span class="sxs-lookup"><span data-stu-id="1698c-168">No</span></span></p></td>
<td><p><span data-ttu-id="1698c-169">Número total de sessões ou de contagem total de mensagens.</span><span class="sxs-lookup"><span data-stu-id="1698c-169">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="1698c-170">Medição da sessão do Sistema de Mensagens Instantâneas Ponto a Ponto por tipo de autenticação</span><span class="sxs-lookup"><span data-stu-id="1698c-170">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="1698c-171">A tabela a seguir lista as informações fornecidas pelo Relatório do Sistema de Mensagens Instantâneas Ponto a Ponto para cada tipo de autenticação usada pelos participantes em uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="1698c-171">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="1698c-172">Medição da sessão do Sistema de Mensagens Instantâneas Ponto a Ponto por tipo de autenticação</span><span class="sxs-lookup"><span data-stu-id="1698c-172">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1698c-173">Nome</span><span class="sxs-lookup"><span data-stu-id="1698c-173">Name</span></span></th>
<th><span data-ttu-id="1698c-174">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="1698c-174">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1698c-175">Descrição</span><span class="sxs-lookup"><span data-stu-id="1698c-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1698c-176"><strong>Tipo de Autenticação</strong>:</span><span class="sxs-lookup"><span data-stu-id="1698c-176"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="1698c-177">Não</span><span class="sxs-lookup"><span data-stu-id="1698c-177">No</span></span></p></td>
<td><p><span data-ttu-id="1698c-p111">Tipo de autenticação usada pelos participantes da sessão. Normalmente, os valores são um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="1698c-p111">Type of authentication used by the session participants. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1698c-180">Enterprise</span><span class="sxs-lookup"><span data-stu-id="1698c-180">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="1698c-181">Fica</span><span class="sxs-lookup"><span data-stu-id="1698c-181">Federated</span></span></p></li>
<li><p><span data-ttu-id="1698c-182">PIC</span><span class="sxs-lookup"><span data-stu-id="1698c-182">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1698c-183"><strong>Data/Hora</strong></span><span class="sxs-lookup"><span data-stu-id="1698c-183"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="1698c-184">Não</span><span class="sxs-lookup"><span data-stu-id="1698c-184">No</span></span></p></td>
<td><p><span data-ttu-id="1698c-185">Data e hora em que a sessões ocorreram.</span><span class="sxs-lookup"><span data-stu-id="1698c-185">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1698c-186"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="1698c-186"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="1698c-187">Não</span><span class="sxs-lookup"><span data-stu-id="1698c-187">No</span></span></p></td>
<td><p><span data-ttu-id="1698c-188">Número total de sessões ou de contagem total de mensagens.</span><span class="sxs-lookup"><span data-stu-id="1698c-188">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

