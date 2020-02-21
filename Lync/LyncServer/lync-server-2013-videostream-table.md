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
ms.openlocfilehash: a313419ca4072fe4d1841ba66a9cb603671e6c56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="5e7cc-102">Tabela VideoStream no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e7cc-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e7cc-103">_**Última modificação do tópico:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="5e7cc-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="5e7cc-104">Cada registro representa um fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-104">Each record represents one video stream.</span></span> <span data-ttu-id="5e7cc-105">Uma linha de mídia de vídeo geralmente contém dois fluxos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e7cc-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5e7cc-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5e7cc-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5e7cc-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-111">datetime</span><span class="sxs-lookup"><span data-stu-id="5e7cc-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5e7cc-112">Primário</span><span class="sxs-lookup"><span data-stu-id="5e7cc-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5e7cc-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-115">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-115">int</span></span></p></td>
<td><p><span data-ttu-id="5e7cc-116">Primário</span><span class="sxs-lookup"><span data-stu-id="5e7cc-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="5e7cc-117">R referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="5e7cc-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5e7cc-120">Primário</span><span class="sxs-lookup"><span data-stu-id="5e7cc-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="5e7cc-121">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-122"><strong>Streamid</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-123">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-123">int</span></span></p></td>
<td><p><span data-ttu-id="5e7cc-124">Primário</span><span class="sxs-lookup"><span data-stu-id="5e7cc-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="5e7cc-125">Identificação exclusiva em uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-127">smallint</span><span class="sxs-lookup"><span data-stu-id="5e7cc-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="5e7cc-128">Externo, primário</span><span class="sxs-lookup"><span data-stu-id="5e7cc-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="5e7cc-129">Descrição da carga.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-129">Payload description.</span></span> <span data-ttu-id="5e7cc-130">Consulte a <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-132">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-133">Média de tremulação de rede a partir da estatística do protocolo RTCP.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-135">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-136">Tremulação máxima da rede durante a sessão de vídeo.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-137"><strong>Aproxima</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-138">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-139">Tempo de ida e volta de estatísticas RTCP.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-141">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-142">Tempo máximo de ida e volta para o fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-144">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="5e7cc-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-145">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-147">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="5e7cc-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-148">Perda máxima de pacotes observada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-150">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-151">Contagem de pacotes do stream de vídeo (Protocolo de Transporte em Tempo Real, RTP).</span><span class="sxs-lookup"><span data-stu-id="5e7cc-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-152"><strong>Mais largura de banda</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-153">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-154">Estimativas de largura de banda para o fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-156">caractere (9)</span><span class="sxs-lookup"><span data-stu-id="5e7cc-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-p103">Resolução de vídeo obtida através da multiplicação dos pixel de altura e de largura. Relatada como uma sequência de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-160">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-161">Taxa de transmissão do stream de vídeo.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-163">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="5e7cc-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-164">A taxa de quadros de vídeo recebida.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-166">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="5e7cc-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-167">A taxa de quadros de vídeo enviada.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-169">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-170">A taxa máxima de bits de vídeo durante a sessão de vídeo.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-172">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="5e7cc-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-173">A porcentagem do total de quadros de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-175">bits</span><span class="sxs-lookup"><span data-stu-id="5e7cc-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-176">Indisponível.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-178">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="5e7cc-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-179">A porcentagem do total de quadros de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="5e7cc-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-182">A porcentagem da chamada que estava na resolução de CIF (Common Interchange Format).</span><span class="sxs-lookup"><span data-stu-id="5e7cc-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="5e7cc-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-185">A porcentagem da chamada que estava na resolução VGA.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="5e7cc-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-188">A porcentagem da chamada que estava na resolução HD720.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="5e7cc-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-191">Porcentagem de duração da chamada sem queda de quadro.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="5e7cc-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-194">Porcentagem de duração da chamada com queda de quadro B.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="5e7cc-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-197">Porcentagem de duração da chamada com depósito de quadro BP.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="5e7cc-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-200">Porcentagem de duração da chamada com descarte de quadro remoção.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="5e7cc-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-203">Porcentagem de duração da chamada com descarte de quadro BPSP.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-204"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-205">bits</span><span class="sxs-lookup"><span data-stu-id="5e7cc-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-206">Dados de fluxo no lado do destinatário são recebidos.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-207"><strong>Saída</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-208">bits</span><span class="sxs-lookup"><span data-stu-id="5e7cc-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-209">Dados de fluxo no lado do remetente são recebidos.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-211">bits</span><span class="sxs-lookup"><span data-stu-id="5e7cc-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5e7cc-212">1 significa que a direção do fluxo é do chamador para o receptor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="5e7cc-213">0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-215">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-216">Indica a porcentagem de tempo em que a chamada estava em um estado de congestionamento de perda.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="5e7cc-217">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-219">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-220">Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada de pacotes de rede.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="5e7cc-221">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-223">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-224">Indica a porcentagem de tempo em que a chamada estava competindo por recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="5e7cc-225">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-227">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-228">Quantidade mínima de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="5e7cc-229">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-231">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-232">Quantidade máxima de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="5e7cc-233">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-235">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-236">O desvio padrão da estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="5e7cc-237">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-239">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-240">Quantidade média de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="5e7cc-241">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-243">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-244">Porcentagem da chamada em que o ponto de extremidade determinou que a conexão de rede não pôde suportar vídeo MultiView.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="5e7cc-245">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-247">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-p104">Quantidade total de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="5e7cc-250">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-252">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-p105">Quantidade média de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="5e7cc-255">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-257">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-p106">Quantidade máxima de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="5e7cc-260">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-262">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-p107">Total de ocorrências de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5e7cc-266">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-268">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-p108">Densidade total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5e7cc-272">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-274">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-p109">Duração total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5e7cc-278">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-280">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-p110">Total de ocorrências de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5e7cc-284">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-286">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-p111">Densidade total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5e7cc-290">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-292">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-p112">Duração total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5e7cc-296">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-298">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="5e7cc-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-299">Taxa de perda dos pacotes de vídeo.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="5e7cc-300">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-302">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-303">Valor médio da largura de banda alocada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="5e7cc-304">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-306">smallint</span><span class="sxs-lookup"><span data-stu-id="5e7cc-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="5e7cc-307">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="5e7cc-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e7cc-308">Tipo de codecs de vídeo usados pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="5e7cc-309">Consulte a <a href="lync-server-2013-codecdescription-table.md">tabela CodecDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="5e7cc-310">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-312">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-313">Largura da resolução usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="5e7cc-314">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-316">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-317">Altura da resolução usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="5e7cc-318">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-320">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-321">Taxa média de transmissão de quadros de vídeo usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="5e7cc-322">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-324">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-325">Taxa de bits máxima para o remetente.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="5e7cc-326">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-328">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-329">Taxa de bits média para o remetente.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-331">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-332">Número máximo de fluxos de vídeo usados pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="5e7cc-333">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-335">smallint</span><span class="sxs-lookup"><span data-stu-id="5e7cc-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="5e7cc-336">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="5e7cc-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e7cc-337">Códigos de vídeo usados pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-337">Video codes used by the receiver.</span></span> <span data-ttu-id="5e7cc-338">Consulte a <a href="lync-server-2013-codecdescription-table.md">tabela CodecDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="5e7cc-339">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-341">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-342">Largura da resolução usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="5e7cc-343">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-345">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-346">Altura da resolução usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="5e7cc-347">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-349">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-350">Taxa média de quadros de vídeo usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="5e7cc-351">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-353">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-354">Taxa de bits máxima para o receptor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="5e7cc-355">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-357">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-358">Taxa de bits média para o receptor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="5e7cc-359">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-361">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-362">Máximo de fluxos de vídeo para o receptor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="5e7cc-363">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-365">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-366">Fluxos de vídeo mínimos para o receptor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="5e7cc-367">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-369">int</span><span class="sxs-lookup"><span data-stu-id="5e7cc-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-370">Modo de vídeo (por exemplo, galeria ou fluxo único) para o receptor.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="5e7cc-371">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-373">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-374">Taxa de perda de pacote após a correção de erro encaminhar ter sido aplicada.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="5e7cc-375">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-377">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-378">Porcentagem de tempo em que o sinalizador de recurso dinâmico estava ativo.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="5e7cc-379">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-381">caractere (9)</span><span class="sxs-lookup"><span data-stu-id="5e7cc-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-382">Resolução mínima medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="5e7cc-383">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-385">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-386">Porcentagem da chamada abaixo do limite de taxa de bits baixa (70 kilobits por segundo).</span><span class="sxs-lookup"><span data-stu-id="5e7cc-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="5e7cc-387">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-389">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-390">Porcentagem da chamada abaixo do limite de baixa taxa de quadros (7,5 quadros por segundo, entrada).</span><span class="sxs-lookup"><span data-stu-id="5e7cc-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="5e7cc-391">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-393">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-394">Porcentagem da chamada que ocorreu na resolução mais baixa.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="5e7cc-395">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="5e7cc-396">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e7cc-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-398">float</span><span class="sxs-lookup"><span data-stu-id="5e7cc-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-399">Duração da chamada em segundos.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="5e7cc-400">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e7cc-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="5e7cc-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="5e7cc-402">bits</span><span class="sxs-lookup"><span data-stu-id="5e7cc-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e7cc-403">Indica se os dados foram agregados a várias chamadas.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="5e7cc-404">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e7cc-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

