---
title: 'Lync Server 2013: Tabela AudioStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9412001652f4f323bdd3fb5722d0d7222535fd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="840cf-102">Tabela AudioStream no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="840cf-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="840cf-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="840cf-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="840cf-104">Cada registro representa um fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="840cf-104">Each record represents one audio stream.</span></span> <span data-ttu-id="840cf-105">Uma linha de mídia de áudio geralmente contém dois fluxos de áudio.</span><span class="sxs-lookup"><span data-stu-id="840cf-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="840cf-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="840cf-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="840cf-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="840cf-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="840cf-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-111">datetime</span><span class="sxs-lookup"><span data-stu-id="840cf-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="840cf-112">Primária</span><span class="sxs-lookup"><span data-stu-id="840cf-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="840cf-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="840cf-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-115">int</span><span class="sxs-lookup"><span data-stu-id="840cf-115">int</span></span></p></td>
<td><p><span data-ttu-id="840cf-116">Primária</span><span class="sxs-lookup"><span data-stu-id="840cf-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="840cf-117">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="840cf-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="840cf-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="840cf-120">Primária</span><span class="sxs-lookup"><span data-stu-id="840cf-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="840cf-121">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="840cf-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-122"><strong>Streamid</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-123">int</span><span class="sxs-lookup"><span data-stu-id="840cf-123">int</span></span></p></td>
<td><p><span data-ttu-id="840cf-124">Primária</span><span class="sxs-lookup"><span data-stu-id="840cf-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="840cf-125">ID exclusiva dentro de uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="840cf-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-127">int</span><span class="sxs-lookup"><span data-stu-id="840cf-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-128">Tremulação média de rede de estatísticas de protocolo de controle de tempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="840cf-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-130">int</span><span class="sxs-lookup"><span data-stu-id="840cf-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-131">Maior tremulação de rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-133">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="840cf-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-134">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-136">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="840cf-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-137">Perda máxima de pacote observado durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-139">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="840cf-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-140">Densidade média de perda de pacote durante intermitências de perdas durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-142">int</span><span class="sxs-lookup"><span data-stu-id="840cf-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-143">Duração média da perda de pacote durante intermitências de perdas durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-145">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="840cf-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-146">Densidade média de perda de pacote durante intervalos entre intermitências de perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="840cf-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-148">int</span><span class="sxs-lookup"><span data-stu-id="840cf-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-149">Duração média de lacunas entre intermitências de perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="840cf-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-151">Núm</span><span class="sxs-lookup"><span data-stu-id="840cf-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-152">Contagem de pacotes para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="840cf-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-153"><strong>Largura de banda</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-154">Núm</span><span class="sxs-lookup"><span data-stu-id="840cf-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-155">Estimativas de largura de banda para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="840cf-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-157">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="840cf-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-158">Degradação do MOS de rede para toda a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="840cf-159">O intervalo é de 0,0 a 5,0.</span><span class="sxs-lookup"><span data-stu-id="840cf-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="840cf-160">Essa métrica mostra o valor que o MOS de rede foi reduzido devido à instabilidade e à perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="840cf-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="840cf-161">Para ter uma qualidade aceitável, ele deve ser menor do que 0,5.</span><span class="sxs-lookup"><span data-stu-id="840cf-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-163">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="840cf-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-164">Degradação do MOS de rede máxima durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-166">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="840cf-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-167">Degradação de MOS de rede causada pela tremulação.</span><span class="sxs-lookup"><span data-stu-id="840cf-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-169">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="840cf-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-170">Degradação de MOS de rede causada por perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="840cf-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-172">int</span><span class="sxs-lookup"><span data-stu-id="840cf-172">int</span></span></p></td>
<td><p><span data-ttu-id="840cf-173">Exterior</span><span class="sxs-lookup"><span data-stu-id="840cf-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="840cf-174">O codec de áudio usado para a chamada, referenciado pela tabela PayloadDescription.</span><span class="sxs-lookup"><span data-stu-id="840cf-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-176">int</span><span class="sxs-lookup"><span data-stu-id="840cf-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-177">Taxa de amostragem do fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="840cf-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-179">int</span><span class="sxs-lookup"><span data-stu-id="840cf-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-180">Tempo de ida e volta das estatísticas do RTCP.</span><span class="sxs-lookup"><span data-stu-id="840cf-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="840cf-181">Para ter uma qualidade aceitável, isso deve ser menor que 100 milhões.</span><span class="sxs-lookup"><span data-stu-id="840cf-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-183">int</span><span class="sxs-lookup"><span data-stu-id="840cf-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-184">Tempo máximo de ida e volta do fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="840cf-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-186">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="840cf-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-187">Banda larga médio de um MOS de rede para a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="840cf-188">Essa métrica depende da perda de pacotes, da tremulação e do codec usados.</span><span class="sxs-lookup"><span data-stu-id="840cf-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="840cf-189">O intervalo é de [1,0 a 5,0].</span><span class="sxs-lookup"><span data-stu-id="840cf-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-191">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="840cf-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-192">A banda larga de rede mínima para a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-194">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="840cf-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-195">A média de Pontuação estimada banda larga de escuta do MOS para áudio enviado, incluindo o nível de fala, o nível de ruído e as características do dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="840cf-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-197">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="840cf-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-198">A SendListenMOS mínima para a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-200">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="840cf-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-201">A média de Pontuação estimada banda larga de escuta do MOS para áudio recebido da rede, incluindo o nível de fala, o nível de ruído, o codec, as condições de rede e as características do dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="840cf-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-203">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="840cf-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-204">A RecvListenMOS mínima para a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-206">bit</span><span class="sxs-lookup"><span data-stu-id="840cf-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-207">Sinalizador que indica se o FEC de áudio foi usado para a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-209">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="840cf-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-210">Índice médio de amostras ocultas geradas pelo reparo de áudio para amostras típicas.</span><span class="sxs-lookup"><span data-stu-id="840cf-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-212">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="840cf-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-213">Índice médio de amostras ampliadas geradas pelo reparo de áudio para amostras típicas.</span><span class="sxs-lookup"><span data-stu-id="840cf-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-215">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="840cf-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-216">Índice médio de amostras compactadas geradas pelo reparo de áudio para amostras típicas.</span><span class="sxs-lookup"><span data-stu-id="840cf-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-217"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-218">bit</span><span class="sxs-lookup"><span data-stu-id="840cf-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-219">Os dados de fluxo no lado do receptor são recebidos.</span><span class="sxs-lookup"><span data-stu-id="840cf-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-220"><strong>Saída</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-221">bit</span><span class="sxs-lookup"><span data-stu-id="840cf-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-222">Dados de fluxo no lado do remetente são recebidos.</span><span class="sxs-lookup"><span data-stu-id="840cf-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-224">bit</span><span class="sxs-lookup"><span data-stu-id="840cf-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="840cf-225">1 significa que a direção do fluxo é do chamador para o receptor.</span><span class="sxs-lookup"><span data-stu-id="840cf-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="840cf-226">0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="840cf-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-228">float</span><span class="sxs-lookup"><span data-stu-id="840cf-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-229">Desvio padrão de tempos de chegada de tremulação.</span><span class="sxs-lookup"><span data-stu-id="840cf-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="840cf-230">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-232">float</span><span class="sxs-lookup"><span data-stu-id="840cf-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-233">Índice máximo de pacotes ocultados pelo REO reparo.</span><span class="sxs-lookup"><span data-stu-id="840cf-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="840cf-234">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-236">float</span><span class="sxs-lookup"><span data-stu-id="840cf-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-237">Desvio padrão da taxa de pacotes ocultados pelo REO reparo.</span><span class="sxs-lookup"><span data-stu-id="840cf-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="840cf-238">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-240">float</span><span class="sxs-lookup"><span data-stu-id="840cf-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-241">Taxa de pacotes removidos pelo REO reparo em comparação ao número total de pacotes recebidos.</span><span class="sxs-lookup"><span data-stu-id="840cf-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="840cf-242">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-244">float</span><span class="sxs-lookup"><span data-stu-id="840cf-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-245">Taxa de pacotes de correção de erro usados encaminhar em comparação com o número total de pacotes recebidos.</span><span class="sxs-lookup"><span data-stu-id="840cf-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="840cf-246">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-248">float</span><span class="sxs-lookup"><span data-stu-id="840cf-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-249">Número máximo de pacotes de áudio que foram compactados pelo REO reparo.</span><span class="sxs-lookup"><span data-stu-id="840cf-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="840cf-250">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-252">float</span><span class="sxs-lookup"><span data-stu-id="840cf-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-253">Indica a porcentagem do tempo em que a chamada estava em um estado de congestionamento de perda.</span><span class="sxs-lookup"><span data-stu-id="840cf-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="840cf-254">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-256">float</span><span class="sxs-lookup"><span data-stu-id="840cf-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-257">Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada dos pacotes de rede.</span><span class="sxs-lookup"><span data-stu-id="840cf-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="840cf-258">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-260">float</span><span class="sxs-lookup"><span data-stu-id="840cf-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-261">Indica a porcentagem do tempo quando a chamada estava competindo pelos recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="840cf-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="840cf-262">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-264">int</span><span class="sxs-lookup"><span data-stu-id="840cf-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-265">Valor mínimo de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="840cf-266">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-268">int</span><span class="sxs-lookup"><span data-stu-id="840cf-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-269">Valor máximo de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="840cf-270">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-272">int</span><span class="sxs-lookup"><span data-stu-id="840cf-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-273">O desvio padrão da estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="840cf-274">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-276">int</span><span class="sxs-lookup"><span data-stu-id="840cf-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-277">Valor médio da estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="840cf-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="840cf-278">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-280">float</span><span class="sxs-lookup"><span data-stu-id="840cf-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-281">Valor total de latência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="840cf-281">Total amount of one-way latency.</span></span> <span data-ttu-id="840cf-282">A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="840cf-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="840cf-283">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-284"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-285">float</span><span class="sxs-lookup"><span data-stu-id="840cf-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-286">Valor médio de uma latência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="840cf-286">Average amount of one-way latency.</span></span> <span data-ttu-id="840cf-287">A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="840cf-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="840cf-288">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-290">float</span><span class="sxs-lookup"><span data-stu-id="840cf-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-291">Valor máximo de latência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="840cf-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="840cf-292">A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="840cf-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="840cf-293">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-295">int</span><span class="sxs-lookup"><span data-stu-id="840cf-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-296">Total de ocorrências intermitentes unidirecionais.</span><span class="sxs-lookup"><span data-stu-id="840cf-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="840cf-297">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</span><span class="sxs-lookup"><span data-stu-id="840cf-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="840cf-298">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="840cf-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="840cf-299">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-301">float</span><span class="sxs-lookup"><span data-stu-id="840cf-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-302">Densidade total de intermitência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="840cf-302">Total one-way burst density.</span></span> <span data-ttu-id="840cf-303">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</span><span class="sxs-lookup"><span data-stu-id="840cf-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="840cf-304">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="840cf-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="840cf-305">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-307">float</span><span class="sxs-lookup"><span data-stu-id="840cf-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-308">Duração total de intermitência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="840cf-308">Total one-way burst duration.</span></span> <span data-ttu-id="840cf-309">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</span><span class="sxs-lookup"><span data-stu-id="840cf-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="840cf-310">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="840cf-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="840cf-311">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-313">int</span><span class="sxs-lookup"><span data-stu-id="840cf-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-314">Total de ocorrências de espaçamento unidirecionais.</span><span class="sxs-lookup"><span data-stu-id="840cf-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="840cf-315">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências.</span><span class="sxs-lookup"><span data-stu-id="840cf-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="840cf-316">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="840cf-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="840cf-317">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-319">float</span><span class="sxs-lookup"><span data-stu-id="840cf-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-320">Densidade total do espaço unidirecional.</span><span class="sxs-lookup"><span data-stu-id="840cf-320">Total one-way gap density.</span></span> <span data-ttu-id="840cf-321">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências.</span><span class="sxs-lookup"><span data-stu-id="840cf-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="840cf-322">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="840cf-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="840cf-323">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-325">float</span><span class="sxs-lookup"><span data-stu-id="840cf-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-326">Duração total unidirecional do espaço.</span><span class="sxs-lookup"><span data-stu-id="840cf-326">Total one-way gap duration.</span></span> <span data-ttu-id="840cf-327">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências.</span><span class="sxs-lookup"><span data-stu-id="840cf-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="840cf-328">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="840cf-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="840cf-329">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-331">float</span><span class="sxs-lookup"><span data-stu-id="840cf-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-332">Porcentagem da chamada decodificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="840cf-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="840cf-333">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-335">float</span><span class="sxs-lookup"><span data-stu-id="840cf-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-336">Porcentagem da chamada renderizada como estéreo pelo cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="840cf-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="840cf-337">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-339">float</span><span class="sxs-lookup"><span data-stu-id="840cf-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-340">Taxa de perda de pacote após a aplicação da correção de erro de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="840cf-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="840cf-341">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="840cf-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-343">float</span><span class="sxs-lookup"><span data-stu-id="840cf-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-344">Porcentagem da chamada codificada como estéreo.</span><span class="sxs-lookup"><span data-stu-id="840cf-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="840cf-345">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="840cf-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="840cf-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="840cf-347">float</span><span class="sxs-lookup"><span data-stu-id="840cf-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="840cf-348">Porcentagem da chamada capturada como estéreo pelo cancelador de eco acústico.</span><span class="sxs-lookup"><span data-stu-id="840cf-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="840cf-349">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="840cf-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

