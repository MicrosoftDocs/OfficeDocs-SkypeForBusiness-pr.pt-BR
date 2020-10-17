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
ms.openlocfilehash: 331b2afbfa4b6c4147ffab3765af4e9e5031c190
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502868"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="8bdd4-102">Tabela AudioStream no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bdd4-102">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bdd4-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8bdd4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8bdd4-104">Cada registro representa um fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-104">Each record represents one audio stream.</span></span> <span data-ttu-id="8bdd4-105">Uma linha de mídia de áudio normalmente contém dois fluxos de áudio.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8bdd4-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8bdd4-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8bdd4-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8bdd4-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-111">datetime</span><span class="sxs-lookup"><span data-stu-id="8bdd4-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8bdd4-112">Primário</span><span class="sxs-lookup"><span data-stu-id="8bdd4-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="8bdd4-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-115">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-115">int</span></span></p></td>
<td><p><span data-ttu-id="8bdd4-116">Primário</span><span class="sxs-lookup"><span data-stu-id="8bdd4-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="8bdd4-117">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="8bdd4-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8bdd4-120">Primário</span><span class="sxs-lookup"><span data-stu-id="8bdd4-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="8bdd4-121">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-122"><strong>Streamid</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-123">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-123">int</span></span></p></td>
<td><p><span data-ttu-id="8bdd4-124">Primário</span><span class="sxs-lookup"><span data-stu-id="8bdd4-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="8bdd4-125">Identificação exclusiva em uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-127">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-128">Média de tremulação de rede a partir da estatística do protocolo RTCP.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-130">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-131">Tremulação máxima da rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-133">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-134">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-136">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-137">Perda máxima de pacotes observada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-139">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-140">Densidade média de perda de pacote durante intermitências de perdas durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-142">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-143">Duração média de perda de pacote durante picos de perdas durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-145">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-146">Densidade média de perda de pacote durante intervalos entre picos de perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-148">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-149">Duração média de intervalos entre picos de perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-151">Int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-152">Contagem de pacotes para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-153"><strong>Mais largura de banda</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-154">Int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-155">Estimativas de largura de banda para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-157">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-p102">Degradação de MOS de rede para a chamada completa. O intervalo vai de 0,0 a 5,0. Essa métrica mostra o quanto o MOS de rede foi reduzido por causa de tremulação e perda de pacote. Para obter a qualidade aceitável, o MOS da rede deve ser menor que 0,5.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-163">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-164">Degradação máxima de MOS de rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-166">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-167">Degradação de MOS de rede causada por tremulação.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-169">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-170">Degradação de MOS de rede causada por perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-172">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-172">int</span></span></p></td>
<td><p><span data-ttu-id="8bdd4-173">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="8bdd4-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8bdd4-174">O codec de áudio usado para a chamada, referenciado da tabela PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-176">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-177">Taxa de amostragem para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-178"><strong>Aproxima</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-179">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-180">Tempo de ida e volta de estatísticas RTCP.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="8bdd4-181">Para uma qualidade aceitável, isso deve ser menor que 100 ms.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-183">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-184">Tempo máximo de ida e volta para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-186">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-187">Média de MOS de rede de banda ampla para a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="8bdd4-188">Essa métrica depende da perda de pacote, da tremulação e do codec usado.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="8bdd4-189">O intervalo é [1,0 a 5,0].</span><span class="sxs-lookup"><span data-stu-id="8bdd4-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-191">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-192">O MOS de rede banda larga mínima para a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-194">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-195">A pontuação média prevista de banda larga de escuta do MOS para áudio enviado, incluindo nível de fala, nível de ruído e características do dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-197">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-198">O SendListenMOS mínimo para a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-200">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-201">A pontuação média prevista de banda larga de escuta para áudio recebido da rede, incluindo nível de fala, nível de ruído, codec, condições de rede e características do dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-203">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-204">O RecvListenMOS mínimo para a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-206">bits</span><span class="sxs-lookup"><span data-stu-id="8bdd4-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-207">Sinalizador que indica se o FEC de áudio foi usado para a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-209">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-210">Taxa média de amostras escondidas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-212">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-213">Taxa média de amostras corrigidas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-215">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8bdd4-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-216">Taxa média de amostras compactadas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-217"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-218">bits</span><span class="sxs-lookup"><span data-stu-id="8bdd4-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-219">Dados de fluxo no lado do destinatário são recebidos.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-220"><strong>Saída</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-221">bits</span><span class="sxs-lookup"><span data-stu-id="8bdd4-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-222">Dados de fluxo no lado do remetente são recebidos.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-224">bits</span><span class="sxs-lookup"><span data-stu-id="8bdd4-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8bdd4-225">1 significa que a direção do fluxo é do chamador para o receptor.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="8bdd4-226">0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-228">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-229">Desvio padrão para tempos de chegada de tremulação.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="8bdd4-230">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-232">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-233">Taxa máxima de pacotes ocultos pelo reparo.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="8bdd4-234">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-236">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-237">Desvio padrão para a taxa de pacotes ocultos pelo reparo.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="8bdd4-238">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-240">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-241">Taxa de pacotes descartados pelo REO reparo em comparação com o número total de pacotes recebidos.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="8bdd4-242">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-244">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-245">Taxa de pacotes de correção de erro de encaminhamento usados em comparação com o número total de pacotes recebidos.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="8bdd4-246">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-248">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-249">Número máximo de pacotes de áudio que foram compactados pelo reparánte.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="8bdd4-250">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-252">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-253">Indica a porcentagem de tempo em que a chamada estava em um estado de congestionamento de perda.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="8bdd4-254">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-256">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-257">Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada de pacotes de rede.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="8bdd4-258">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-260">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-261">Indica a porcentagem de tempo em que a chamada estava competindo por recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="8bdd4-262">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-264">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-265">Quantidade mínima de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="8bdd4-266">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-268">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-269">Quantidade máxima de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="8bdd4-270">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-272">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-273">O desvio padrão da estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="8bdd4-274">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-276">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-277">Quantidade média de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="8bdd4-278">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-280">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-p105">Quantidade total de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="8bdd4-283">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-285">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-p106">Quantidade média de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="8bdd4-288">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-290">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-p107">Quantidade máxima de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="8bdd4-293">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-295">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-p108">Total de ocorrências de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="8bdd4-299">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-301">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-p109">Densidade total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="8bdd4-305">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-307">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-p110">Duração total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="8bdd4-311">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-313">int</span><span class="sxs-lookup"><span data-stu-id="8bdd4-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-p111">Total de ocorrências de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="8bdd4-317">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-319">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-p112">Densidade total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="8bdd4-323">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-325">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-p113">Duração total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="8bdd4-329">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-331">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-332">Porcentagem da chamada decodificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="8bdd4-333">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-335">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-336">Porcentagem da chamada processada como estéreo pelo cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="8bdd4-337">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-339">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-340">Taxa de perda de pacote após a correção de erro encaminhar ter sido aplicada.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="8bdd4-341">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8bdd4-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-343">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-344">Porcentagem da chamada codificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="8bdd4-345">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8bdd4-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="8bdd4-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="8bdd4-347">flutuação</span><span class="sxs-lookup"><span data-stu-id="8bdd4-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8bdd4-348">Porcentagem da chamada capturada como estéreo pelo cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="8bdd4-349">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8bdd4-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

