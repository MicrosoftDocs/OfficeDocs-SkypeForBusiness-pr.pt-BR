---
title: 'Lync Server 2013: relatório de distribuição de métricas de qualidade de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d814fd001f3510a7ae83e63746bdc1265932e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="86f46-102">O relatório de distribuição de métricas de qualidade de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86f46-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86f46-103">_**Tópico da última modificação:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="86f46-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="86f46-p101">O Relatório de Distribuição da Métrica de Qualidade de Mídia permite ver um gráfico que mostra os valores de distribuição para a métrica Qualidade da Experiência, como tremulação ou perda de pacotes. Por exemplo, suponha que seus usuários fazem um total de 10 ligações telefônicas; essas 10 chamadas relatam os seguintes tempos de ida e volta:</span><span class="sxs-lookup"><span data-stu-id="86f46-p101">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss. For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86f46-106">Número da chamada</span><span class="sxs-lookup"><span data-stu-id="86f46-106">Call Number</span></span></th>
<th><span data-ttu-id="86f46-107">Tempo de resposta (milissegundos)</span><span class="sxs-lookup"><span data-stu-id="86f46-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86f46-108">1</span><span class="sxs-lookup"><span data-stu-id="86f46-108">1</span></span></p></td>
<td><p><span data-ttu-id="86f46-109">50</span><span class="sxs-lookup"><span data-stu-id="86f46-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86f46-110">2</span><span class="sxs-lookup"><span data-stu-id="86f46-110">2</span></span></p></td>
<td><p><span data-ttu-id="86f46-111">50</span><span class="sxs-lookup"><span data-stu-id="86f46-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86f46-112">3</span><span class="sxs-lookup"><span data-stu-id="86f46-112">3</span></span></p></td>
<td><p><span data-ttu-id="86f46-113">50</span><span class="sxs-lookup"><span data-stu-id="86f46-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86f46-114">4</span><span class="sxs-lookup"><span data-stu-id="86f46-114">4</span></span></p></td>
<td><p><span data-ttu-id="86f46-115">50</span><span class="sxs-lookup"><span data-stu-id="86f46-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86f46-116">5</span><span class="sxs-lookup"><span data-stu-id="86f46-116">5</span></span></p></td>
<td><p><span data-ttu-id="86f46-117">50</span><span class="sxs-lookup"><span data-stu-id="86f46-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86f46-118">6</span><span class="sxs-lookup"><span data-stu-id="86f46-118">6</span></span></p></td>
<td><p><span data-ttu-id="86f46-119">50</span><span class="sxs-lookup"><span data-stu-id="86f46-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86f46-120">7</span><span class="sxs-lookup"><span data-stu-id="86f46-120">7</span></span></p></td>
<td><p><span data-ttu-id="86f46-121">50</span><span class="sxs-lookup"><span data-stu-id="86f46-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86f46-122">08</span><span class="sxs-lookup"><span data-stu-id="86f46-122">8</span></span></p></td>
<td><p><span data-ttu-id="86f46-123">4550</span><span class="sxs-lookup"><span data-stu-id="86f46-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86f46-124">222</span><span class="sxs-lookup"><span data-stu-id="86f46-124">9</span></span></p></td>
<td><p><span data-ttu-id="86f46-125">50</span><span class="sxs-lookup"><span data-stu-id="86f46-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86f46-126">254</span><span class="sxs-lookup"><span data-stu-id="86f46-126">10</span></span></p></td>
<td><p><span data-ttu-id="86f46-127">50</span><span class="sxs-lookup"><span data-stu-id="86f46-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="86f46-128">A média dessas horas de ida e volta é de 500 milissegundos (5000 dividida por 10).</span><span class="sxs-lookup"><span data-stu-id="86f46-128">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="86f46-129">500 milissegundos é um tempo de ida e volta extremamente grande; Como resultado, você pode acreditar que tem um problema sério com o congestionamento da rede.</span><span class="sxs-lookup"><span data-stu-id="86f46-129">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="86f46-130">(Geralmente, períodos de tempo de resposta longos são o resultado de redes sobrecarregadas).</span><span class="sxs-lookup"><span data-stu-id="86f46-130">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="86f46-131">Na realidade, claro, 90% das suas chamadas têm excelentes tempos de ida e volta; você teve uma única chamada ruim que distorceu os resultados gerais.</span><span class="sxs-lookup"><span data-stu-id="86f46-131">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="86f46-132">Se você só olhar o tempo médio de ida e volta, você pode ir para uma conclusão muito errada.</span><span class="sxs-lookup"><span data-stu-id="86f46-132">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="86f46-p104">O Relatório de Distribuição da Métrica de Qualidade de Mídia ajuda a evitar conclusões incorretas mostrando uma distribuição gráfica de uma métrica especificada (como o tempo de ida e volta). Estes gráficos ajudam a deixar claro que você teve nove chamadas muito boas e uma muito ruim. Você ainda pode desejar investigar melhor essa chamada. No entanto, o fato de 9 entre 10 chamadas terem sido muito boas sugere que não há motivo para fazer qualquer mudança radical em sua rede, pelo menos não neste momento.</span><span class="sxs-lookup"><span data-stu-id="86f46-p104">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time). These graphs can help make it clear that you had nine very good calls and one very bad call. Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="86f46-136">Filtros</span><span class="sxs-lookup"><span data-stu-id="86f46-136">Filters</span></span>

<span data-ttu-id="86f46-p105">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. A tabela a seguir lista os filtros que você pode usar com o Relatório de Distribuição da Métrica de Qualidade de Mídia.</span><span class="sxs-lookup"><span data-stu-id="86f46-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="86f46-139">Filtros do Relatório de Distribuição da Métrica de Qualidade de Mídia</span><span class="sxs-lookup"><span data-stu-id="86f46-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86f46-140">Nome</span><span class="sxs-lookup"><span data-stu-id="86f46-140">Name</span></span></th>
<th><span data-ttu-id="86f46-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="86f46-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86f46-142"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="86f46-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="86f46-p106">Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</span><span class="sxs-lookup"><span data-stu-id="86f46-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="86f46-145">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="86f46-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="86f46-p107">Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="86f46-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="86f46-148">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="86f46-148">7/7/2012</span></span></p>
<p><span data-ttu-id="86f46-149">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="86f46-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="86f46-150">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="86f46-150">7/3/2012</span></span></p>
<p><span data-ttu-id="86f46-151">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="86f46-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86f46-152"><strong>Até</strong></span><span class="sxs-lookup"><span data-stu-id="86f46-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="86f46-p108">Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</span><span class="sxs-lookup"><span data-stu-id="86f46-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="86f46-155">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="86f46-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="86f46-p109">Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</span><span class="sxs-lookup"><span data-stu-id="86f46-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="86f46-158">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="86f46-158">7/7/2012</span></span></p>
<p><span data-ttu-id="86f46-159">Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="86f46-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="86f46-160">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="86f46-160">7/3/2012</span></span></p>
<p><span data-ttu-id="86f46-161">As semanas sempre vão de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="86f46-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86f46-162"><strong>Mínimo no eixo x</strong></span><span class="sxs-lookup"><span data-stu-id="86f46-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="86f46-163">Menor valor para ser exibido no eixo X do gráfico.</span><span class="sxs-lookup"><span data-stu-id="86f46-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86f46-164"><strong>Máximo no eixo x</strong></span><span class="sxs-lookup"><span data-stu-id="86f46-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="86f46-165">Maior valor para ser exibido no eixo X do gráfico.</span><span class="sxs-lookup"><span data-stu-id="86f46-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86f46-166"><strong>Tipo de acesso</strong></span><span class="sxs-lookup"><span data-stu-id="86f46-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="86f46-p110">Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="86f46-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86f46-169">[Todos]</span><span class="sxs-lookup"><span data-stu-id="86f46-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="86f46-170">Interno</span><span class="sxs-lookup"><span data-stu-id="86f46-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="86f46-171">Externo</span><span class="sxs-lookup"><span data-stu-id="86f46-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86f46-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="86f46-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="86f46-p111">Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="86f46-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86f46-175">[Todos]</span><span class="sxs-lookup"><span data-stu-id="86f46-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="86f46-176">VPN</span><span class="sxs-lookup"><span data-stu-id="86f46-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="86f46-177">Não VPN</span><span class="sxs-lookup"><span data-stu-id="86f46-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86f46-178"><strong>Tipo de rede</strong></span><span class="sxs-lookup"><span data-stu-id="86f46-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="86f46-p112">Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="86f46-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="86f46-181">[Todos]</span><span class="sxs-lookup"><span data-stu-id="86f46-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="86f46-182">Com fio</span><span class="sxs-lookup"><span data-stu-id="86f46-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="86f46-183">Sem fio</span><span class="sxs-lookup"><span data-stu-id="86f46-183">Wireless</span></span></p></li>
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

