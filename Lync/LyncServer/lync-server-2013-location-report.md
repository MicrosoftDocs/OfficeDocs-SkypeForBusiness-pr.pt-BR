---
title: 'Lync Server 2013: relatório de localização'
description: 'Lync Server 2013: relatório de localização.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b819bcffeee0795cd39d3dde3e38fbd9e4a1b7c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569467"
---
# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="9fd54-103">Relatório de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fd54-103">Location Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fd54-104">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9fd54-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9fd54-p101">O Relatório de Localização oferece informações sobre as métricas de qualidade de chamada agrupadas pelo local de rede (isto é, pela subrede). Se seus usuários enfrentarem problemas com suas chamadas, este relatório pode ajudar você a determinar se estes problemas são amplos ou estão confinados a um determinado segmento da rede.</span><span class="sxs-lookup"><span data-stu-id="9fd54-p101">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet). If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="9fd54-107">Acessando o Relatório de Localização</span><span class="sxs-lookup"><span data-stu-id="9fd54-107">Accessing the Location Report</span></span>

<span data-ttu-id="9fd54-p102">O Relatório de Localização é acessado na página inicial de Relatórios de Monitoramento. É possível detalhar o Relatório de Lista de Chamadas clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="9fd54-p102">The Location Report is accessed from the Monitoring Reports home page. You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="9fd54-110">Volume da chamada</span><span class="sxs-lookup"><span data-stu-id="9fd54-110">Call volume</span></span>

  - <span data-ttu-id="9fd54-111">Porcentagem de chamada inválida</span><span class="sxs-lookup"><span data-stu-id="9fd54-111">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="9fd54-112">Filtros</span><span class="sxs-lookup"><span data-stu-id="9fd54-112">Filters</span></span>

<span data-ttu-id="9fd54-p103">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Locais permite que você filtre coisas como o local onde a chamada foi originada ou se a chamada ocorreu em uma conexão com ou sem fio. Também é possível escolher como os dados devem ser agrupados. Nesse caso, as chamadas são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="9fd54-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="9fd54-117">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Locais.</span><span class="sxs-lookup"><span data-stu-id="9fd54-117">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="9fd54-118">Filtros do Relatório de Locais</span><span class="sxs-lookup"><span data-stu-id="9fd54-118">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fd54-119">Nome</span><span class="sxs-lookup"><span data-stu-id="9fd54-119">Name</span></span></th>
<th><span data-ttu-id="9fd54-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="9fd54-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fd54-121"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-121"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-p104">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="9fd54-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="9fd54-124">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="9fd54-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9fd54-p105">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="9fd54-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9fd54-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9fd54-127">7/7/2012</span></span></p>
<p><span data-ttu-id="9fd54-128">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="9fd54-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9fd54-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9fd54-129">7/3/2012</span></span></p>
<p><span data-ttu-id="9fd54-130">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="9fd54-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fd54-131"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-131"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-p106">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="9fd54-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="9fd54-134">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="9fd54-134">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="9fd54-p107">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="9fd54-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="9fd54-137">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="9fd54-137">7/7/2012</span></span></p>
<p><span data-ttu-id="9fd54-138">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="9fd54-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="9fd54-139">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="9fd54-139">7/3/2012</span></span></p>
<p><span data-ttu-id="9fd54-140">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="9fd54-140">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fd54-141"><strong>Local do chamador</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-141"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-p108">Sub-rede IP do usuário que fez a chamada. É possível selecionar somente <strong>[Tudo]</strong> para indicar todas as sub-redes.</span><span class="sxs-lookup"><span data-stu-id="9fd54-p108">IP subnet of the user who placed the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fd54-144"><strong>Local do receptor da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-144"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-p109">Sub-rede IP do usuário que recebeu a chamada. É possível selecionar somente <strong>[Tudo]</strong> para indicar todas as sub-redes.</span><span class="sxs-lookup"><span data-stu-id="9fd54-p109">IP subnet of the user who received the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fd54-147"><strong>Tipo de rede</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-147"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-p110">Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="9fd54-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="9fd54-150">Todos os</span><span class="sxs-lookup"><span data-stu-id="9fd54-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="9fd54-151">Com fio</span><span class="sxs-lookup"><span data-stu-id="9fd54-151">Wired</span></span></p></li>
<li><p><span data-ttu-id="9fd54-152">Conexão</span><span class="sxs-lookup"><span data-stu-id="9fd54-152">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fd54-153"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-153"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-p111">Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="9fd54-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="9fd54-156">Todos os</span><span class="sxs-lookup"><span data-stu-id="9fd54-156">[All]</span></span></p></li>
<li><p><span data-ttu-id="9fd54-157">VPN</span><span class="sxs-lookup"><span data-stu-id="9fd54-157">VPN</span></span></p></li>
<li><p><span data-ttu-id="9fd54-158">Não VPN</span><span class="sxs-lookup"><span data-stu-id="9fd54-158">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="9fd54-159">Métrica</span><span class="sxs-lookup"><span data-stu-id="9fd54-159">Metrics</span></span>

<span data-ttu-id="9fd54-160">A tabela a seguir lista as informações fornecidas no Relatório de Locais.</span><span class="sxs-lookup"><span data-stu-id="9fd54-160">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="9fd54-161">Métricas do Relatório de Locais</span><span class="sxs-lookup"><span data-stu-id="9fd54-161">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fd54-162">Nome</span><span class="sxs-lookup"><span data-stu-id="9fd54-162">Name</span></span></th>
<th><span data-ttu-id="9fd54-163">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="9fd54-163">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9fd54-164">Descrição</span><span class="sxs-lookup"><span data-stu-id="9fd54-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fd54-165"><strong>Sub-rede do chamador </strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-165"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-166">Não</span><span class="sxs-lookup"><span data-stu-id="9fd54-166">No</span></span></p></td>
<td><p><span data-ttu-id="9fd54-167">Sub-rede IP do usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="9fd54-167">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fd54-168"><strong>Sub-rede do receptor da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-168"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-169">Não</span><span class="sxs-lookup"><span data-stu-id="9fd54-169">No</span></span></p></td>
<td><p><span data-ttu-id="9fd54-170">Sub-rede IP do usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="9fd54-170">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fd54-171"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-171"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-172">Sim</span><span class="sxs-lookup"><span data-stu-id="9fd54-172">Yes</span></span></p></td>
<td><p><span data-ttu-id="9fd54-173">Número total de chamadas realizadas.</span><span class="sxs-lookup"><span data-stu-id="9fd54-173">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fd54-174"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-174"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-175">Sim</span><span class="sxs-lookup"><span data-stu-id="9fd54-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="9fd54-p112">Porcentual de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada da qual pelo menos uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada que experimentou tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="9fd54-p112">Percentage of calls classified as poor calls. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fd54-178"><strong>Viagem de ida e volta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-178"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-179">Sim</span><span class="sxs-lookup"><span data-stu-id="9fd54-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="9fd54-p113">Quantidade média de (em milissegundos) exigida para que um pacote RTP (protocolo de transporte em tempo real) viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 100 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="9fd54-p113">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="9fd54-p114">Os valores altos de ida e volta pode ser causados por roteamento de chamada internacional, um erro de configuração de roteamento ou um servidor de mídia sobrecarregado. Tempos de ida e volta altos resultam em dificuldades com conversas de áudio em tempo real e bidirecionais.</span><span class="sxs-lookup"><span data-stu-id="9fd54-p114">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fd54-184"><strong>Degradação (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-184"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-185">Sim</span><span class="sxs-lookup"><span data-stu-id="9fd54-185">Yes</span></span></p></td>
<td><p><span data-ttu-id="9fd54-186">Quantidade média da degradação MOS enfrentada durante uma chamada.</span><span class="sxs-lookup"><span data-stu-id="9fd54-186">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="9fd54-187">Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0.</span><span class="sxs-lookup"><span data-stu-id="9fd54-187">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="9fd54-188">Um valor de 0,5 ou menos representa degradação aceitável.</span><span class="sxs-lookup"><span data-stu-id="9fd54-188">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="9fd54-189">Historicamente, pontuações de opções médias foram calculadas com usuários classificando a qualidade de uma chamada em uma escala de 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="9fd54-189">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="9fd54-190">No Lync Server, o Lync Server usa um conjunto de algoritmos para prever como os usuários classificaram uma chamada.</span><span class="sxs-lookup"><span data-stu-id="9fd54-190">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="9fd54-p116">Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="9fd54-p116">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fd54-193"><strong>Perda de pacote </strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-193"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-194">Sim</span><span class="sxs-lookup"><span data-stu-id="9fd54-194">Yes</span></span></p></td>
<td><p><span data-ttu-id="9fd54-p117">Taxa média de perda de pacote RTP. (A perda de pacote ocorre quando os pacotes RTP, um protocolo usado para transmissão de áudio e vídeo pela Internet, não conseguem chegar aos seus destinos.) Taxas de perda altas normalmente são causadas por congestionamento, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia sobrecarregado. A perda de pacote normalmente resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="9fd54-p117">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fd54-198"><strong>Torção</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-198"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-199">Sim</span><span class="sxs-lookup"><span data-stu-id="9fd54-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="9fd54-200">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="9fd54-200">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="9fd54-201">(Tremulação é uma medida do &quot; tremula &quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="9fd54-201">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fd54-202"><strong>Taxa de correção oculta</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-202"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-203">Sim</span><span class="sxs-lookup"><span data-stu-id="9fd54-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="9fd54-p119">Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="9fd54-p119">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fd54-206"><strong>Taxa de correção estendida</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-206"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-207">Sim</span><span class="sxs-lookup"><span data-stu-id="9fd54-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="9fd54-p120">Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="9fd54-p120">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fd54-210"><strong>Taxa de correção compactada</strong></span><span class="sxs-lookup"><span data-stu-id="9fd54-210"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="9fd54-211">Sim</span><span class="sxs-lookup"><span data-stu-id="9fd54-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="9fd54-p121">Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="9fd54-p121">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

