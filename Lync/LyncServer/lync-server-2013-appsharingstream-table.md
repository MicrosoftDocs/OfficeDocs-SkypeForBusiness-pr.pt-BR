---
title: 'Lync Server 2013: tabela AppSharingStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56f23e214ffcffad8613d413924a53ffe571883d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="cbdd7-102">Tabela AppSharingStream no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbdd7-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbdd7-103">_**Tópico da última modificação:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="cbdd7-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="cbdd7-104">A tabela AppSharingStream contém métricas de qualidade de experiência para os fluxos de rede usados para compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="cbdd7-105">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbdd7-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="cbdd7-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="cbdd7-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="cbdd7-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="cbdd7-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="cbdd7-112">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="cbdd7-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cbdd7-113">Data e hora em que a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-115">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-115">int</span></span></p></td>
<td><p><span data-ttu-id="cbdd7-116">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="cbdd7-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cbdd7-117">Identificador sequencial usado para distinguir entre as sessões iniciadas na mesma data e ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="cbdd7-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="cbdd7-120">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="cbdd7-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cbdd7-121">Representa o tipo de linha de vídeo usado na chamada.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="cbdd7-122">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="cbdd7-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbdd7-123">0 – áudio</span><span class="sxs-lookup"><span data-stu-id="cbdd7-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="cbdd7-124">1 – vídeo</span><span class="sxs-lookup"><span data-stu-id="cbdd7-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="cbdd7-125">2 – vídeo panorâmico</span><span class="sxs-lookup"><span data-stu-id="cbdd7-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="cbdd7-126">3 – compartilhamento de aplicativos/área de trabalho</span><span class="sxs-lookup"><span data-stu-id="cbdd7-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-127"><strong>Streamid</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-128">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-128">int</span></span></p></td>
<td><p><span data-ttu-id="cbdd7-129">Primária</span><span class="sxs-lookup"><span data-stu-id="cbdd7-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="cbdd7-130">Identificador exclusivo do fluxo de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-132">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-133">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="cbdd7-134">(Tremulação é uma medida do &quot;shakiness&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou um servidor de mídia sobrecarregado, resultando em áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-136">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-137">Variação máxima detectada entre as entradas do pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="cbdd7-138">(Tremulação é uma medida do &quot;shakiness&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou um servidor de mídia sobrecarregado, resultando em áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-139"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-140">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-p105">Quantidade média (em milissegundos) exigida para que um pacote de protocolo RTP viaje até outro ponto de extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="cbdd7-p106">Os valores altos de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-146">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-147">A quantidade máxima de (em milissegundos) necessária para que um pacote de protocolo de transporte em tempo real vá para outro ponto de extremidade e, em seguida, retorne.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="cbdd7-148">Tempos de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="cbdd7-p108">Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-152">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-p109">Taxa média de perda de pacotes de RTP (protocolo de transporte em tempo real). (A perda de pacotes ocorre quando pacotes de RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-157">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-158">Taxa máxima de perda de pacotes do protocolo de transporte em tempo real (RTP).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="cbdd7-159">(A perda de pacote ocorre quando pacotes RTP, um protocolo usado para a transmissão de áudio e vídeo pela Internet, não atinge seu destino.) Tarifas de alta perda são geralmente causadas por congestionamento; falta de largura de banda; congestionamento ou interferência sem fio; ou um servidor de mídia sobrecarregado.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="cbdd7-160">A perda de pacote normalmente resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-162">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-163">Número de pacotes enviados.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-164"><strong>Largura de banda</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-165">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-166">Largura de banda unidirecional estimada disponível no final da sessão.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="cbdd7-167">Relatado em bits por segundo.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-169">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-170">Descrição da carga de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-172">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-173">Valor total de latência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-173">Total amount of one-way latency.</span></span> <span data-ttu-id="cbdd7-174">A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-175"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-176">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-177">Valor médio de uma latência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-177">Average amount of one-way latency.</span></span> <span data-ttu-id="cbdd7-178">A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-180">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-181">Valor máximo de latência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="cbdd7-182">A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-184">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-185">Total de ocorrências intermitentes unidirecionais.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="cbdd7-186">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="cbdd7-187">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-189">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-190">Densidade total de intermitência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-190">Total one-way burst density.</span></span> <span data-ttu-id="cbdd7-191">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="cbdd7-192">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-194">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-195">Duração total de intermitência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-195">Total one-way burst duration.</span></span> <span data-ttu-id="cbdd7-196">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="cbdd7-197">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-199">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-200">Total de ocorrências de espaçamento unidirecionais.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="cbdd7-201">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="cbdd7-202">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-204">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-205">Densidade total do espaço unidirecional.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-205">Total one-way gap density.</span></span> <span data-ttu-id="cbdd7-206">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="cbdd7-207">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-209">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-210">Duração total unidirecional do espaço.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-210">Total one-way gap duration.</span></span> <span data-ttu-id="cbdd7-211">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="cbdd7-212">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="cbdd7-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-215">Função do aplicativo (compartilhamento ou visualizador) e tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-217">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-218">Tempo total de processamento para blocos RDP (protocolo de área de trabalho remota).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="cbdd7-219">Um total maior equivale a um atraso mais longo na experiência de visualização.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-220"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-221">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-222">Tempo médio de processamento de blocos RDP (protocolo de área de trabalho remota).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="cbdd7-223">Um total maior equivale a um atraso mais longo na experiência de visualização.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-225">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-226">Tempo máximo de processamento de blocos RDP (protocolo de área de trabalho remota).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="cbdd7-227">Um total maior equivale a um atraso mais longo na experiência de visualização.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-229">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-230">Ocorrências intermitentes no tempo de processamento dos blocos RDP (protocolo de área de trabalho remota).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="cbdd7-231">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-233">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-234">Densidade de intermitência no tempo de processamento dos blocos RDP (protocolo de área de trabalho remota).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="cbdd7-235">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-237">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-238">Duração da intermitência no tempo de processamento dos blocos RDP (protocolo de área de trabalho remota).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="cbdd7-239">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-241">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-242">Ocorrências de lacunas no tempo de processamento dos blocos RDP (protocolo de área de trabalho remota).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-244">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-245">Densidade de espaço no bloco tempo de processamento de blocos RDP (protocolo de área de trabalho remota).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="cbdd7-246">A densidade de lacunas baixas equivale a uma melhor experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-248">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-249">Duração do espaço no bloco de tempo de processamento para blocos RDP (protocolo de área de trabalho remota).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="cbdd7-250">Durações de espaço curto equivalem a uma melhor experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-252">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-253">Taxa total de blocos capturados (em blocos por segundo).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-255">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-256">Taxa média de blocos capturados (em blocos por segundo).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-258">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-259">Taxa máxima de blocos capturados (em blocos por segundo).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-261">em t</span><span class="sxs-lookup"><span data-stu-id="cbdd7-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-262">Ocorrências intermitentes na taxa de blocos capturados (em blocos por segundo).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-264">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-265">Densidade de intermitência na taxa de blocos capturados (em blocos por segundo).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-267">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-268">Duração da intermitência na taxa de blocos capturados (em blocos por segundo).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-270">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-271">Ocorrências de lacunas na taxa de blocos capturados (em blocos por segundo).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-273">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-274">Densidade da lacuna na taxa de blocos capturados (em blocos por segundo).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-276">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-277">Duração do espaçamento na taxa de blocos capturados (em blocos por segundo).</span><span class="sxs-lookup"><span data-stu-id="cbdd7-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-278"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-279">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-280">A porcentagem total do conteúdo que não chegou ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-282">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-283">A porcentagem média do conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-285">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-286">A porcentagem máxima do conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartada e sobrescrita pelo conteúdo novo.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-288">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-289">As ocorrências de intermitência do conteúdo que não chegavam ao visualizador foram descartadas e sobrescritas pelo conteúdo novo.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-291">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-292">Densidade de intermitência para o conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-294">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-295">A duração da intermitência para o conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-297">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-298">As ocorrências de lacunas do conteúdo que não chegavam ao visualizador foram descartadas e sobrescritas pelo conteúdo novo.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-300">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-301">Densidade de espaço para o conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-303">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-304">Duração do espaço para o conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-306">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-307">Número total de quadros recortedos da fonte de elementos gráficos.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-309">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-310">Número médio de quadros recortes da fonte de elementos gráficos.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-312">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-313">Número máximo de quadros recortes da fonte de elementos gráficos.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-315">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-316">Ocorrências intermitentes nos quadros recortes da fonte gráfica.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-318">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-319">Densidade de intermitência nos quadros recapturada da fonte de elementos gráficos.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-321">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-322">A duração da intermitência nos quadros é recapturada da fonte de elementos gráficos.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-324">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-325">Ocorrências de lacunas nos quadros recortes da fonte gráfica.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-327">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-328">Densidade de lacunas nos quadros recortes da fonte gráfica.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-330">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-331">Intervalo de tempo nos quadros recortes da fonte de elementos gráficos.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-333">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-334">Taxa de quadro de entrada total conforme recebido pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-336">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-337">Taxa média de quadros recebidos, conforme recebido pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-339">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-340">Taxa máxima de bloco de entrada recebido pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-342">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-343">Ocorrências de intermitência na taxa de peça de entrada recebidas pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-345">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-346">Densidade de intermitência na taxa de peça de entrada como recebida pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-348">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-349">Duração da intermitência na taxa de peça de entrada como recebida pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-351">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-352">Ocorrências de lacunas na taxa de peça de entrada recebidas pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-354">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-355">Densidade de espaço na taxa de peça de entrada como recebida pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-357">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-358">Duração do espaçamento na taxa de peça de entrada como recebida pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-360">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-361">Taxa de quadro de entrada total conforme recebido pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-363">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-364">Taxa média de quadros recebidos, conforme recebido pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-366">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-367">Taxa máxima de quadros de entrada, conforme recebido pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-369">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-370">Ocorrências de intermitência na taxa de quadros de entrada conforme recebidas pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-372">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-373">Densidade de intermitência na taxa de quadros de entrada como recebida pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-375">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-376">Duração da intermitência na taxa de quadros de entrada como recebida pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-378">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-379">Ocorrências de lacunas na taxa de quadros de entrada recebidas pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-381">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-382">Densidade de espaço na taxa de quadros de entrada como recebida pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-384">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-385">Duração do espaçamento na taxa de quadro de entrada como recebida pelo Visualizador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-387">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-388">Taxa total de blocos de saída para o remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-390">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-391">Taxa média de peça de saída para o remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-393">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-394">Taxa máxima de bloco de saída para o remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-396">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-397">Ocorrências de intermitência na taxa de bloco de saída para o remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-399">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-400">Densidade de intermitência na taxa de peça de saída do remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-402">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-403">Duração da intermitência na taxa de peça de saída do remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-405">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-406">Ocorrências de lacunas na taxa de bloco de saída para o remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-408">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-409">Densidade de espaço na taxa de bloco de saída para o remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-411">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-412">Duração do espaçamento na taxa de peça de saída para o remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-414">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-415">Taxa de quadros de saída total para o remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-417">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-418">taxa média de quadros de saída para o remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-420">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-421">Taxa máxima de quadros de saída para o remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-423">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-424">Ocorrências intermitentes na taxa de quadros de saída do remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-426">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-427">Densidade de intermitência na taxa de quadros de saída do remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-429">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-430">Duração da intermitência na taxa de quadros de saída do remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-432">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-433">Ocorrências de lacunas na taxa de quadros de saída do remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-435">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-436">Densidade da lacuna na taxa de quadros de saída do remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-438">float</span><span class="sxs-lookup"><span data-stu-id="cbdd7-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-439">Duração do espaçamento na taxa de quadros de saída do remetente.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-441">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-442">Altura média da resolução de vídeo em pixels.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-444">int</span><span class="sxs-lookup"><span data-stu-id="cbdd7-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-445">Largura média da resolução de vídeo em pixels.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-446"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-447">bit</span><span class="sxs-lookup"><span data-stu-id="cbdd7-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-448">Taxa média de quadros (em quadros por segundo) para transmissões de entrada.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbdd7-449"><strong>Saída</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-450">bit</span><span class="sxs-lookup"><span data-stu-id="cbdd7-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-451">Taxa média de quadros (em quadros por segundo) para transmissões de saída.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbdd7-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="cbdd7-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="cbdd7-453">bit</span><span class="sxs-lookup"><span data-stu-id="cbdd7-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cbdd7-454">1 significa que a direção do fluxo é do chamador para o chamado.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="cbdd7-455">0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="cbdd7-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

