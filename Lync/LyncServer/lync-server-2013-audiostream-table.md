---
title: 'Lync Server 2013: tabela AudioStream'
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
ms.openlocfilehash: 0f169a00a9eff262d0229daf6e52110d64cf7a34
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="a780f-102">Tabela AudioStream no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a780f-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a780f-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a780f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a780f-104">Cada registro representa um fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="a780f-104">Each record represents one audio stream.</span></span> <span data-ttu-id="a780f-105">Uma linha de mídia de áudio normalmente contém dois fluxos de áudio.</span><span class="sxs-lookup"><span data-stu-id="a780f-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a780f-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a780f-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a780f-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a780f-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a780f-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a780f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a780f-112">Primário</span><span class="sxs-lookup"><span data-stu-id="a780f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a780f-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a780f-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-115">int</span><span class="sxs-lookup"><span data-stu-id="a780f-115">int</span></span></p></td>
<td><p><span data-ttu-id="a780f-116">Primário</span><span class="sxs-lookup"><span data-stu-id="a780f-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="a780f-117">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a780f-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="a780f-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a780f-120">Primário</span><span class="sxs-lookup"><span data-stu-id="a780f-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="a780f-121">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a780f-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-122"><strong>Streamid</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-123">int</span><span class="sxs-lookup"><span data-stu-id="a780f-123">int</span></span></p></td>
<td><p><span data-ttu-id="a780f-124">Primário</span><span class="sxs-lookup"><span data-stu-id="a780f-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="a780f-125">Identificação exclusiva em uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="a780f-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-127">int</span><span class="sxs-lookup"><span data-stu-id="a780f-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-128">Média de tremulação de rede a partir da estatística do protocolo RTCP.</span><span class="sxs-lookup"><span data-stu-id="a780f-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-130">int</span><span class="sxs-lookup"><span data-stu-id="a780f-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-131">Tremulação máxima da rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-133">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="a780f-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-134">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-136">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="a780f-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-137">Perda máxima de pacotes observada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-139">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a780f-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-140">Densidade média de perda de pacote durante intermitências de perdas durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-142">int</span><span class="sxs-lookup"><span data-stu-id="a780f-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-143">Duração média de perda de pacote durante picos de perdas durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-145">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a780f-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-146">Densidade média de perda de pacote durante intervalos entre picos de perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="a780f-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-148">int</span><span class="sxs-lookup"><span data-stu-id="a780f-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-149">Duração média de intervalos entre picos de perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="a780f-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-151">Int</span><span class="sxs-lookup"><span data-stu-id="a780f-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-152">Contagem de pacotes para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="a780f-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-153"><strong>Mais largura de banda</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-154">Int</span><span class="sxs-lookup"><span data-stu-id="a780f-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-155">Estimativas de largura de banda para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="a780f-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-157">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a780f-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-p102">Degradação de MOS de rede para a chamada completa. O intervalo vai de 0,0 a 5,0. Essa métrica mostra o quanto o MOS de rede foi reduzido por causa de tremulação e perda de pacote. Para obter a qualidade aceitável, o MOS da rede deve ser menor que 0,5.</span><span class="sxs-lookup"><span data-stu-id="a780f-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-163">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a780f-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-164">Degradação máxima de MOS de rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-166">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a780f-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-167">Degradação de MOS de rede causada por tremulação.</span><span class="sxs-lookup"><span data-stu-id="a780f-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-169">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a780f-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-170">Degradação de MOS de rede causada por perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="a780f-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-172">int</span><span class="sxs-lookup"><span data-stu-id="a780f-172">int</span></span></p></td>
<td><p><span data-ttu-id="a780f-173">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="a780f-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a780f-174">O codec de áudio usado para a chamada, referenciado da tabela PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="a780f-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-176">int</span><span class="sxs-lookup"><span data-stu-id="a780f-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-177">Taxa de amostragem para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="a780f-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-178"><strong>Aproxima</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-179">int</span><span class="sxs-lookup"><span data-stu-id="a780f-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-180">Tempo de ida e volta de estatísticas RTCP.</span><span class="sxs-lookup"><span data-stu-id="a780f-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="a780f-181">Para uma qualidade aceitável, isso deve ser menor que 100 ms.</span><span class="sxs-lookup"><span data-stu-id="a780f-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-183">int</span><span class="sxs-lookup"><span data-stu-id="a780f-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-184">Tempo máximo de ida e volta para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="a780f-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-186">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a780f-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-187">Média de MOS de rede de banda ampla para a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="a780f-188">Essa métrica depende da perda de pacote, da tremulação e do codec usado.</span><span class="sxs-lookup"><span data-stu-id="a780f-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="a780f-189">O intervalo é [1,0 a 5,0].</span><span class="sxs-lookup"><span data-stu-id="a780f-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-191">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a780f-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-192">O MOS de rede banda larga mínima para a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-194">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a780f-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-195">A pontuação média prevista de banda larga de escuta do MOS para áudio enviado, incluindo nível de fala, nível de ruído e características do dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="a780f-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-197">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a780f-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-198">O SendListenMOS mínimo para a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-200">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a780f-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-201">A pontuação média prevista de banda larga de escuta para áudio recebido da rede, incluindo nível de fala, nível de ruído, codec, condições de rede e características do dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="a780f-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-203">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="a780f-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-204">O RecvListenMOS mínimo para a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-206">bits</span><span class="sxs-lookup"><span data-stu-id="a780f-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-207">Sinalizador que indica se o FEC de áudio foi usado para a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-209">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a780f-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-210">Taxa média de amostras escondidas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="a780f-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-212">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a780f-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-213">Taxa média de amostras corrigidas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="a780f-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-215">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a780f-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-216">Taxa média de amostras compactadas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="a780f-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-217"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-218">bits</span><span class="sxs-lookup"><span data-stu-id="a780f-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-219">Dados de fluxo no lado do destinatário são recebidos.</span><span class="sxs-lookup"><span data-stu-id="a780f-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-220"><strong>Saída</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-221">bits</span><span class="sxs-lookup"><span data-stu-id="a780f-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-222">Dados de fluxo no lado do remetente são recebidos.</span><span class="sxs-lookup"><span data-stu-id="a780f-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-224">bits</span><span class="sxs-lookup"><span data-stu-id="a780f-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a780f-225">1 significa que a direção do fluxo é do chamador para o receptor.</span><span class="sxs-lookup"><span data-stu-id="a780f-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="a780f-226">0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="a780f-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-228">float</span><span class="sxs-lookup"><span data-stu-id="a780f-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-229">Desvio padrão para tempos de chegada de tremulação.</span><span class="sxs-lookup"><span data-stu-id="a780f-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="a780f-230">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-232">float</span><span class="sxs-lookup"><span data-stu-id="a780f-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-233">Taxa máxima de pacotes ocultos pelo reparo.</span><span class="sxs-lookup"><span data-stu-id="a780f-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="a780f-234">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-236">float</span><span class="sxs-lookup"><span data-stu-id="a780f-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-237">Desvio padrão para a taxa de pacotes ocultos pelo reparo.</span><span class="sxs-lookup"><span data-stu-id="a780f-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="a780f-238">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-240">float</span><span class="sxs-lookup"><span data-stu-id="a780f-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-241">Taxa de pacotes descartados pelo REO reparo em comparação com o número total de pacotes recebidos.</span><span class="sxs-lookup"><span data-stu-id="a780f-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="a780f-242">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-244">float</span><span class="sxs-lookup"><span data-stu-id="a780f-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-245">Taxa de pacotes de correção de erro de encaminhamento usados em comparação com o número total de pacotes recebidos.</span><span class="sxs-lookup"><span data-stu-id="a780f-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="a780f-246">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-248">float</span><span class="sxs-lookup"><span data-stu-id="a780f-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-249">Número máximo de pacotes de áudio que foram compactados pelo reparánte.</span><span class="sxs-lookup"><span data-stu-id="a780f-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="a780f-250">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-252">float</span><span class="sxs-lookup"><span data-stu-id="a780f-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-253">Indica a porcentagem de tempo em que a chamada estava em um estado de congestionamento de perda.</span><span class="sxs-lookup"><span data-stu-id="a780f-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="a780f-254">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-256">float</span><span class="sxs-lookup"><span data-stu-id="a780f-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-257">Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada de pacotes de rede.</span><span class="sxs-lookup"><span data-stu-id="a780f-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="a780f-258">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-260">float</span><span class="sxs-lookup"><span data-stu-id="a780f-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-261">Indica a porcentagem de tempo em que a chamada estava competindo por recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="a780f-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="a780f-262">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-264">int</span><span class="sxs-lookup"><span data-stu-id="a780f-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-265">Quantidade mínima de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a780f-266">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-268">int</span><span class="sxs-lookup"><span data-stu-id="a780f-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-269">Quantidade máxima de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a780f-270">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-272">int</span><span class="sxs-lookup"><span data-stu-id="a780f-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-273">O desvio padrão da estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a780f-274">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-276">int</span><span class="sxs-lookup"><span data-stu-id="a780f-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-277">Quantidade média de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a780f-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a780f-278">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-280">float</span><span class="sxs-lookup"><span data-stu-id="a780f-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-p105">Quantidade total de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a780f-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="a780f-283">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-285">float</span><span class="sxs-lookup"><span data-stu-id="a780f-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-p106">Quantidade média de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a780f-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="a780f-288">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-290">float</span><span class="sxs-lookup"><span data-stu-id="a780f-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-p107">Quantidade máxima de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a780f-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="a780f-293">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-295">int</span><span class="sxs-lookup"><span data-stu-id="a780f-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-p108">Total de ocorrências de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a780f-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a780f-299">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-301">float</span><span class="sxs-lookup"><span data-stu-id="a780f-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-p109">Densidade total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a780f-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a780f-305">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-307">float</span><span class="sxs-lookup"><span data-stu-id="a780f-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-p110">Duração total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a780f-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a780f-311">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-313">int</span><span class="sxs-lookup"><span data-stu-id="a780f-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-p111">Total de ocorrências de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a780f-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a780f-317">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-319">float</span><span class="sxs-lookup"><span data-stu-id="a780f-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-p112">Densidade total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a780f-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a780f-323">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-325">float</span><span class="sxs-lookup"><span data-stu-id="a780f-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-p113">Duração total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a780f-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a780f-329">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-331">float</span><span class="sxs-lookup"><span data-stu-id="a780f-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-332">Porcentagem da chamada decodificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="a780f-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="a780f-333">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-335">float</span><span class="sxs-lookup"><span data-stu-id="a780f-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-336">Porcentagem da chamada processada como estéreo pelo cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="a780f-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="a780f-337">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-339">float</span><span class="sxs-lookup"><span data-stu-id="a780f-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-340">Taxa de perda de pacote após a correção de erro encaminhar ter sido aplicada.</span><span class="sxs-lookup"><span data-stu-id="a780f-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="a780f-341">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a780f-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-343">float</span><span class="sxs-lookup"><span data-stu-id="a780f-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-344">Porcentagem da chamada codificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="a780f-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="a780f-345">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a780f-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a780f-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a780f-347">float</span><span class="sxs-lookup"><span data-stu-id="a780f-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a780f-348">Porcentagem da chamada capturada como estéreo pelo cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="a780f-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="a780f-349">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a780f-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

