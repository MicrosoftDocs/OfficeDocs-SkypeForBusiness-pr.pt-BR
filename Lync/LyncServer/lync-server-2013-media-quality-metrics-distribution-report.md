---
title: 'Lync Server 2013: relatório de distribuição de métricas de qualidade de mídia'
description: 'Lync Server 2013: relatório de distribuição de métricas de qualidade de mídia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def56580477dadf989268e1fc24fcec7776c00d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548147"
---
# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="69f5d-103">O relatório de distribuição de métricas de qualidade de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69f5d-103">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69f5d-104">_**Última modificação do tópico:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="69f5d-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="69f5d-p101">O Relatório de Distribuição da Métrica de Qualidade de Mídia permite ver um gráfico que mostra os valores de distribuição para a métrica Qualidade da Experiência como jitter ou perda do pacote. Por exemplo, suponha que seus usuários fazem um total de 10 ligações telefônicas; estas 10 chamadas relatam os seguintes tempos de ida e volta:</span><span class="sxs-lookup"><span data-stu-id="69f5d-p101">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss. For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69f5d-107">Número da chamada</span><span class="sxs-lookup"><span data-stu-id="69f5d-107">Call Number</span></span></th>
<th><span data-ttu-id="69f5d-108">Tempo de ida e volta (milissegundos)</span><span class="sxs-lookup"><span data-stu-id="69f5d-108">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69f5d-109">1</span><span class="sxs-lookup"><span data-stu-id="69f5d-109">1</span></span></p></td>
<td><p><span data-ttu-id="69f5d-110">50</span><span class="sxs-lookup"><span data-stu-id="69f5d-110">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69f5d-111">duas</span><span class="sxs-lookup"><span data-stu-id="69f5d-111">2</span></span></p></td>
<td><p><span data-ttu-id="69f5d-112">50</span><span class="sxs-lookup"><span data-stu-id="69f5d-112">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69f5d-113">3D</span><span class="sxs-lookup"><span data-stu-id="69f5d-113">3</span></span></p></td>
<td><p><span data-ttu-id="69f5d-114">50</span><span class="sxs-lookup"><span data-stu-id="69f5d-114">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69f5d-115">4 </span><span class="sxs-lookup"><span data-stu-id="69f5d-115">4</span></span></p></td>
<td><p><span data-ttu-id="69f5d-116">50</span><span class="sxs-lookup"><span data-stu-id="69f5d-116">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69f5d-117">5 </span><span class="sxs-lookup"><span data-stu-id="69f5d-117">5</span></span></p></td>
<td><p><span data-ttu-id="69f5d-118">50</span><span class="sxs-lookup"><span data-stu-id="69f5d-118">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69f5d-119">6 </span><span class="sxs-lookup"><span data-stu-id="69f5d-119">6</span></span></p></td>
<td><p><span data-ttu-id="69f5d-120">50</span><span class="sxs-lookup"><span data-stu-id="69f5d-120">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69f5d-121">7 </span><span class="sxs-lookup"><span data-stu-id="69f5d-121">7</span></span></p></td>
<td><p><span data-ttu-id="69f5d-122">50</span><span class="sxs-lookup"><span data-stu-id="69f5d-122">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69f5d-123">8 </span><span class="sxs-lookup"><span data-stu-id="69f5d-123">8</span></span></p></td>
<td><p><span data-ttu-id="69f5d-124">4550</span><span class="sxs-lookup"><span data-stu-id="69f5d-124">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69f5d-125">9 </span><span class="sxs-lookup"><span data-stu-id="69f5d-125">9</span></span></p></td>
<td><p><span data-ttu-id="69f5d-126">50</span><span class="sxs-lookup"><span data-stu-id="69f5d-126">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69f5d-127">10 </span><span class="sxs-lookup"><span data-stu-id="69f5d-127">10</span></span></p></td>
<td><p><span data-ttu-id="69f5d-128">50</span><span class="sxs-lookup"><span data-stu-id="69f5d-128">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="69f5d-p102">A média para estes tempos de ida e volta é de 500 milissegundos (5000 dividido por 10). Cinco mil milissegundos é um tempo de ida e volta extremamente grande; como resultado, você pode acreditar ter um sério problema com a congestão de rede. (Tempo de ida e volta longo é geralmente resultado de redes sobrecarregadas.)</span><span class="sxs-lookup"><span data-stu-id="69f5d-p102">The average for those roundtrip times is 500 milliseconds (5000 divided by 10). Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion. (Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="69f5d-p103">Na realidade, claro,, 90% das suas chamadas possuem excelentes tempos de ida e volta; você mal tinha uma chamada em seus resultados gerais. Se procurar pelo tempo de ida e volta médio, pode terminar em uma conclusão errada.</span><span class="sxs-lookup"><span data-stu-id="69f5d-p103">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results. If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="69f5d-p104">O Relatório de Distribuição da Métrica de Qualidade de Mídia ajuda a evitar conclusões incorretas mostrando uma distribuição gráfica de uma métrica especificada (como o tempo de ida e volta). Estes gráficos ajudam a tornar claro que você possui nova chamadas muito boas e uma muito ruim. Você ainda pode desejar investigar mais que uma chamada. No entanto, o fato que 9 de 10 chamadas foram muito boas sugere que não há motivo para fazer qualquer mudança radical em sua rede, pelo menos não neste momento.</span><span class="sxs-lookup"><span data-stu-id="69f5d-p104">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time). These graphs can help make it clear that you had nine very good calls and one very bad call. Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="69f5d-137">Filtros</span><span class="sxs-lookup"><span data-stu-id="69f5d-137">Filters</span></span>

<span data-ttu-id="69f5d-p105">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. A tabela a seguir lista os filtros que você pode usar com o Relatório de Distribuição da Métrica de Qualidade de Mídia.</span><span class="sxs-lookup"><span data-stu-id="69f5d-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="69f5d-140">Filtros do Relatório de Distribuição da Métrica de Qualidade de Mídia</span><span class="sxs-lookup"><span data-stu-id="69f5d-140">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69f5d-141">Nome</span><span class="sxs-lookup"><span data-stu-id="69f5d-141">Name</span></span></th>
<th><span data-ttu-id="69f5d-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="69f5d-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69f5d-143"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="69f5d-143"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="69f5d-p106">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="69f5d-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="69f5d-146">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="69f5d-146">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="69f5d-p107">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="69f5d-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="69f5d-149">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="69f5d-149">7/7/2012</span></span></p>
<p><span data-ttu-id="69f5d-150">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="69f5d-150">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="69f5d-151">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="69f5d-151">7/3/2012</span></span></p>
<p><span data-ttu-id="69f5d-152">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="69f5d-152">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69f5d-153"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="69f5d-153"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="69f5d-p108">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="69f5d-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="69f5d-156">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="69f5d-156">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="69f5d-p109">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="69f5d-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="69f5d-159">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="69f5d-159">7/7/2012</span></span></p>
<p><span data-ttu-id="69f5d-160">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="69f5d-160">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="69f5d-161">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="69f5d-161">7/3/2012</span></span></p>
<p><span data-ttu-id="69f5d-162">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="69f5d-162">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69f5d-163"><strong>Mínimo no eixo x</strong></span><span class="sxs-lookup"><span data-stu-id="69f5d-163"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="69f5d-164">Menor valor para ser exibido no eixo X do gráfico.</span><span class="sxs-lookup"><span data-stu-id="69f5d-164">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69f5d-165"><strong>Máximo no eixo x</strong></span><span class="sxs-lookup"><span data-stu-id="69f5d-165"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="69f5d-166">Maior valor para ser exibido no eixo X do gráfico.</span><span class="sxs-lookup"><span data-stu-id="69f5d-166">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69f5d-167"><strong>Tipo de acesso</strong></span><span class="sxs-lookup"><span data-stu-id="69f5d-167"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="69f5d-p110">Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="69f5d-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="69f5d-170">Todos os</span><span class="sxs-lookup"><span data-stu-id="69f5d-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="69f5d-171">Interno</span><span class="sxs-lookup"><span data-stu-id="69f5d-171">Internal</span></span></p></li>
<li><p><span data-ttu-id="69f5d-172">Externo</span><span class="sxs-lookup"><span data-stu-id="69f5d-172">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69f5d-173"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="69f5d-173"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="69f5d-p111">Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="69f5d-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="69f5d-176">Todos os</span><span class="sxs-lookup"><span data-stu-id="69f5d-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="69f5d-177">VPN</span><span class="sxs-lookup"><span data-stu-id="69f5d-177">VPN</span></span></p></li>
<li><p><span data-ttu-id="69f5d-178">Não VPN</span><span class="sxs-lookup"><span data-stu-id="69f5d-178">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69f5d-179"><strong>Tipo de rede</strong></span><span class="sxs-lookup"><span data-stu-id="69f5d-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="69f5d-p112">Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="69f5d-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="69f5d-182">Todos os</span><span class="sxs-lookup"><span data-stu-id="69f5d-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="69f5d-183">Com fio</span><span class="sxs-lookup"><span data-stu-id="69f5d-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="69f5d-184">Conexão</span><span class="sxs-lookup"><span data-stu-id="69f5d-184">Wireless</span></span></p></li>
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

