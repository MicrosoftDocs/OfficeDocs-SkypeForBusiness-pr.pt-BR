---
title: 'Lync Server 2013: Tabela VideoStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 674d013faca3b43db04d2c5b4802103def83dbd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="818d9-102">Tabela VideoStream no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="818d9-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="818d9-103">_**Tópico da última modificação:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="818d9-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="818d9-104">Cada registro representa um fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="818d9-104">Each record represents one video stream.</span></span> <span data-ttu-id="818d9-105">Uma linha de mídia de vídeo geralmente contém dois fluxos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="818d9-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="818d9-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="818d9-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="818d9-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="818d9-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="818d9-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-111">datetime</span><span class="sxs-lookup"><span data-stu-id="818d9-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="818d9-112">Primária</span><span class="sxs-lookup"><span data-stu-id="818d9-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="818d9-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="818d9-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-115">int</span><span class="sxs-lookup"><span data-stu-id="818d9-115">int</span></span></p></td>
<td><p><span data-ttu-id="818d9-116">Primária</span><span class="sxs-lookup"><span data-stu-id="818d9-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="818d9-117">R referenciada na <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="818d9-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="818d9-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="818d9-120">Primária</span><span class="sxs-lookup"><span data-stu-id="818d9-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="818d9-121">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="818d9-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-122"><strong>Streamid</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-123">int</span><span class="sxs-lookup"><span data-stu-id="818d9-123">int</span></span></p></td>
<td><p><span data-ttu-id="818d9-124">Primária</span><span class="sxs-lookup"><span data-stu-id="818d9-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="818d9-125">ID exclusiva dentro de uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="818d9-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-127">smallint</span><span class="sxs-lookup"><span data-stu-id="818d9-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="818d9-128">Estrangeiro, primário</span><span class="sxs-lookup"><span data-stu-id="818d9-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="818d9-129">Descrição da carga.</span><span class="sxs-lookup"><span data-stu-id="818d9-129">Payload description.</span></span> <span data-ttu-id="818d9-130">Consulte a <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="818d9-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-132">int</span><span class="sxs-lookup"><span data-stu-id="818d9-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-133">Tremulação média de rede de estatísticas de protocolo de controle de tempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="818d9-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-135">int</span><span class="sxs-lookup"><span data-stu-id="818d9-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-136">Maior tremulação de rede durante a sessão de vídeo.</span><span class="sxs-lookup"><span data-stu-id="818d9-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-137"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-138">int</span><span class="sxs-lookup"><span data-stu-id="818d9-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-139">Tempo de ida e volta das estatísticas do RTCP.</span><span class="sxs-lookup"><span data-stu-id="818d9-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-141">int</span><span class="sxs-lookup"><span data-stu-id="818d9-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-142">Tempo máximo de ida e volta do fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="818d9-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-144">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="818d9-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-145">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="818d9-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-147">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="818d9-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-148">Perda máxima de pacote observado durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="818d9-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-150">int</span><span class="sxs-lookup"><span data-stu-id="818d9-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-151">Contagem de pacotes para o fluxo de vídeo (protocolo de transporte em tempo real, RTP).</span><span class="sxs-lookup"><span data-stu-id="818d9-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-152"><strong>Largura de banda</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-153">int</span><span class="sxs-lookup"><span data-stu-id="818d9-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-154">Estimativas de largura de banda para o fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="818d9-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-156">caractere (9)</span><span class="sxs-lookup"><span data-stu-id="818d9-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-157">Resolução do vídeo em largura de pixels multiplicada pela altura de pixels.</span><span class="sxs-lookup"><span data-stu-id="818d9-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="818d9-158">Relatado como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="818d9-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-160">int</span><span class="sxs-lookup"><span data-stu-id="818d9-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-161">Taxa média de bits do fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="818d9-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-163">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="818d9-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-164">A taxa de quadros de vídeo recebida.</span><span class="sxs-lookup"><span data-stu-id="818d9-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-166">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="818d9-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-167">A taxa de quadros de vídeo enviada.</span><span class="sxs-lookup"><span data-stu-id="818d9-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-169">int</span><span class="sxs-lookup"><span data-stu-id="818d9-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-170">A taxa máxima de bits de vídeo durante a sessão de vídeo.</span><span class="sxs-lookup"><span data-stu-id="818d9-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-172">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="818d9-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-173">A porcentagem total de quadros de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="818d9-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-175">bit</span><span class="sxs-lookup"><span data-stu-id="818d9-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-176">Não disponível.</span><span class="sxs-lookup"><span data-stu-id="818d9-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-177"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-178">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="818d9-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-179">A porcentagem total de quadros de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="818d9-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="818d9-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-182">A porcentagem da chamada que estava na resolução de formato de intercâmbio (CIF) comum.</span><span class="sxs-lookup"><span data-stu-id="818d9-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="818d9-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-185">A porcentagem da chamada que estava na resolução VGA.</span><span class="sxs-lookup"><span data-stu-id="818d9-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="818d9-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-188">A porcentagem da chamada que estava a HD720 resolução.</span><span class="sxs-lookup"><span data-stu-id="818d9-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="818d9-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-191">Porcentagem de duração da chamada sem depósito de quadro.</span><span class="sxs-lookup"><span data-stu-id="818d9-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="818d9-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-194">Porcentagem de duração da chamada com B frame drop.</span><span class="sxs-lookup"><span data-stu-id="818d9-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="818d9-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-197">Porcentagem da duração da chamada com o depósito de quadros BP.</span><span class="sxs-lookup"><span data-stu-id="818d9-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="818d9-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-200">Porcentagem da duração da chamada com o BPSP frame drop.</span><span class="sxs-lookup"><span data-stu-id="818d9-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="818d9-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-203">Porcentagem da duração da chamada com o BPSPI frame drop.</span><span class="sxs-lookup"><span data-stu-id="818d9-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-204"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-205">bit</span><span class="sxs-lookup"><span data-stu-id="818d9-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-206">Os dados de fluxo no lado do receptor são recebidos.</span><span class="sxs-lookup"><span data-stu-id="818d9-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-207"><strong>Saída</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-208">bit</span><span class="sxs-lookup"><span data-stu-id="818d9-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-209">Dados de fluxo no lado do remetente são recebidos.</span><span class="sxs-lookup"><span data-stu-id="818d9-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-211">bit</span><span class="sxs-lookup"><span data-stu-id="818d9-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="818d9-212">1 significa que a direção do fluxo é do chamador para o chamado.</span><span class="sxs-lookup"><span data-stu-id="818d9-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="818d9-213">0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="818d9-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-215">float</span><span class="sxs-lookup"><span data-stu-id="818d9-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-216">Indica a porcentagem do tempo em que a chamada estava em um estado de congestionamento de perda.</span><span class="sxs-lookup"><span data-stu-id="818d9-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="818d9-217">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-219">float</span><span class="sxs-lookup"><span data-stu-id="818d9-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-220">Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada dos pacotes de rede.</span><span class="sxs-lookup"><span data-stu-id="818d9-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="818d9-221">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-223">float</span><span class="sxs-lookup"><span data-stu-id="818d9-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-224">Indica a porcentagem do tempo quando a chamada estava competindo pelos recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="818d9-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="818d9-225">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-227">int</span><span class="sxs-lookup"><span data-stu-id="818d9-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-228">Valor mínimo de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="818d9-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="818d9-229">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-231">int</span><span class="sxs-lookup"><span data-stu-id="818d9-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-232">Valor máximo de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="818d9-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="818d9-233">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-235">int</span><span class="sxs-lookup"><span data-stu-id="818d9-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-236">O desvio padrão da estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="818d9-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="818d9-237">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-239">int</span><span class="sxs-lookup"><span data-stu-id="818d9-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-240">Valor médio da estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="818d9-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="818d9-241">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-243">float</span><span class="sxs-lookup"><span data-stu-id="818d9-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-244">Porcentagem da chamada na qual o ponto de extremidade determinou que a conexão de rede não pôde dar suporte a vídeo MultiView.</span><span class="sxs-lookup"><span data-stu-id="818d9-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="818d9-245">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-247">float</span><span class="sxs-lookup"><span data-stu-id="818d9-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-248">Valor total de latência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="818d9-248">Total amount of one-way latency.</span></span> <span data-ttu-id="818d9-249">A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="818d9-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="818d9-250">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-251"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-252">float</span><span class="sxs-lookup"><span data-stu-id="818d9-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-253">Valor médio de uma latência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="818d9-253">Average amount of one-way latency.</span></span> <span data-ttu-id="818d9-254">A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="818d9-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="818d9-255">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-257">float</span><span class="sxs-lookup"><span data-stu-id="818d9-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-258">Valor máximo de latência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="818d9-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="818d9-259">A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="818d9-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="818d9-260">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-262">int</span><span class="sxs-lookup"><span data-stu-id="818d9-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-263">Total de ocorrências intermitentes unidirecionais.</span><span class="sxs-lookup"><span data-stu-id="818d9-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="818d9-264">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</span><span class="sxs-lookup"><span data-stu-id="818d9-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="818d9-265">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="818d9-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="818d9-266">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-268">int</span><span class="sxs-lookup"><span data-stu-id="818d9-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-269">Densidade total de intermitência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="818d9-269">Total one-way burst density.</span></span> <span data-ttu-id="818d9-270">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</span><span class="sxs-lookup"><span data-stu-id="818d9-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="818d9-271">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="818d9-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="818d9-272">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-274">float</span><span class="sxs-lookup"><span data-stu-id="818d9-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-275">Duração total de intermitência unidirecional.</span><span class="sxs-lookup"><span data-stu-id="818d9-275">Total one-way burst duration.</span></span> <span data-ttu-id="818d9-276">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</span><span class="sxs-lookup"><span data-stu-id="818d9-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="818d9-277">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="818d9-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="818d9-278">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-280">int</span><span class="sxs-lookup"><span data-stu-id="818d9-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-281">Total de ocorrências de espaçamento unidirecionais.</span><span class="sxs-lookup"><span data-stu-id="818d9-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="818d9-282">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências.</span><span class="sxs-lookup"><span data-stu-id="818d9-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="818d9-283">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="818d9-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="818d9-284">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-286">float</span><span class="sxs-lookup"><span data-stu-id="818d9-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-287">Densidade total do espaço unidirecional.</span><span class="sxs-lookup"><span data-stu-id="818d9-287">Total one-way gap density.</span></span> <span data-ttu-id="818d9-288">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências.</span><span class="sxs-lookup"><span data-stu-id="818d9-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="818d9-289">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="818d9-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="818d9-290">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-292">float</span><span class="sxs-lookup"><span data-stu-id="818d9-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-293">Duração total unidirecional do espaço.</span><span class="sxs-lookup"><span data-stu-id="818d9-293">Total one-way gap duration.</span></span> <span data-ttu-id="818d9-294">Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências.</span><span class="sxs-lookup"><span data-stu-id="818d9-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="818d9-295">Essa métrica mede o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="818d9-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="818d9-296">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-297"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-298">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="818d9-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-299">Taxa de perda de pacotes de vídeo.</span><span class="sxs-lookup"><span data-stu-id="818d9-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="818d9-300">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-302">int</span><span class="sxs-lookup"><span data-stu-id="818d9-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-303">Quantidade média de largura de banda alocada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="818d9-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="818d9-304">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-306">smallint</span><span class="sxs-lookup"><span data-stu-id="818d9-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="818d9-307">Exterior</span><span class="sxs-lookup"><span data-stu-id="818d9-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="818d9-308">Tipo de codecs de vídeo usados pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="818d9-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="818d9-309">Consulte a <a href="lync-server-2013-codecdescription-table.md">tabela CodecDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="818d9-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="818d9-310">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-312">int</span><span class="sxs-lookup"><span data-stu-id="818d9-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-313">Largura da resolução usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="818d9-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="818d9-314">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-316">int</span><span class="sxs-lookup"><span data-stu-id="818d9-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-317">Altura da resolução usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="818d9-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="818d9-318">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-320">float</span><span class="sxs-lookup"><span data-stu-id="818d9-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-321">Transmissão média de taxa de quadros de vídeo usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="818d9-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="818d9-322">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-324">int</span><span class="sxs-lookup"><span data-stu-id="818d9-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-325">Taxa máxima de bits do remetente.</span><span class="sxs-lookup"><span data-stu-id="818d9-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="818d9-326">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-328">int</span><span class="sxs-lookup"><span data-stu-id="818d9-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-329">Taxa média de bits para o remetente.</span><span class="sxs-lookup"><span data-stu-id="818d9-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-331">int</span><span class="sxs-lookup"><span data-stu-id="818d9-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-332">Número máximo de fluxos de vídeo usados pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="818d9-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="818d9-333">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-335">smallint</span><span class="sxs-lookup"><span data-stu-id="818d9-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="818d9-336">Exterior</span><span class="sxs-lookup"><span data-stu-id="818d9-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="818d9-337">Códigos de vídeo usados pelo destinatário.</span><span class="sxs-lookup"><span data-stu-id="818d9-337">Video codes used by the receiver.</span></span> <span data-ttu-id="818d9-338">Consulte a <a href="lync-server-2013-codecdescription-table.md">tabela CodecDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="818d9-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="818d9-339">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-341">int</span><span class="sxs-lookup"><span data-stu-id="818d9-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-342">Largura da resolução usada pelo destinatário.</span><span class="sxs-lookup"><span data-stu-id="818d9-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="818d9-343">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-345">int</span><span class="sxs-lookup"><span data-stu-id="818d9-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-346">Altura da resolução usada pelo destinatário.</span><span class="sxs-lookup"><span data-stu-id="818d9-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="818d9-347">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-348"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-349">float</span><span class="sxs-lookup"><span data-stu-id="818d9-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-350">Taxa média de quadros de vídeo usada pelo destinatário.</span><span class="sxs-lookup"><span data-stu-id="818d9-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="818d9-351">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-353">int</span><span class="sxs-lookup"><span data-stu-id="818d9-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-354">Taxa máxima de bits do destinatário.</span><span class="sxs-lookup"><span data-stu-id="818d9-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="818d9-355">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-357">int</span><span class="sxs-lookup"><span data-stu-id="818d9-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-358">Taxa média de bits para o destinatário.</span><span class="sxs-lookup"><span data-stu-id="818d9-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="818d9-359">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-361">int</span><span class="sxs-lookup"><span data-stu-id="818d9-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-362">Máximo de fluxos de vídeo para o receptor.</span><span class="sxs-lookup"><span data-stu-id="818d9-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="818d9-363">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-365">int</span><span class="sxs-lookup"><span data-stu-id="818d9-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-366">Fluxos de vídeo mínimos para o receptor.</span><span class="sxs-lookup"><span data-stu-id="818d9-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="818d9-367">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-369">int</span><span class="sxs-lookup"><span data-stu-id="818d9-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-370">Modo de vídeo (por exemplo, galeria ou único fluxo) para o destinatário.</span><span class="sxs-lookup"><span data-stu-id="818d9-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="818d9-371">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-372"><strong>À FEC PLR</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-373">float</span><span class="sxs-lookup"><span data-stu-id="818d9-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-374">Taxa de perda de pacote após a aplicação da correção de erro de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="818d9-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="818d9-375">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-376"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-377">float</span><span class="sxs-lookup"><span data-stu-id="818d9-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-378">Porcentagem de tempo que o sinalizador de recurso dinâmico estava ativo.</span><span class="sxs-lookup"><span data-stu-id="818d9-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="818d9-379">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-381">caractere (9)</span><span class="sxs-lookup"><span data-stu-id="818d9-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-382">Resolução mínima medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="818d9-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="818d9-383">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-385">float</span><span class="sxs-lookup"><span data-stu-id="818d9-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-386">Porcentagem da chamada abaixo do limite de baixa taxa de bits (70 quilobits por segundo).</span><span class="sxs-lookup"><span data-stu-id="818d9-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="818d9-387">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-388"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-389">float</span><span class="sxs-lookup"><span data-stu-id="818d9-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-390">Porcentagem da chamada abaixo do limite de baixa taxa de quadros (7,5 quadros por segundo, entrada).</span><span class="sxs-lookup"><span data-stu-id="818d9-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="818d9-391">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-392"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-393">float</span><span class="sxs-lookup"><span data-stu-id="818d9-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-394">Porcentagem da chamada ocorrida na resolução mais baixa.</span><span class="sxs-lookup"><span data-stu-id="818d9-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="818d9-395">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="818d9-396">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="818d9-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-398">float</span><span class="sxs-lookup"><span data-stu-id="818d9-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-399">Duração da chamada em segundos.</span><span class="sxs-lookup"><span data-stu-id="818d9-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="818d9-400">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="818d9-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="818d9-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="818d9-402">bit</span><span class="sxs-lookup"><span data-stu-id="818d9-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="818d9-403">Indica se os dados foram agregados de várias chamadas.</span><span class="sxs-lookup"><span data-stu-id="818d9-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="818d9-404">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="818d9-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

