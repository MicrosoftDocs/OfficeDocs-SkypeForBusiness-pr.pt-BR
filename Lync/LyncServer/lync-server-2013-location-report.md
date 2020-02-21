---
title: 'Lync Server 2013: relatório de localização'
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
ms.openlocfilehash: 2035d66d9b690a351a9b286eeff378ec0a36c1f9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="2a109-102">Relatório de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a109-102">Location Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a109-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2a109-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2a109-p101">O Relatório de Localização oferece informações sobre as métricas de qualidade de chamada agrupadas pelo local de rede (isto é, pela subrede). Se seus usuários enfrentarem problemas com suas chamadas, este relatório pode ajudar você a determinar se estes problemas são amplos ou estão confinados a um determinado segmento da rede.</span><span class="sxs-lookup"><span data-stu-id="2a109-p101">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet). If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="2a109-106">Acessando o Relatório de Localização</span><span class="sxs-lookup"><span data-stu-id="2a109-106">Accessing the Location Report</span></span>

<span data-ttu-id="2a109-p102">O Relatório de Localização é acessado na página inicial de Relatórios de Monitoramento. É possível detalhar o Relatório de Lista de Chamadas clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="2a109-p102">The Location Report is accessed from the Monitoring Reports home page. You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="2a109-109">Volume da chamada</span><span class="sxs-lookup"><span data-stu-id="2a109-109">Call volume</span></span>

  - <span data-ttu-id="2a109-110">Porcentagem de chamada inválida</span><span class="sxs-lookup"><span data-stu-id="2a109-110">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2a109-111">Filtros</span><span class="sxs-lookup"><span data-stu-id="2a109-111">Filters</span></span>

<span data-ttu-id="2a109-p103">Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Locais permite que você filtre coisas como o local onde a chamada foi originada ou se a chamada ocorreu em uma conexão com ou sem fio. Também é possível escolher como os dados devem ser agrupados. Nesse caso, as chamadas são agrupadas por hora, dia, semana ou mês.</span><span class="sxs-lookup"><span data-stu-id="2a109-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="2a109-116">A tabela a seguir lista os filtros que podem ser usados com o Relatório de Locais.</span><span class="sxs-lookup"><span data-stu-id="2a109-116">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="2a109-117">Filtros do Relatório de Locais</span><span class="sxs-lookup"><span data-stu-id="2a109-117">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a109-118">Nome</span><span class="sxs-lookup"><span data-stu-id="2a109-118">Name</span></span></th>
<th><span data-ttu-id="2a109-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="2a109-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a109-120"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-p104">Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</span><span class="sxs-lookup"><span data-stu-id="2a109-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2a109-123">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="2a109-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2a109-p105">Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="2a109-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2a109-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2a109-126">7/7/2012</span></span></p>
<p><span data-ttu-id="2a109-127">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="2a109-127">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2a109-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2a109-128">7/3/2012</span></span></p>
<p><span data-ttu-id="2a109-129">As semanas são sempre de domingo a sábado.</span><span class="sxs-lookup"><span data-stu-id="2a109-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a109-130"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-p106">Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</span><span class="sxs-lookup"><span data-stu-id="2a109-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2a109-133">7/7/2012 13:00 horas</span><span class="sxs-lookup"><span data-stu-id="2a109-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2a109-p107">Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</span><span class="sxs-lookup"><span data-stu-id="2a109-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2a109-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2a109-136">7/7/2012</span></span></p>
<p><span data-ttu-id="2a109-137">Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</span><span class="sxs-lookup"><span data-stu-id="2a109-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2a109-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2a109-138">7/3/2012</span></span></p>
<p><span data-ttu-id="2a109-139">As semanas sempre correm do domingo até sábado.</span><span class="sxs-lookup"><span data-stu-id="2a109-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a109-140"><strong>Local do chamador</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-140"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-p108">Sub-rede IP do usuário que fez a chamada. É possível selecionar somente <strong>[Tudo]</strong> para indicar todas as sub-redes.</span><span class="sxs-lookup"><span data-stu-id="2a109-p108">IP subnet of the user who placed the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a109-143"><strong>Local do receptor da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-143"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-p109">Sub-rede IP do usuário que recebeu a chamada. É possível selecionar somente <strong>[Tudo]</strong> para indicar todas as sub-redes.</span><span class="sxs-lookup"><span data-stu-id="2a109-p109">IP subnet of the user who received the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a109-146"><strong>Tipo de rede</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-146"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-p110">Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="2a109-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="2a109-149">Todos os</span><span class="sxs-lookup"><span data-stu-id="2a109-149">[All]</span></span></p></li>
<li><p><span data-ttu-id="2a109-150">Com fio</span><span class="sxs-lookup"><span data-stu-id="2a109-150">Wired</span></span></p></li>
<li><p><span data-ttu-id="2a109-151">Conexão</span><span class="sxs-lookup"><span data-stu-id="2a109-151">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a109-152"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-152"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-p111">Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="2a109-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="2a109-155">Todos os</span><span class="sxs-lookup"><span data-stu-id="2a109-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="2a109-156">VPN</span><span class="sxs-lookup"><span data-stu-id="2a109-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="2a109-157">Não VPN</span><span class="sxs-lookup"><span data-stu-id="2a109-157">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2a109-158">Métricas</span><span class="sxs-lookup"><span data-stu-id="2a109-158">Metrics</span></span>

<span data-ttu-id="2a109-159">A tabela a seguir lista as informações fornecidas no Relatório de Locais.</span><span class="sxs-lookup"><span data-stu-id="2a109-159">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="2a109-160">Métricas do Relatório de Locais</span><span class="sxs-lookup"><span data-stu-id="2a109-160">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a109-161">Nome</span><span class="sxs-lookup"><span data-stu-id="2a109-161">Name</span></span></th>
<th><span data-ttu-id="2a109-162">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="2a109-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2a109-163">Descrição</span><span class="sxs-lookup"><span data-stu-id="2a109-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a109-164"><strong>Sub-rede do chamador </strong></span><span class="sxs-lookup"><span data-stu-id="2a109-164"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-165">Não</span><span class="sxs-lookup"><span data-stu-id="2a109-165">No</span></span></p></td>
<td><p><span data-ttu-id="2a109-166">Sub-rede IP do usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="2a109-166">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a109-167"><strong>Sub-rede do receptor da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-167"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-168">Não</span><span class="sxs-lookup"><span data-stu-id="2a109-168">No</span></span></p></td>
<td><p><span data-ttu-id="2a109-169">Sub-rede IP do usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="2a109-169">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a109-170"><strong>Volume da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-170"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-171">Sim</span><span class="sxs-lookup"><span data-stu-id="2a109-171">Yes</span></span></p></td>
<td><p><span data-ttu-id="2a109-172">Número total de chamadas realizadas.</span><span class="sxs-lookup"><span data-stu-id="2a109-172">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a109-173"><strong>Percentual de chamadas ruins</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-173"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-174">Sim</span><span class="sxs-lookup"><span data-stu-id="2a109-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="2a109-p112">Porcentual de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada da qual pelo menos uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada que experimentou tremulação excessiva).</span><span class="sxs-lookup"><span data-stu-id="2a109-p112">Percentage of calls classified as poor calls. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a109-177"><strong>Viagem de ida e volta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-177"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-178">Sim</span><span class="sxs-lookup"><span data-stu-id="2a109-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="2a109-p113">Quantidade média de (em milissegundos) exigida para que um pacote RTP (protocolo de transporte em tempo real) viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 100 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="2a109-p113">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="2a109-p114">Os valores altos de ida e volta pode ser causados por roteamento de chamada internacional, um erro de configuração de roteamento ou um servidor de mídia sobrecarregado. Tempos de ida e volta altos resultam em dificuldades com conversas de áudio em tempo real e bidirecionais.</span><span class="sxs-lookup"><span data-stu-id="2a109-p114">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a109-183"><strong>Degradação (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-184">Sim</span><span class="sxs-lookup"><span data-stu-id="2a109-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="2a109-185">Quantidade média da degradação MOS enfrentada durante uma chamada.</span><span class="sxs-lookup"><span data-stu-id="2a109-185">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="2a109-186">Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0.</span><span class="sxs-lookup"><span data-stu-id="2a109-186">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="2a109-187">Um valor de 0,5 ou menos representa degradação aceitável.</span><span class="sxs-lookup"><span data-stu-id="2a109-187">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="2a109-188">Historicamente, pontuações de opções médias foram calculadas com usuários classificando a qualidade de uma chamada em uma escala de 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="2a109-188">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="2a109-189">No Lync Server, o Lync Server usa um conjunto de algoritmos para prever como os usuários classificaram uma chamada.</span><span class="sxs-lookup"><span data-stu-id="2a109-189">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="2a109-p116">Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="2a109-p116">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a109-192"><strong>Perda de pacote </strong></span><span class="sxs-lookup"><span data-stu-id="2a109-192"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-193">Sim</span><span class="sxs-lookup"><span data-stu-id="2a109-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="2a109-p117">Taxa média de perda de pacote RTP. (A perda de pacote ocorre quando os pacotes RTP, um protocolo usado para transmissão de áudio e vídeo pela Internet, não conseguem chegar aos seus destinos.) Taxas de perda altas normalmente são causadas por congestionamento, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia sobrecarregado. A perda de pacote normalmente resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="2a109-p117">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a109-197"><strong>Torção</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-197"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-198">Sim</span><span class="sxs-lookup"><span data-stu-id="2a109-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="2a109-199">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="2a109-199">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="2a109-200">(Tremulação é uma medida do &quot;tremula&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="2a109-200">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a109-201"><strong>Taxa de correção oculta</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-201"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-202">Sim</span><span class="sxs-lookup"><span data-stu-id="2a109-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="2a109-p119">Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="2a109-p119">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a109-205"><strong>Taxa de correção estendida</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-205"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-206">Sim</span><span class="sxs-lookup"><span data-stu-id="2a109-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="2a109-p120">Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="2a109-p120">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a109-209"><strong>Taxa de correção compactada</strong></span><span class="sxs-lookup"><span data-stu-id="2a109-209"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2a109-210">Sim</span><span class="sxs-lookup"><span data-stu-id="2a109-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="2a109-p121">Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="2a109-p121">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

