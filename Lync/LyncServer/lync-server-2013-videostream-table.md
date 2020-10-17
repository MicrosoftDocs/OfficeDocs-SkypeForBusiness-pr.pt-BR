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
ms.openlocfilehash: ef5c417ff391bb3ec5954cf12d00f6de3d2e6d9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518558"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="a4e38-102">Tabela VideoStream no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4e38-102">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4e38-103">_**Última modificação do tópico:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="a4e38-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="a4e38-104">Cada registro representa um fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="a4e38-104">Each record represents one video stream.</span></span> <span data-ttu-id="a4e38-105">Uma linha de mídia de vídeo geralmente contém dois fluxos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="a4e38-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4e38-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a4e38-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a4e38-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a4e38-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a4e38-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a4e38-112">Primário</span><span class="sxs-lookup"><span data-stu-id="a4e38-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a4e38-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a4e38-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-115">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-115">int</span></span></p></td>
<td><p><span data-ttu-id="a4e38-116">Primário</span><span class="sxs-lookup"><span data-stu-id="a4e38-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="a4e38-117">R referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a4e38-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="a4e38-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a4e38-120">Primário</span><span class="sxs-lookup"><span data-stu-id="a4e38-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="a4e38-121">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a4e38-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-122"><strong>Streamid</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-123">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-123">int</span></span></p></td>
<td><p><span data-ttu-id="a4e38-124">Primário</span><span class="sxs-lookup"><span data-stu-id="a4e38-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="a4e38-125">Identificação exclusiva em uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="a4e38-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-127">smallint</span><span class="sxs-lookup"><span data-stu-id="a4e38-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="a4e38-128">Externo, primário</span><span class="sxs-lookup"><span data-stu-id="a4e38-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="a4e38-129">Descrição da carga.</span><span class="sxs-lookup"><span data-stu-id="a4e38-129">Payload description.</span></span> <span data-ttu-id="a4e38-130">Consulte a <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a4e38-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-132">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-133">Média de tremulação de rede a partir da estatística do protocolo RTCP.</span><span class="sxs-lookup"><span data-stu-id="a4e38-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-135">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-136">Tremulação máxima da rede durante a sessão de vídeo.</span><span class="sxs-lookup"><span data-stu-id="a4e38-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-137"><strong>Aproxima</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-138">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-139">Tempo de ida e volta de estatísticas RTCP.</span><span class="sxs-lookup"><span data-stu-id="a4e38-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-141">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-142">Tempo máximo de ida e volta para o fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="a4e38-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-144">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="a4e38-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-145">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a4e38-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-147">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="a4e38-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-148">Perda máxima de pacotes observada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a4e38-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-150">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-151">Contagem de pacotes do stream de vídeo (Protocolo de Transporte em Tempo Real, RTP).</span><span class="sxs-lookup"><span data-stu-id="a4e38-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-152"><strong>Mais largura de banda</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-153">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-154">Estimativas de largura de banda para o fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="a4e38-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-156">caractere (9)</span><span class="sxs-lookup"><span data-stu-id="a4e38-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-p103">Resolução de vídeo obtida através da multiplicação dos pixel de altura e de largura. Relatada como uma sequência de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a4e38-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-160">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-161">Taxa de transmissão do stream de vídeo.</span><span class="sxs-lookup"><span data-stu-id="a4e38-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-163">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a4e38-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-164">A taxa de quadros de vídeo recebida.</span><span class="sxs-lookup"><span data-stu-id="a4e38-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-166">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a4e38-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-167">A taxa de quadros de vídeo enviada.</span><span class="sxs-lookup"><span data-stu-id="a4e38-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-169">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-170">A taxa máxima de bits de vídeo durante a sessão de vídeo.</span><span class="sxs-lookup"><span data-stu-id="a4e38-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-172">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a4e38-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-173">A porcentagem do total de quadros de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="a4e38-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-175">bits</span><span class="sxs-lookup"><span data-stu-id="a4e38-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-176">Indisponível.</span><span class="sxs-lookup"><span data-stu-id="a4e38-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-178">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a4e38-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-179">A porcentagem do total de quadros de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="a4e38-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="a4e38-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-182">A porcentagem da chamada que estava na resolução de CIF (Common Interchange Format).</span><span class="sxs-lookup"><span data-stu-id="a4e38-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="a4e38-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-185">A porcentagem da chamada que estava na resolução VGA.</span><span class="sxs-lookup"><span data-stu-id="a4e38-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="a4e38-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-188">A porcentagem da chamada que estava na resolução HD720.</span><span class="sxs-lookup"><span data-stu-id="a4e38-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="a4e38-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-191">Porcentagem de duração da chamada sem queda de quadro.</span><span class="sxs-lookup"><span data-stu-id="a4e38-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="a4e38-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-194">Porcentagem de duração da chamada com queda de quadro B.</span><span class="sxs-lookup"><span data-stu-id="a4e38-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="a4e38-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-197">Porcentagem de duração da chamada com depósito de quadro BP.</span><span class="sxs-lookup"><span data-stu-id="a4e38-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="a4e38-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-200">Porcentagem de duração da chamada com descarte de quadro remoção.</span><span class="sxs-lookup"><span data-stu-id="a4e38-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="a4e38-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-203">Porcentagem de duração da chamada com descarte de quadro BPSP.</span><span class="sxs-lookup"><span data-stu-id="a4e38-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-204"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-205">bits</span><span class="sxs-lookup"><span data-stu-id="a4e38-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-206">Dados de fluxo no lado do destinatário são recebidos.</span><span class="sxs-lookup"><span data-stu-id="a4e38-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-207"><strong>Saída</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-208">bits</span><span class="sxs-lookup"><span data-stu-id="a4e38-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-209">Dados de fluxo no lado do remetente são recebidos.</span><span class="sxs-lookup"><span data-stu-id="a4e38-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-211">bits</span><span class="sxs-lookup"><span data-stu-id="a4e38-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a4e38-212">1 significa que a direção do fluxo é do chamador para o receptor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="a4e38-213">0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="a4e38-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-215">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-216">Indica a porcentagem de tempo em que a chamada estava em um estado de congestionamento de perda.</span><span class="sxs-lookup"><span data-stu-id="a4e38-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="a4e38-217">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-219">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-220">Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada de pacotes de rede.</span><span class="sxs-lookup"><span data-stu-id="a4e38-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="a4e38-221">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-223">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-224">Indica a porcentagem de tempo em que a chamada estava competindo por recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="a4e38-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="a4e38-225">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-227">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-228">Quantidade mínima de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a4e38-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a4e38-229">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-231">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-232">Quantidade máxima de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a4e38-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a4e38-233">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-235">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-236">O desvio padrão da estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a4e38-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a4e38-237">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-239">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-240">Quantidade média de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a4e38-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a4e38-241">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-243">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-244">Porcentagem da chamada em que o ponto de extremidade determinou que a conexão de rede não pôde suportar vídeo MultiView.</span><span class="sxs-lookup"><span data-stu-id="a4e38-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="a4e38-245">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-247">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-p104">Quantidade total de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="a4e38-250">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-252">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-p105">Quantidade média de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="a4e38-255">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-257">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-p106">Quantidade máxima de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="a4e38-260">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-262">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-p107">Total de ocorrências de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a4e38-266">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-268">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-p108">Densidade total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a4e38-272">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-274">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-p109">Duração total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a4e38-278">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-280">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-p110">Total de ocorrências de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a4e38-284">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-286">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-p111">Densidade total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a4e38-290">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-292">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-p112">Duração total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a4e38-296">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-298">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a4e38-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-299">Taxa de perda dos pacotes de vídeo.</span><span class="sxs-lookup"><span data-stu-id="a4e38-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="a4e38-300">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-302">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-303">Valor médio da largura de banda alocada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="a4e38-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="a4e38-304">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-306">smallint</span><span class="sxs-lookup"><span data-stu-id="a4e38-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="a4e38-307">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="a4e38-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a4e38-308">Tipo de codecs de vídeo usados pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="a4e38-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="a4e38-309">Consulte a <a href="lync-server-2013-codecdescription-table.md">tabela CodecDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a4e38-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="a4e38-310">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-312">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-313">Largura da resolução usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="a4e38-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="a4e38-314">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-316">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-317">Altura da resolução usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="a4e38-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="a4e38-318">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-320">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-321">Taxa média de transmissão de quadros de vídeo usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="a4e38-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="a4e38-322">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-324">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-325">Taxa de bits máxima para o remetente.</span><span class="sxs-lookup"><span data-stu-id="a4e38-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="a4e38-326">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-328">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-329">Taxa de bits média para o remetente.</span><span class="sxs-lookup"><span data-stu-id="a4e38-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-331">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-332">Número máximo de fluxos de vídeo usados pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="a4e38-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="a4e38-333">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-335">smallint</span><span class="sxs-lookup"><span data-stu-id="a4e38-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="a4e38-336">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="a4e38-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a4e38-337">Códigos de vídeo usados pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-337">Video codes used by the receiver.</span></span> <span data-ttu-id="a4e38-338">Consulte a <a href="lync-server-2013-codecdescription-table.md">tabela CodecDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a4e38-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="a4e38-339">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-341">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-342">Largura da resolução usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="a4e38-343">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-345">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-346">Altura da resolução usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="a4e38-347">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-349">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-350">Taxa média de quadros de vídeo usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="a4e38-351">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-353">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-354">Taxa de bits máxima para o receptor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="a4e38-355">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-357">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-358">Taxa de bits média para o receptor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="a4e38-359">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-361">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-362">Máximo de fluxos de vídeo para o receptor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="a4e38-363">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-365">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-366">Fluxos de vídeo mínimos para o receptor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="a4e38-367">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-369">int</span><span class="sxs-lookup"><span data-stu-id="a4e38-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-370">Modo de vídeo (por exemplo, galeria ou fluxo único) para o receptor.</span><span class="sxs-lookup"><span data-stu-id="a4e38-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="a4e38-371">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-373">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-374">Taxa de perda de pacote após a correção de erro encaminhar ter sido aplicada.</span><span class="sxs-lookup"><span data-stu-id="a4e38-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="a4e38-375">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-377">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-378">Porcentagem de tempo em que o sinalizador de recurso dinâmico estava ativo.</span><span class="sxs-lookup"><span data-stu-id="a4e38-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="a4e38-379">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-381">caractere (9)</span><span class="sxs-lookup"><span data-stu-id="a4e38-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-382">Resolução mínima medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="a4e38-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="a4e38-383">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-385">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-386">Porcentagem da chamada abaixo do limite de taxa de bits baixa (70 kilobits por segundo).</span><span class="sxs-lookup"><span data-stu-id="a4e38-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="a4e38-387">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-389">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-390">Porcentagem da chamada abaixo do limite de baixa taxa de quadros (7,5 quadros por segundo, entrada).</span><span class="sxs-lookup"><span data-stu-id="a4e38-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="a4e38-391">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-393">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-394">Porcentagem da chamada que ocorreu na resolução mais baixa.</span><span class="sxs-lookup"><span data-stu-id="a4e38-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="a4e38-395">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="a4e38-396">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4e38-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-398">flutuação</span><span class="sxs-lookup"><span data-stu-id="a4e38-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-399">Duração da chamada em segundos.</span><span class="sxs-lookup"><span data-stu-id="a4e38-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="a4e38-400">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4e38-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="a4e38-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="a4e38-402">bits</span><span class="sxs-lookup"><span data-stu-id="a4e38-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4e38-403">Indica se os dados foram agregados a várias chamadas.</span><span class="sxs-lookup"><span data-stu-id="a4e38-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="a4e38-404">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a4e38-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

