---
title: 'Lync Server 2013: relatório de tendências de localização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68c1eac461d65c2c0b023086422bb66505e9c929
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-trend-report-in-lync-server-2013"></a><span data-ttu-id="da58b-102">Relatório de tendências de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da58b-102">Location Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da58b-103">_**Tópico da última modificação:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="da58b-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="da58b-104">O Relatório de Tendências de Local fornece informações sobre as tendências de qualidade de chamada para locais de rede.</span><span class="sxs-lookup"><span data-stu-id="da58b-104">The Location Trend Report provides call quality trend information for network locations.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="da58b-105">Filtros</span><span class="sxs-lookup"><span data-stu-id="da58b-105">Filters</span></span>

<span data-ttu-id="da58b-p101">Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Tendências de Local permite filtrar os dados retornados por informações como tipo de acesso (ou seja, acesso interno x acesso externo) ou por conexão de rede com fio/sem fio. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="da58b-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Trend Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, or week.</span></span>

<span data-ttu-id="da58b-110">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Tendências de Local.</span><span class="sxs-lookup"><span data-stu-id="da58b-110">The following table lists the filters that you can use with the Location Trend Report.</span></span>

### <a name="location-trend-report-filters"></a><span data-ttu-id="da58b-111">Filtros do Relatório de Tendências de Local</span><span class="sxs-lookup"><span data-stu-id="da58b-111">Location Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da58b-112">Nome</span><span class="sxs-lookup"><span data-stu-id="da58b-112">Name</span></span></th>
<th><span data-ttu-id="da58b-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="da58b-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da58b-114"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="da58b-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="da58b-p102">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="da58b-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="da58b-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="da58b-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="da58b-p103">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="da58b-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="da58b-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="da58b-120">7/7/2012</span></span></p>
<p><span data-ttu-id="da58b-121">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="da58b-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="da58b-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="da58b-122">7/3/2012</span></span></p>
<p><span data-ttu-id="da58b-123">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="da58b-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da58b-124"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="da58b-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="da58b-p104">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="da58b-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="da58b-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="da58b-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="da58b-p105">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="da58b-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="da58b-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="da58b-130">7/7/2012</span></span></p>
<p><span data-ttu-id="da58b-131">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="da58b-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="da58b-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="da58b-132">7/3/2012</span></span></p>
<p><span data-ttu-id="da58b-133">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="da58b-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da58b-134"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="da58b-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="da58b-p106">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="da58b-p106">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="da58b-137">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="da58b-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="da58b-138">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="da58b-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="da58b-139">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="da58b-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="da58b-p107">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com a data de início 1/1/2012 e a data de término 28/2/2011, os dados serão exibidos para os dias de 1/8/2012 00:00 a 1/9/2012 00:00 (ou seja, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="da58b-p107">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 1/1/2011 and an end date of 2/28/2011, data is displayed for the days 8/1/2011 12:00 AM to 9/1/2011 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da58b-142"><strong>Tipo de acesso</strong></span><span class="sxs-lookup"><span data-stu-id="da58b-142"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="da58b-p108">Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="da58b-p108">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="da58b-145">[Todos]</span><span class="sxs-lookup"><span data-stu-id="da58b-145">[All]</span></span></p></li>
<li><p><span data-ttu-id="da58b-146">Interno</span><span class="sxs-lookup"><span data-stu-id="da58b-146">Internal</span></span></p></li>
<li><p><span data-ttu-id="da58b-147">Externo</span><span class="sxs-lookup"><span data-stu-id="da58b-147">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da58b-148"><strong>Tipo de rede</strong></span><span class="sxs-lookup"><span data-stu-id="da58b-148"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="da58b-p109">Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="da58b-p109">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="da58b-151">[Todos]</span><span class="sxs-lookup"><span data-stu-id="da58b-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="da58b-152">Com fio</span><span class="sxs-lookup"><span data-stu-id="da58b-152">Wired</span></span></p></li>
<li><p><span data-ttu-id="da58b-153">Sem fio</span><span class="sxs-lookup"><span data-stu-id="da58b-153">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da58b-154"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="da58b-154"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="da58b-p110">Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="da58b-p110">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="da58b-157">[Todos]</span><span class="sxs-lookup"><span data-stu-id="da58b-157">[All]</span></span></p></li>
<li><p><span data-ttu-id="da58b-158">VPN</span><span class="sxs-lookup"><span data-stu-id="da58b-158">VPN</span></span></p></li>
<li><p><span data-ttu-id="da58b-159">Não-VPN</span><span class="sxs-lookup"><span data-stu-id="da58b-159">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

