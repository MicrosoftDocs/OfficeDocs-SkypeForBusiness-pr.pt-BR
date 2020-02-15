---
title: 'Lync Server 2013: tabela VideoStream'
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
ms.openlocfilehash: 00abc61fc7ba83b94f3228de91eb9fa6810fc93c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="7b722-102">Tabela VideoStream no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b722-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b722-103">_**Última modificação do tópico:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="7b722-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="7b722-104">Cada registro representa um fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="7b722-104">Each record represents one video stream.</span></span> <span data-ttu-id="7b722-105">Uma linha de mídia de vídeo geralmente contém dois fluxos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="7b722-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b722-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7b722-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7b722-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7b722-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b722-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-111">datetime</span><span class="sxs-lookup"><span data-stu-id="7b722-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7b722-112">Primário</span><span class="sxs-lookup"><span data-stu-id="7b722-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7b722-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7b722-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-115">int</span><span class="sxs-lookup"><span data-stu-id="7b722-115">int</span></span></p></td>
<td><p><span data-ttu-id="7b722-116">Primário</span><span class="sxs-lookup"><span data-stu-id="7b722-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="7b722-117">R referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7b722-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="7b722-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7b722-120">Primário</span><span class="sxs-lookup"><span data-stu-id="7b722-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="7b722-121">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="7b722-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-122"><strong>Streamid</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-123">int</span><span class="sxs-lookup"><span data-stu-id="7b722-123">int</span></span></p></td>
<td><p><span data-ttu-id="7b722-124">Primário</span><span class="sxs-lookup"><span data-stu-id="7b722-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="7b722-125">Identificação exclusiva em uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="7b722-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-127">smallint</span><span class="sxs-lookup"><span data-stu-id="7b722-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="7b722-128">Externo, primário</span><span class="sxs-lookup"><span data-stu-id="7b722-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="7b722-129">Descrição da carga.</span><span class="sxs-lookup"><span data-stu-id="7b722-129">Payload description.</span></span> <span data-ttu-id="7b722-130">Consulte a <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7b722-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-132">int</span><span class="sxs-lookup"><span data-stu-id="7b722-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-133">Média de tremulação de rede a partir da estatística do protocolo RTCP.</span><span class="sxs-lookup"><span data-stu-id="7b722-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-135">int</span><span class="sxs-lookup"><span data-stu-id="7b722-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-136">Tremulação máxima da rede durante a sessão de vídeo.</span><span class="sxs-lookup"><span data-stu-id="7b722-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-137"><strong>Aproxima</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-138">int</span><span class="sxs-lookup"><span data-stu-id="7b722-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-139">Tempo de ida e volta de estatísticas RTCP.</span><span class="sxs-lookup"><span data-stu-id="7b722-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-141">int</span><span class="sxs-lookup"><span data-stu-id="7b722-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-142">Tempo máximo de ida e volta para o fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="7b722-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-144">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="7b722-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-145">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="7b722-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-147">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="7b722-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-148">Perda máxima de pacotes observada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="7b722-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-150">int</span><span class="sxs-lookup"><span data-stu-id="7b722-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-151">Contagem de pacotes do stream de vídeo (Protocolo de Transporte em Tempo Real, RTP).</span><span class="sxs-lookup"><span data-stu-id="7b722-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-152"><strong>Mais largura de banda</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-153">int</span><span class="sxs-lookup"><span data-stu-id="7b722-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-154">Estimativas de largura de banda para o fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="7b722-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-156">caractere (9)</span><span class="sxs-lookup"><span data-stu-id="7b722-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-p103">Resolução de vídeo obtida através da multiplicação dos pixel de altura e de largura. Relatada como uma sequência de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7b722-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-160">int</span><span class="sxs-lookup"><span data-stu-id="7b722-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-161">Taxa de transmissão do stream de vídeo.</span><span class="sxs-lookup"><span data-stu-id="7b722-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-163">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7b722-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-164">A taxa de quadros de vídeo recebida.</span><span class="sxs-lookup"><span data-stu-id="7b722-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-166">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7b722-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-167">A taxa de quadros de vídeo enviada.</span><span class="sxs-lookup"><span data-stu-id="7b722-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-169">int</span><span class="sxs-lookup"><span data-stu-id="7b722-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-170">A taxa máxima de bits de vídeo durante a sessão de vídeo.</span><span class="sxs-lookup"><span data-stu-id="7b722-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-172">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7b722-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-173">A porcentagem do total de quadros de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="7b722-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-175">bits</span><span class="sxs-lookup"><span data-stu-id="7b722-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-176">Indisponível.</span><span class="sxs-lookup"><span data-stu-id="7b722-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-178">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7b722-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-179">A porcentagem do total de quadros de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="7b722-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="7b722-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-182">A porcentagem da chamada que estava na resolução de CIF (Common Interchange Format).</span><span class="sxs-lookup"><span data-stu-id="7b722-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="7b722-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-185">A porcentagem da chamada que estava na resolução VGA.</span><span class="sxs-lookup"><span data-stu-id="7b722-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="7b722-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-188">A porcentagem da chamada que estava na resolução HD720.</span><span class="sxs-lookup"><span data-stu-id="7b722-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="7b722-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-191">Porcentagem de duração da chamada sem queda de quadro.</span><span class="sxs-lookup"><span data-stu-id="7b722-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="7b722-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-194">Porcentagem de duração da chamada com queda de quadro B.</span><span class="sxs-lookup"><span data-stu-id="7b722-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="7b722-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-197">Porcentagem de duração da chamada com depósito de quadro BP.</span><span class="sxs-lookup"><span data-stu-id="7b722-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="7b722-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-200">Porcentagem de duração da chamada com descarte de quadro remoção.</span><span class="sxs-lookup"><span data-stu-id="7b722-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="7b722-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-203">Porcentagem de duração da chamada com descarte de quadro BPSP.</span><span class="sxs-lookup"><span data-stu-id="7b722-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-204"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-205">bits</span><span class="sxs-lookup"><span data-stu-id="7b722-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-206">Dados de fluxo no lado do destinatário são recebidos.</span><span class="sxs-lookup"><span data-stu-id="7b722-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-207"><strong>Saída</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-208">bits</span><span class="sxs-lookup"><span data-stu-id="7b722-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-209">Dados de fluxo no lado do remetente são recebidos.</span><span class="sxs-lookup"><span data-stu-id="7b722-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-211">bits</span><span class="sxs-lookup"><span data-stu-id="7b722-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7b722-212">1 significa que a direção do fluxo é do chamador para o receptor.</span><span class="sxs-lookup"><span data-stu-id="7b722-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="7b722-213">0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="7b722-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-215">float</span><span class="sxs-lookup"><span data-stu-id="7b722-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-216">Indica a porcentagem de tempo em que a chamada estava em um estado de congestionamento de perda.</span><span class="sxs-lookup"><span data-stu-id="7b722-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="7b722-217">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-219">float</span><span class="sxs-lookup"><span data-stu-id="7b722-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-220">Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada de pacotes de rede.</span><span class="sxs-lookup"><span data-stu-id="7b722-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="7b722-221">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-223">float</span><span class="sxs-lookup"><span data-stu-id="7b722-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-224">Indica a porcentagem de tempo em que a chamada estava competindo por recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="7b722-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="7b722-225">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-227">int</span><span class="sxs-lookup"><span data-stu-id="7b722-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-228">Quantidade mínima de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="7b722-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7b722-229">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-231">int</span><span class="sxs-lookup"><span data-stu-id="7b722-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-232">Quantidade máxima de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="7b722-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7b722-233">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-235">int</span><span class="sxs-lookup"><span data-stu-id="7b722-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-236">O desvio padrão da estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="7b722-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7b722-237">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-239">int</span><span class="sxs-lookup"><span data-stu-id="7b722-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-240">Quantidade média de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="7b722-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7b722-241">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-243">float</span><span class="sxs-lookup"><span data-stu-id="7b722-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-244">Porcentagem da chamada em que o ponto de extremidade determinou que a conexão de rede não pôde suportar vídeo MultiView.</span><span class="sxs-lookup"><span data-stu-id="7b722-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="7b722-245">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-247">float</span><span class="sxs-lookup"><span data-stu-id="7b722-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-p104">Quantidade total de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="7b722-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7b722-250">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-252">float</span><span class="sxs-lookup"><span data-stu-id="7b722-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-p105">Quantidade média de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="7b722-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7b722-255">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-257">float</span><span class="sxs-lookup"><span data-stu-id="7b722-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-p106">Quantidade máxima de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="7b722-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7b722-260">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-262">int</span><span class="sxs-lookup"><span data-stu-id="7b722-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-p107">Total de ocorrências de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="7b722-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7b722-266">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-268">int</span><span class="sxs-lookup"><span data-stu-id="7b722-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-p108">Densidade total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="7b722-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7b722-272">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-274">float</span><span class="sxs-lookup"><span data-stu-id="7b722-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-p109">Duração total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="7b722-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7b722-278">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-280">int</span><span class="sxs-lookup"><span data-stu-id="7b722-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-p110">Total de ocorrências de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="7b722-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7b722-284">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-286">float</span><span class="sxs-lookup"><span data-stu-id="7b722-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-p111">Densidade total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="7b722-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7b722-290">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-292">float</span><span class="sxs-lookup"><span data-stu-id="7b722-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-p112">Duração total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="7b722-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7b722-296">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-298">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7b722-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-299">Taxa de perda dos pacotes de vídeo.</span><span class="sxs-lookup"><span data-stu-id="7b722-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="7b722-300">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-302">int</span><span class="sxs-lookup"><span data-stu-id="7b722-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-303">Valor médio da largura de banda alocada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="7b722-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="7b722-304">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-306">smallint</span><span class="sxs-lookup"><span data-stu-id="7b722-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="7b722-307">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="7b722-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7b722-308">Tipo de codecs de vídeo usados pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="7b722-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="7b722-309">Consulte a <a href="lync-server-2013-codecdescription-table.md">tabela CodecDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7b722-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="7b722-310">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-312">int</span><span class="sxs-lookup"><span data-stu-id="7b722-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-313">Largura da resolução usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="7b722-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="7b722-314">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-316">int</span><span class="sxs-lookup"><span data-stu-id="7b722-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-317">Altura da resolução usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="7b722-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="7b722-318">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-320">float</span><span class="sxs-lookup"><span data-stu-id="7b722-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-321">Taxa média de transmissão de quadros de vídeo usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="7b722-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="7b722-322">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-324">int</span><span class="sxs-lookup"><span data-stu-id="7b722-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-325">Taxa de bits máxima para o remetente.</span><span class="sxs-lookup"><span data-stu-id="7b722-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="7b722-326">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-328">int</span><span class="sxs-lookup"><span data-stu-id="7b722-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-329">Taxa de bits média para o remetente.</span><span class="sxs-lookup"><span data-stu-id="7b722-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-331">int</span><span class="sxs-lookup"><span data-stu-id="7b722-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-332">Número máximo de fluxos de vídeo usados pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="7b722-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="7b722-333">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-335">smallint</span><span class="sxs-lookup"><span data-stu-id="7b722-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="7b722-336">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="7b722-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7b722-337">Códigos de vídeo usados pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="7b722-337">Video codes used by the receiver.</span></span> <span data-ttu-id="7b722-338">Consulte a <a href="lync-server-2013-codecdescription-table.md">tabela CodecDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7b722-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="7b722-339">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-341">int</span><span class="sxs-lookup"><span data-stu-id="7b722-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-342">Largura da resolução usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="7b722-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="7b722-343">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-345">int</span><span class="sxs-lookup"><span data-stu-id="7b722-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-346">Altura da resolução usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="7b722-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="7b722-347">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-349">float</span><span class="sxs-lookup"><span data-stu-id="7b722-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-350">Taxa média de quadros de vídeo usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="7b722-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="7b722-351">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-353">int</span><span class="sxs-lookup"><span data-stu-id="7b722-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-354">Taxa de bits máxima para o receptor.</span><span class="sxs-lookup"><span data-stu-id="7b722-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="7b722-355">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-357">int</span><span class="sxs-lookup"><span data-stu-id="7b722-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-358">Taxa de bits média para o receptor.</span><span class="sxs-lookup"><span data-stu-id="7b722-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="7b722-359">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-361">int</span><span class="sxs-lookup"><span data-stu-id="7b722-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-362">Máximo de fluxos de vídeo para o receptor.</span><span class="sxs-lookup"><span data-stu-id="7b722-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="7b722-363">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-365">int</span><span class="sxs-lookup"><span data-stu-id="7b722-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-366">Fluxos de vídeo mínimos para o receptor.</span><span class="sxs-lookup"><span data-stu-id="7b722-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="7b722-367">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-369">int</span><span class="sxs-lookup"><span data-stu-id="7b722-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-370">Modo de vídeo (por exemplo, galeria ou fluxo único) para o receptor.</span><span class="sxs-lookup"><span data-stu-id="7b722-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="7b722-371">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-373">float</span><span class="sxs-lookup"><span data-stu-id="7b722-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-374">Taxa de perda de pacote após a correção de erro encaminhar ter sido aplicada.</span><span class="sxs-lookup"><span data-stu-id="7b722-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="7b722-375">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-377">float</span><span class="sxs-lookup"><span data-stu-id="7b722-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-378">Porcentagem de tempo em que o sinalizador de recurso dinâmico estava ativo.</span><span class="sxs-lookup"><span data-stu-id="7b722-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="7b722-379">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-381">caractere (9)</span><span class="sxs-lookup"><span data-stu-id="7b722-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-382">Resolução mínima medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="7b722-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="7b722-383">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-385">float</span><span class="sxs-lookup"><span data-stu-id="7b722-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-386">Porcentagem da chamada abaixo do limite de taxa de bits baixa (70 kilobits por segundo).</span><span class="sxs-lookup"><span data-stu-id="7b722-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="7b722-387">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-389">float</span><span class="sxs-lookup"><span data-stu-id="7b722-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-390">Porcentagem da chamada abaixo do limite de baixa taxa de quadros (7,5 quadros por segundo, entrada).</span><span class="sxs-lookup"><span data-stu-id="7b722-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="7b722-391">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-393">float</span><span class="sxs-lookup"><span data-stu-id="7b722-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-394">Porcentagem da chamada que ocorreu na resolução mais baixa.</span><span class="sxs-lookup"><span data-stu-id="7b722-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="7b722-395">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="7b722-396">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b722-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-398">float</span><span class="sxs-lookup"><span data-stu-id="7b722-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-399">Duração da chamada em segundos.</span><span class="sxs-lookup"><span data-stu-id="7b722-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="7b722-400">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b722-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="7b722-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="7b722-402">bits</span><span class="sxs-lookup"><span data-stu-id="7b722-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7b722-403">Indica se os dados foram agregados a várias chamadas.</span><span class="sxs-lookup"><span data-stu-id="7b722-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="7b722-404">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b722-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

