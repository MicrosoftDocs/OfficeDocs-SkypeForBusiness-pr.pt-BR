---
title: 'Lync Server 2013: relatório de comparação de qualidade de mídia'
description: 'Lync Server 2013: relatório de comparação de qualidade de mídia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2c4c5c948d167ce5210f9814c4e0625ffaa9152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548227"
---
# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="044ac-103">Relatório de comparação de qualidade de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="044ac-103">Media Quality Comparison Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="044ac-104">_**Última modificação do tópico:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="044ac-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="044ac-105">O Relatório de Comparação de Qualidade da Mídia permite você comparar os valores de qualidade da chamada para diferentes tipos de chamadas de áudio (por exemplo, chamadas realizadas através de uma rede sem fio contra chamadas realizadas em uma conexão com fio).</span><span class="sxs-lookup"><span data-stu-id="044ac-105">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="044ac-106">Acessando o Relatório de Comparação de Qualidade da Mídia</span><span class="sxs-lookup"><span data-stu-id="044ac-106">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="044ac-107">O Relatório de Comparação de Qualidade da Mídia é acessado na página inicial de Relatórios de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="044ac-107">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="044ac-108">Filtros</span><span class="sxs-lookup"><span data-stu-id="044ac-108">Filters</span></span>

<span data-ttu-id="044ac-p101">Os filtros oferecem uma forma de retornar um conjunto de dados mais detalhado ou exibir os dados retornados em formas diferentes. A tabela a seguir lista os filtros que você pode usar com o Relatório de Comparação de Qualidade da Mídia.</span><span class="sxs-lookup"><span data-stu-id="044ac-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="044ac-111">Filtros do Relatório de Comparação de Qualidade da Mídia</span><span class="sxs-lookup"><span data-stu-id="044ac-111">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="044ac-112">Nome</span><span class="sxs-lookup"><span data-stu-id="044ac-112">Name</span></span></th>
<th><span data-ttu-id="044ac-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="044ac-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="044ac-114"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="044ac-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="044ac-p102">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="044ac-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="044ac-117">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="044ac-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="044ac-p103">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="044ac-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="044ac-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="044ac-120">7/7/2012</span></span></p>
<p><span data-ttu-id="044ac-121">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="044ac-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="044ac-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="044ac-122">7/3/2012</span></span></p>
<p><span data-ttu-id="044ac-123">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="044ac-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="044ac-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="044ac-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="044ac-p104">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="044ac-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="044ac-127">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="044ac-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="044ac-p105">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="044ac-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="044ac-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="044ac-130">7/7/2012</span></span></p>
<p><span data-ttu-id="044ac-131">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="044ac-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="044ac-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="044ac-132">7/3/2012</span></span></p>
<p><span data-ttu-id="044ac-133">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="044ac-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="044ac-134"><strong>Chamadas</strong></span><span class="sxs-lookup"><span data-stu-id="044ac-134"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="044ac-p106">Tipo de chamada a ser usada como o item de comparação principal. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="044ac-p106">Type of call to be used as the main comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="044ac-137">Todos os</span><span class="sxs-lookup"><span data-stu-id="044ac-137">[All]</span></span></p></li>
<li><p><span data-ttu-id="044ac-138">Externo</span><span class="sxs-lookup"><span data-stu-id="044ac-138">External</span></span></p></li>
<li><p><span data-ttu-id="044ac-139">Interno</span><span class="sxs-lookup"><span data-stu-id="044ac-139">Internal</span></span></p></li>
<li><p><span data-ttu-id="044ac-140">VPN</span><span class="sxs-lookup"><span data-stu-id="044ac-140">VPN</span></span></p></li>
<li><p><span data-ttu-id="044ac-141">Não VPN</span><span class="sxs-lookup"><span data-stu-id="044ac-141">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="044ac-142">Com fio</span><span class="sxs-lookup"><span data-stu-id="044ac-142">Wired</span></span></p></li>
<li><p><span data-ttu-id="044ac-143">Conexão</span><span class="sxs-lookup"><span data-stu-id="044ac-143">Wireless</span></span></p></li>
<li><p><span data-ttu-id="044ac-144">Externa e com fio</span><span class="sxs-lookup"><span data-stu-id="044ac-144">External and wired</span></span></p></li>
<li><p><span data-ttu-id="044ac-145">Externa e sem fio</span><span class="sxs-lookup"><span data-stu-id="044ac-145">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="044ac-146">Externa e VPN</span><span class="sxs-lookup"><span data-stu-id="044ac-146">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="044ac-147">Externa e não-VPN</span><span class="sxs-lookup"><span data-stu-id="044ac-147">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="044ac-148">Interna e com fio</span><span class="sxs-lookup"><span data-stu-id="044ac-148">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="044ac-149">Interna e sem fio</span><span class="sxs-lookup"><span data-stu-id="044ac-149">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="044ac-150"><strong>Comparar com chamadas</strong></span><span class="sxs-lookup"><span data-stu-id="044ac-150"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="044ac-p107">Tipo de chamada a ser usada como o item de comparação secundária. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="044ac-p107">Type of call to be used as the secondary comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="044ac-153">Todos os</span><span class="sxs-lookup"><span data-stu-id="044ac-153">[All]</span></span></p></li>
<li><p><span data-ttu-id="044ac-154">Externo</span><span class="sxs-lookup"><span data-stu-id="044ac-154">External</span></span></p></li>
<li><p><span data-ttu-id="044ac-155">Interno</span><span class="sxs-lookup"><span data-stu-id="044ac-155">Internal</span></span></p></li>
<li><p><span data-ttu-id="044ac-156">VPN</span><span class="sxs-lookup"><span data-stu-id="044ac-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="044ac-157">Não VPN</span><span class="sxs-lookup"><span data-stu-id="044ac-157">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="044ac-158">Com fio</span><span class="sxs-lookup"><span data-stu-id="044ac-158">Wired</span></span></p></li>
<li><p><span data-ttu-id="044ac-159">Conexão</span><span class="sxs-lookup"><span data-stu-id="044ac-159">Wireless</span></span></p></li>
<li><p><span data-ttu-id="044ac-160">Externa e com fio</span><span class="sxs-lookup"><span data-stu-id="044ac-160">External and wired</span></span></p></li>
<li><p><span data-ttu-id="044ac-161">Externa e sem fio</span><span class="sxs-lookup"><span data-stu-id="044ac-161">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="044ac-162">Externa e VPN</span><span class="sxs-lookup"><span data-stu-id="044ac-162">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="044ac-163">Externa e não-VPN</span><span class="sxs-lookup"><span data-stu-id="044ac-163">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="044ac-164">Interna e com fio</span><span class="sxs-lookup"><span data-stu-id="044ac-164">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="044ac-165">Interna e sem fio</span><span class="sxs-lookup"><span data-stu-id="044ac-165">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="044ac-166"><strong>Intervalo</strong></span><span class="sxs-lookup"><span data-stu-id="044ac-166"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="044ac-p108">Intervalo de tempo. Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="044ac-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="044ac-169">Por hora (é possível exibir no máximo 25 horas)</span><span class="sxs-lookup"><span data-stu-id="044ac-169">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="044ac-170">Diariamente (é possível exibir no máximo 31 dias)</span><span class="sxs-lookup"><span data-stu-id="044ac-170">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="044ac-171">Semanalmente (é possível exibir no máximo 12 semanas)</span><span class="sxs-lookup"><span data-stu-id="044ac-171">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="044ac-p109">Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com a data de início 7/7/12 e uma data de término de 28/2/12, os dados serão exibidos para os dias 7/8/2 00:00 horas até 7/9/12 00:00 horas (ou seja, um total de 31 dias de dados).</span><span class="sxs-lookup"><span data-stu-id="044ac-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="044ac-174">Métrica</span><span class="sxs-lookup"><span data-stu-id="044ac-174">Metrics</span></span>

<span data-ttu-id="044ac-175">A tabela a seguir lista as informações fornecidas no Relatório de Comparação de Qualidade da Mídia.</span><span class="sxs-lookup"><span data-stu-id="044ac-175">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="044ac-176">Métricas do Relatório de Comparação de Qualidade da Mídia</span><span class="sxs-lookup"><span data-stu-id="044ac-176">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="044ac-177">Nome</span><span class="sxs-lookup"><span data-stu-id="044ac-177">Name</span></span></th>
<th><span data-ttu-id="044ac-178">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="044ac-178">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="044ac-179">Descrição</span><span class="sxs-lookup"><span data-stu-id="044ac-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="044ac-180"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="044ac-180"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="044ac-181">Não</span><span class="sxs-lookup"><span data-stu-id="044ac-181">No</span></span></p></td>
<td><p><span data-ttu-id="044ac-182">Número total de chamadas.</span><span class="sxs-lookup"><span data-stu-id="044ac-182">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="044ac-183"><strong>Degradação (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="044ac-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="044ac-184">Não</span><span class="sxs-lookup"><span data-stu-id="044ac-184">No</span></span></p></td>
<td><p><span data-ttu-id="044ac-185">Valor médio de uma degradação de MOS (Pontuação média de opinião) em uma chamada.</span><span class="sxs-lookup"><span data-stu-id="044ac-185">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="044ac-186">Os valores de degradação podem variar de um baixo de 0,0 para um alto de 5,0; um valor de 0,5 ou menos representa degradação aceitável.</span><span class="sxs-lookup"><span data-stu-id="044ac-186">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="044ac-187">Historicamente, médias pontuações de opinião foram calculadas tendo os usuários a taxa de qualidade de uma chamada em uma escala de 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="044ac-187">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="044ac-188">O Lync Server usa um conjunto de algoritmos para prever como os usuários classificaram uma chamada.</span><span class="sxs-lookup"><span data-stu-id="044ac-188">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="044ac-p111">Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="044ac-p111">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="044ac-191"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="044ac-191"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="044ac-192">Não</span><span class="sxs-lookup"><span data-stu-id="044ac-192">No</span></span></p></td>
<td><p><span data-ttu-id="044ac-p112">O número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="044ac-p112">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="044ac-195"><strong>Viagem de ida e volta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="044ac-195"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="044ac-196">Não</span><span class="sxs-lookup"><span data-stu-id="044ac-196">No</span></span></p></td>
<td><p><span data-ttu-id="044ac-p113">Quantidade média de (em milissegundos) exigida para que um pacote de Protocolo de Transporte em Tempo Real viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="044ac-p113">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="044ac-p114">Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="044ac-p114">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="044ac-201"><strong>Perda de pacote </strong></span><span class="sxs-lookup"><span data-stu-id="044ac-201"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="044ac-202">Não</span><span class="sxs-lookup"><span data-stu-id="044ac-202">No</span></span></p></td>
<td><p><span data-ttu-id="044ac-p115">Taxa média de perda de pacotes de Protocolo de Transporte em Tempo Real (RTP). (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="044ac-p115">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="044ac-206"><strong>Tremulação (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="044ac-206"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="044ac-207">Não</span><span class="sxs-lookup"><span data-stu-id="044ac-207">No</span></span></p></td>
<td><p><span data-ttu-id="044ac-208">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="044ac-208">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="044ac-209">(Tremulação é uma medida do &quot; tremula &quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="044ac-209">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="044ac-210"><strong>Taxa de correção oculta</strong></span><span class="sxs-lookup"><span data-stu-id="044ac-210"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="044ac-211">Não</span><span class="sxs-lookup"><span data-stu-id="044ac-211">No</span></span></p></td>
<td><p><span data-ttu-id="044ac-p117">Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="044ac-p117">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="044ac-214"><strong>Taxa de correção estendida</strong></span><span class="sxs-lookup"><span data-stu-id="044ac-214"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="044ac-215">Não</span><span class="sxs-lookup"><span data-stu-id="044ac-215">No</span></span></p></td>
<td><p><span data-ttu-id="044ac-p118">Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="044ac-p118">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="044ac-218"><strong>Taxa de correção compactada</strong></span><span class="sxs-lookup"><span data-stu-id="044ac-218"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="044ac-219">Não</span><span class="sxs-lookup"><span data-stu-id="044ac-219">No</span></span></p></td>
<td><p><span data-ttu-id="044ac-p119">Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="044ac-p119">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

