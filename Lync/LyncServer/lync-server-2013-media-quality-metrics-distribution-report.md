---
title: 'Lync Server 2013: relatório de distribuição de métricas de qualidade de mídia'
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
ms.openlocfilehash: c3823f65d5bc565f01b55b08259a4482c97bbd43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500648"
---
# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="706a4-102">O relatório de distribuição de métricas de qualidade de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="706a4-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="706a4-103">_**Última modificação do tópico:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="706a4-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="706a4-p101">O Relatório de Distribuição da Métrica de Qualidade de Mídia permite ver um gráfico que mostra os valores de distribuição para a métrica Qualidade da Experiência como jitter ou perda do pacote. Por exemplo, suponha que seus usuários fazem um total de 10 ligações telefônicas; estas 10 chamadas relatam os seguintes tempos de ida e volta:</span><span class="sxs-lookup"><span data-stu-id="706a4-p101">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss. For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="706a4-106">Número da chamada</span><span class="sxs-lookup"><span data-stu-id="706a4-106">Call Number</span></span></th>
<th><span data-ttu-id="706a4-107">Tempo de ida e volta (milissegundos)</span><span class="sxs-lookup"><span data-stu-id="706a4-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="706a4-108">1</span><span class="sxs-lookup"><span data-stu-id="706a4-108">1</span></span></p></td>
<td><p><span data-ttu-id="706a4-109">50</span><span class="sxs-lookup"><span data-stu-id="706a4-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706a4-110">duas</span><span class="sxs-lookup"><span data-stu-id="706a4-110">2</span></span></p></td>
<td><p><span data-ttu-id="706a4-111">50</span><span class="sxs-lookup"><span data-stu-id="706a4-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706a4-112">3D</span><span class="sxs-lookup"><span data-stu-id="706a4-112">3</span></span></p></td>
<td><p><span data-ttu-id="706a4-113">50</span><span class="sxs-lookup"><span data-stu-id="706a4-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706a4-114">4 </span><span class="sxs-lookup"><span data-stu-id="706a4-114">4</span></span></p></td>
<td><p><span data-ttu-id="706a4-115">50</span><span class="sxs-lookup"><span data-stu-id="706a4-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706a4-116">5 </span><span class="sxs-lookup"><span data-stu-id="706a4-116">5</span></span></p></td>
<td><p><span data-ttu-id="706a4-117">50</span><span class="sxs-lookup"><span data-stu-id="706a4-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706a4-118">6 </span><span class="sxs-lookup"><span data-stu-id="706a4-118">6</span></span></p></td>
<td><p><span data-ttu-id="706a4-119">50</span><span class="sxs-lookup"><span data-stu-id="706a4-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706a4-120">7 </span><span class="sxs-lookup"><span data-stu-id="706a4-120">7</span></span></p></td>
<td><p><span data-ttu-id="706a4-121">50</span><span class="sxs-lookup"><span data-stu-id="706a4-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706a4-122">8 </span><span class="sxs-lookup"><span data-stu-id="706a4-122">8</span></span></p></td>
<td><p><span data-ttu-id="706a4-123">4550</span><span class="sxs-lookup"><span data-stu-id="706a4-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706a4-124">9 </span><span class="sxs-lookup"><span data-stu-id="706a4-124">9</span></span></p></td>
<td><p><span data-ttu-id="706a4-125">50</span><span class="sxs-lookup"><span data-stu-id="706a4-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706a4-126">10 </span><span class="sxs-lookup"><span data-stu-id="706a4-126">10</span></span></p></td>
<td><p><span data-ttu-id="706a4-127">50</span><span class="sxs-lookup"><span data-stu-id="706a4-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="706a4-p102">A média para estes tempos de ida e volta é de 500 milissegundos (5000 dividido por 10). Cinco mil milissegundos é um tempo de ida e volta extremamente grande; como resultado, você pode acreditar ter um sério problema com a congestão de rede. (Tempo de ida e volta longo é geralmente resultado de redes sobrecarregadas.)</span><span class="sxs-lookup"><span data-stu-id="706a4-p102">The average for those roundtrip times is 500 milliseconds (5000 divided by 10). Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion. (Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="706a4-p103">Na realidade, claro,, 90% das suas chamadas possuem excelentes tempos de ida e volta; você mal tinha uma chamada em seus resultados gerais. Se procurar pelo tempo de ida e volta médio, pode terminar em uma conclusão errada.</span><span class="sxs-lookup"><span data-stu-id="706a4-p103">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results. If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="706a4-p104">O Relatório de Distribuição da Métrica de Qualidade de Mídia ajuda a evitar conclusões incorretas mostrando uma distribuição gráfica de uma métrica especificada (como o tempo de ida e volta). Estes gráficos ajudam a tornar claro que você possui nova chamadas muito boas e uma muito ruim. Você ainda pode desejar investigar mais que uma chamada. No entanto, o fato que 9 de 10 chamadas foram muito boas sugere que não há motivo para fazer qualquer mudança radical em sua rede, pelo menos não neste momento.</span><span class="sxs-lookup"><span data-stu-id="706a4-p104">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time). These graphs can help make it clear that you had nine very good calls and one very bad call. Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="706a4-136">Filtros</span><span class="sxs-lookup"><span data-stu-id="706a4-136">Filters</span></span>

<span data-ttu-id="706a4-p105">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. A tabela a seguir lista os filtros que você pode usar com o Relatório de Distribuição da Métrica de Qualidade de Mídia.</span><span class="sxs-lookup"><span data-stu-id="706a4-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="706a4-139">Filtros do Relatório de Distribuição da Métrica de Qualidade de Mídia</span><span class="sxs-lookup"><span data-stu-id="706a4-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="706a4-140">Nome</span><span class="sxs-lookup"><span data-stu-id="706a4-140">Name</span></span></th>
<th><span data-ttu-id="706a4-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="706a4-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="706a4-142"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="706a4-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="706a4-p106">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="706a4-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="706a4-145">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="706a4-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="706a4-p107">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="706a4-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="706a4-148">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="706a4-148">7/7/2012</span></span></p>
<p><span data-ttu-id="706a4-149">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="706a4-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="706a4-150">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="706a4-150">7/3/2012</span></span></p>
<p><span data-ttu-id="706a4-151">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="706a4-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706a4-152"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="706a4-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="706a4-p108">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="706a4-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="706a4-155">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="706a4-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="706a4-p109">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="706a4-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="706a4-158">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="706a4-158">7/7/2012</span></span></p>
<p><span data-ttu-id="706a4-159">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="706a4-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="706a4-160">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="706a4-160">7/3/2012</span></span></p>
<p><span data-ttu-id="706a4-161">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="706a4-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706a4-162"><strong>Mínimo no eixo x</strong></span><span class="sxs-lookup"><span data-stu-id="706a4-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="706a4-163">Menor valor para ser exibido no eixo X do gráfico.</span><span class="sxs-lookup"><span data-stu-id="706a4-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706a4-164"><strong>Máximo no eixo x</strong></span><span class="sxs-lookup"><span data-stu-id="706a4-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="706a4-165">Maior valor para ser exibido no eixo X do gráfico.</span><span class="sxs-lookup"><span data-stu-id="706a4-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706a4-166"><strong>Tipo de acesso</strong></span><span class="sxs-lookup"><span data-stu-id="706a4-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="706a4-p110">Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="706a4-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="706a4-169">Todos os</span><span class="sxs-lookup"><span data-stu-id="706a4-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="706a4-170">Interno</span><span class="sxs-lookup"><span data-stu-id="706a4-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="706a4-171">Externo</span><span class="sxs-lookup"><span data-stu-id="706a4-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="706a4-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="706a4-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="706a4-p111">Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="706a4-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="706a4-175">Todos os</span><span class="sxs-lookup"><span data-stu-id="706a4-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="706a4-176">VPN</span><span class="sxs-lookup"><span data-stu-id="706a4-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="706a4-177">Não VPN</span><span class="sxs-lookup"><span data-stu-id="706a4-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="706a4-178"><strong>Tipo de rede</strong></span><span class="sxs-lookup"><span data-stu-id="706a4-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="706a4-p112">Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="706a4-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="706a4-181">Todos os</span><span class="sxs-lookup"><span data-stu-id="706a4-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="706a4-182">Com fio</span><span class="sxs-lookup"><span data-stu-id="706a4-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="706a4-183">Conexão</span><span class="sxs-lookup"><span data-stu-id="706a4-183">Wireless</span></span></p></li>
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

