---
title: 'Lync Server 2013: tabela AudioStream'
description: 'Lync Server 2013: tabela AudioStream.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af2e622e14c54fa4f9a6313e1b0dae8f2483132
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552337"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="2facc-103">Tabela AudioStream no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2facc-103">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2facc-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2facc-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2facc-105">Cada registro representa um fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="2facc-105">Each record represents one audio stream.</span></span> <span data-ttu-id="2facc-106">Uma linha de mídia de áudio normalmente contém dois fluxos de áudio.</span><span class="sxs-lookup"><span data-stu-id="2facc-106">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2facc-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="2facc-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="2facc-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="2facc-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2facc-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-112">datetime</span><span class="sxs-lookup"><span data-stu-id="2facc-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="2facc-113">Primário</span><span class="sxs-lookup"><span data-stu-id="2facc-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="2facc-114">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2facc-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-116">int</span><span class="sxs-lookup"><span data-stu-id="2facc-116">int</span></span></p></td>
<td><p><span data-ttu-id="2facc-117">Primário</span><span class="sxs-lookup"><span data-stu-id="2facc-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="2facc-118">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2facc-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="2facc-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2facc-121">Primário</span><span class="sxs-lookup"><span data-stu-id="2facc-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="2facc-122">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="2facc-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-123"><strong>Streamid</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-124">int</span><span class="sxs-lookup"><span data-stu-id="2facc-124">int</span></span></p></td>
<td><p><span data-ttu-id="2facc-125">Primário</span><span class="sxs-lookup"><span data-stu-id="2facc-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="2facc-126">Identificação exclusiva em uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="2facc-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-127"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-127"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-128">int</span><span class="sxs-lookup"><span data-stu-id="2facc-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-129">Média de tremulação de rede a partir da estatística do protocolo RTCP.</span><span class="sxs-lookup"><span data-stu-id="2facc-129">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-130"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-130"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-131">int</span><span class="sxs-lookup"><span data-stu-id="2facc-131">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-132">Tremulação máxima da rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-132">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-133"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-133"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-134">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="2facc-134">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-135">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-135">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-136"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-136"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-137">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="2facc-137">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-138">Perda máxima de pacotes observada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-138">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-139"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-139"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-140">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="2facc-140">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-141">Densidade média de perda de pacote durante intermitências de perdas durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-141">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-142"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-142"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-143">int</span><span class="sxs-lookup"><span data-stu-id="2facc-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-144">Duração média de perda de pacote durante picos de perdas durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-144">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-145"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-145"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-146">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="2facc-146">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-147">Densidade média de perda de pacote durante intervalos entre picos de perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="2facc-147">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-148"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-148"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-149">int</span><span class="sxs-lookup"><span data-stu-id="2facc-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-150">Duração média de intervalos entre picos de perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="2facc-150">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-151"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-151"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-152">Int</span><span class="sxs-lookup"><span data-stu-id="2facc-152">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-153">Contagem de pacotes para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="2facc-153">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-154"><strong>Mais largura de banda</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-154"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-155">Int</span><span class="sxs-lookup"><span data-stu-id="2facc-155">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-156">Estimativas de largura de banda para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="2facc-156">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-157"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-157"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-158">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="2facc-158">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-p102">Degradação de MOS de rede para a chamada completa. O intervalo vai de 0,0 a 5,0. Essa métrica mostra o quanto o MOS de rede foi reduzido por causa de tremulação e perda de pacote. Para obter a qualidade aceitável, o MOS da rede deve ser menor que 0,5.</span><span class="sxs-lookup"><span data-stu-id="2facc-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-163"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-163"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-164">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="2facc-164">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-165">Degradação máxima de MOS de rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-165">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-166"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-166"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-167">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="2facc-167">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-168">Degradação de MOS de rede causada por tremulação.</span><span class="sxs-lookup"><span data-stu-id="2facc-168">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-169"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-169"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-170">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="2facc-170">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-171">Degradação de MOS de rede causada por perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="2facc-171">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-172"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-172"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-173">int</span><span class="sxs-lookup"><span data-stu-id="2facc-173">int</span></span></p></td>
<td><p><span data-ttu-id="2facc-174">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="2facc-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2facc-175">O codec de áudio usado para a chamada, referenciado da tabela PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="2facc-175">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-176"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-176"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-177">int</span><span class="sxs-lookup"><span data-stu-id="2facc-177">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-178">Taxa de amostragem para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="2facc-178">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-179"><strong>Aproxima</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-179"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-180">int</span><span class="sxs-lookup"><span data-stu-id="2facc-180">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-181">Tempo de ida e volta de estatísticas RTCP.</span><span class="sxs-lookup"><span data-stu-id="2facc-181">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="2facc-182">Para uma qualidade aceitável, isso deve ser menor que 100 ms.</span><span class="sxs-lookup"><span data-stu-id="2facc-182">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-183"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-183"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-184">int</span><span class="sxs-lookup"><span data-stu-id="2facc-184">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-185">Tempo máximo de ida e volta para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="2facc-185">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-186"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-186"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-187">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="2facc-187">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-188">Média de MOS de rede de banda ampla para a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-188">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="2facc-189">Essa métrica depende da perda de pacote, da tremulação e do codec usado.</span><span class="sxs-lookup"><span data-stu-id="2facc-189">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="2facc-190">O intervalo é [1,0 a 5,0].</span><span class="sxs-lookup"><span data-stu-id="2facc-190">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-191"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-191"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-192">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="2facc-192">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-193">O MOS de rede banda larga mínima para a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-193">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-194"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-194"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-195">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="2facc-195">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-196">A pontuação média prevista de banda larga de escuta do MOS para áudio enviado, incluindo nível de fala, nível de ruído e características do dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="2facc-196">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-197"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-197"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-198">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="2facc-198">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-199">O SendListenMOS mínimo para a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-199">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-200"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-200"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-201">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="2facc-201">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-202">A pontuação média prevista de banda larga de escuta para áudio recebido da rede, incluindo nível de fala, nível de ruído, codec, condições de rede e características do dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="2facc-202">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-203"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-203"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-204">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="2facc-204">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-205">O RecvListenMOS mínimo para a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-205">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-206"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-206"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-207">bits</span><span class="sxs-lookup"><span data-stu-id="2facc-207">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-208">Sinalizador que indica se o FEC de áudio foi usado para a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-208">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-209"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-209"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-210">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2facc-210">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-211">Taxa média de amostras escondidas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="2facc-211">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-212"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-212"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-213">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2facc-213">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-214">Taxa média de amostras corrigidas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="2facc-214">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-215"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-215"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-216">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="2facc-216">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-217">Taxa média de amostras compactadas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="2facc-217">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-218"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-218"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-219">bits</span><span class="sxs-lookup"><span data-stu-id="2facc-219">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-220">Dados de fluxo no lado do destinatário são recebidos.</span><span class="sxs-lookup"><span data-stu-id="2facc-220">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-221"><strong>Saída</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-221"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-222">bits</span><span class="sxs-lookup"><span data-stu-id="2facc-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-223">Dados de fluxo no lado do remetente são recebidos.</span><span class="sxs-lookup"><span data-stu-id="2facc-223">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-224"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-224"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-225">bits</span><span class="sxs-lookup"><span data-stu-id="2facc-225">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2facc-226">1 significa que a direção do fluxo é do chamador para o receptor.</span><span class="sxs-lookup"><span data-stu-id="2facc-226">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="2facc-227">0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="2facc-227">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-228"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-228"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-229">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-229">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-230">Desvio padrão para tempos de chegada de tremulação.</span><span class="sxs-lookup"><span data-stu-id="2facc-230">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="2facc-231">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-231">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-232"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-232"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-233">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-234">Taxa máxima de pacotes ocultos pelo reparo.</span><span class="sxs-lookup"><span data-stu-id="2facc-234">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="2facc-235">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-235">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-236"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-236"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-237">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-238">Desvio padrão para a taxa de pacotes ocultos pelo reparo.</span><span class="sxs-lookup"><span data-stu-id="2facc-238">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="2facc-239">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-239">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-240"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-240"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-241">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-241">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-242">Taxa de pacotes descartados pelo REO reparo em comparação com o número total de pacotes recebidos.</span><span class="sxs-lookup"><span data-stu-id="2facc-242">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="2facc-243">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-243">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-244"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-244"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-245">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-246">Taxa de pacotes de correção de erro de encaminhamento usados em comparação com o número total de pacotes recebidos.</span><span class="sxs-lookup"><span data-stu-id="2facc-246">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="2facc-247">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-247">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-248"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-248"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-249">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-250">Número máximo de pacotes de áudio que foram compactados pelo reparánte.</span><span class="sxs-lookup"><span data-stu-id="2facc-250">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="2facc-251">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-252"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-252"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-253">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-254">Indica a porcentagem de tempo em que a chamada estava em um estado de congestionamento de perda.</span><span class="sxs-lookup"><span data-stu-id="2facc-254">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="2facc-255">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-256"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-256"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-257">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-258">Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada de pacotes de rede.</span><span class="sxs-lookup"><span data-stu-id="2facc-258">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="2facc-259">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-259">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-260"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-260"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-261">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-261">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-262">Indica a porcentagem de tempo em que a chamada estava competindo por recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="2facc-262">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="2facc-263">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-263">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-264"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-264"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-265">int</span><span class="sxs-lookup"><span data-stu-id="2facc-265">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-266">Quantidade mínima de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-266">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="2facc-267">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-268"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-268"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-269">int</span><span class="sxs-lookup"><span data-stu-id="2facc-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-270">Quantidade máxima de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-270">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="2facc-271">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-271">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-272"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-272"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-273">int</span><span class="sxs-lookup"><span data-stu-id="2facc-273">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-274">O desvio padrão da estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-274">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="2facc-275">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-275">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-276"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-276"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-277">int</span><span class="sxs-lookup"><span data-stu-id="2facc-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-278">Quantidade média de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="2facc-278">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="2facc-279">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-280"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-280"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-281">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-281">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-p105">Quantidade total de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="2facc-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="2facc-284">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-285"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-285"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-286">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-p106">Quantidade média de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="2facc-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="2facc-289">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-289">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-290"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-290"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-291">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-p107">Quantidade máxima de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="2facc-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="2facc-294">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-294">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-295"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-295"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-296">int</span><span class="sxs-lookup"><span data-stu-id="2facc-296">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-p108">Total de ocorrências de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="2facc-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2facc-300">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-301"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-301"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-302">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-302">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-p109">Densidade total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="2facc-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2facc-306">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-306">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-307"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-307"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-308">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-308">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-p110">Duração total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="2facc-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2facc-312">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-312">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-313"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-313"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-314">int</span><span class="sxs-lookup"><span data-stu-id="2facc-314">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-p111">Total de ocorrências de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="2facc-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2facc-318">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-319"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-319"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-320">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-p112">Densidade total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="2facc-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2facc-324">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-325"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-325"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-326">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-326">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-p113">Duração total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="2facc-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2facc-330">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-331"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-331"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-332">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-332">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-333">Porcentagem da chamada decodificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="2facc-333">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="2facc-334">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-335"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-335"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-336">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-337">Porcentagem da chamada processada como estéreo pelo cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="2facc-337">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="2facc-338">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-338">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-339"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-339"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-340">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-341">Taxa de perda de pacote após a correção de erro encaminhar ter sido aplicada.</span><span class="sxs-lookup"><span data-stu-id="2facc-341">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="2facc-342">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-342">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2facc-343"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-343"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-344">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-344">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-345">Porcentagem da chamada codificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="2facc-345">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="2facc-346">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-346">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2facc-347"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2facc-347"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2facc-348">flutuação</span><span class="sxs-lookup"><span data-stu-id="2facc-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2facc-349">Porcentagem da chamada capturada como estéreo pelo cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="2facc-349">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="2facc-350">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2facc-350">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

