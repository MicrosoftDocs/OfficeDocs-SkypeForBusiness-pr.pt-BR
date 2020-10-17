---
title: 'Lync Server 2013: relatório de tendências de local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df3896704565a617ae4f50cfcc9afee29f5f098e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513768"
---
# <a name="location-trend-report-in-lync-server-2013"></a><span data-ttu-id="dab68-102">Relatório de tendências de local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dab68-102">Location Trend Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dab68-103">_**Última modificação do tópico:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="dab68-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="dab68-104">O Relatório de Tendências de Local fornece informações sobre as tendências de qualidade de chamada para locais de rede.</span><span class="sxs-lookup"><span data-stu-id="dab68-104">The Location Trend Report provides call quality trend information for network locations.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="dab68-105">Filtros</span><span class="sxs-lookup"><span data-stu-id="dab68-105">Filters</span></span>

<span data-ttu-id="dab68-p101">Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Tendências de Local permite filtrar os dados retornados por informações como tipo de acesso (ou seja, acesso interno x acesso externo) ou por conexão de rede com fio/sem fio. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="dab68-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Trend Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, or week.</span></span>

<span data-ttu-id="dab68-110">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Tendências de Local.</span><span class="sxs-lookup"><span data-stu-id="dab68-110">The following table lists the filters that you can use with the Location Trend Report.</span></span>

### <a name="location-trend-report-filters"></a><span data-ttu-id="dab68-111">Filtros do Relatório de Tendências de Local</span><span class="sxs-lookup"><span data-stu-id="dab68-111">Location Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dab68-112">Nome</span><span class="sxs-lookup"><span data-stu-id="dab68-112">Name</span></span></th>
<th><span data-ttu-id="dab68-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="dab68-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dab68-114"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="dab68-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="dab68-p102">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="dab68-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="dab68-117">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="dab68-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="dab68-p103">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="dab68-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dab68-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="dab68-120">7/7/2012</span></span></p>
<p><span data-ttu-id="dab68-121">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="dab68-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dab68-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="dab68-122">7/3/2012</span></span></p>
<p><span data-ttu-id="dab68-123">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="dab68-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dab68-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="dab68-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="dab68-p104">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="dab68-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="dab68-127">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="dab68-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="dab68-p105">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="dab68-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dab68-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="dab68-130">7/7/2012</span></span></p>
<p><span data-ttu-id="dab68-131">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="dab68-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dab68-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="dab68-132">7/3/2012</span></span></p>
<p><span data-ttu-id="dab68-133">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="dab68-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dab68-134"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="dab68-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="dab68-p106">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="dab68-p106">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dab68-137">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="dab68-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="dab68-138">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="dab68-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="dab68-139">Semanal (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="dab68-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="dab68-p107">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com a data de início 7/8/2012 e a data de término 28/9/2011, os dados serão exibidos para os dias de 7/8/2012 12:00 AM a 7/9/2012 12:00 AM (ou seja, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="dab68-p107">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 1/1/2011 and an end date of 2/28/2011, data is displayed for the days 8/1/2011 12:00 AM to 9/1/2011 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dab68-142"><strong>Tipo de acesso</strong></span><span class="sxs-lookup"><span data-stu-id="dab68-142"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="dab68-p108">Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="dab68-p108">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dab68-145">Todos os</span><span class="sxs-lookup"><span data-stu-id="dab68-145">[All]</span></span></p></li>
<li><p><span data-ttu-id="dab68-146">Interno</span><span class="sxs-lookup"><span data-stu-id="dab68-146">Internal</span></span></p></li>
<li><p><span data-ttu-id="dab68-147">Externo</span><span class="sxs-lookup"><span data-stu-id="dab68-147">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dab68-148"><strong>Tipo de rede</strong></span><span class="sxs-lookup"><span data-stu-id="dab68-148"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="dab68-p109">Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="dab68-p109">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dab68-151">Todos os</span><span class="sxs-lookup"><span data-stu-id="dab68-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="dab68-152">Com fio</span><span class="sxs-lookup"><span data-stu-id="dab68-152">Wired</span></span></p></li>
<li><p><span data-ttu-id="dab68-153">Conexão</span><span class="sxs-lookup"><span data-stu-id="dab68-153">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dab68-154"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="dab68-154"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="dab68-p110">Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="dab68-p110">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dab68-157">Todos os</span><span class="sxs-lookup"><span data-stu-id="dab68-157">[All]</span></span></p></li>
<li><p><span data-ttu-id="dab68-158">VPN</span><span class="sxs-lookup"><span data-stu-id="dab68-158">VPN</span></span></p></li>
<li><p><span data-ttu-id="dab68-159">Não VPN</span><span class="sxs-lookup"><span data-stu-id="dab68-159">Non-VPN</span></span></p></li>
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

