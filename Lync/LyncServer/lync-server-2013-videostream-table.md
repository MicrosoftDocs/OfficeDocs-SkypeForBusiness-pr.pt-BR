---
title: 'Lync Server 2013: tabela VideoStream'
description: 'Lync Server 2013: tabela VideoStream.'
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
ms.openlocfilehash: 0d741478e1f6290685181bff471f143e41ce9ca1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567987"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="e123e-103">Tabela VideoStream no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e123e-103">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e123e-104">_**Última modificação do tópico:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="e123e-104">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="e123e-105">Cada registro representa um fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e123e-105">Each record represents one video stream.</span></span> <span data-ttu-id="e123e-106">Uma linha de mídia de vídeo geralmente contém dois fluxos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e123e-106">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e123e-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e123e-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e123e-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e123e-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e123e-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e123e-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e123e-113">Primário</span><span class="sxs-lookup"><span data-stu-id="e123e-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e123e-114">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e123e-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-116">int</span><span class="sxs-lookup"><span data-stu-id="e123e-116">int</span></span></p></td>
<td><p><span data-ttu-id="e123e-117">Primário</span><span class="sxs-lookup"><span data-stu-id="e123e-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="e123e-118">R referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e123e-118">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="e123e-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e123e-121">Primário</span><span class="sxs-lookup"><span data-stu-id="e123e-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="e123e-122">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e123e-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-123"><strong>Streamid</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-124">int</span><span class="sxs-lookup"><span data-stu-id="e123e-124">int</span></span></p></td>
<td><p><span data-ttu-id="e123e-125">Primário</span><span class="sxs-lookup"><span data-stu-id="e123e-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="e123e-126">Identificação exclusiva em uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e123e-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-127"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-127"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-128">smallint</span><span class="sxs-lookup"><span data-stu-id="e123e-128">smallint</span></span></p></td>
<td><p><span data-ttu-id="e123e-129">Externo, primário</span><span class="sxs-lookup"><span data-stu-id="e123e-129">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="e123e-130">Descrição da carga.</span><span class="sxs-lookup"><span data-stu-id="e123e-130">Payload description.</span></span> <span data-ttu-id="e123e-131">Consulte a <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e123e-131">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-133">int</span><span class="sxs-lookup"><span data-stu-id="e123e-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-134">Média de tremulação de rede a partir da estatística do protocolo RTCP.</span><span class="sxs-lookup"><span data-stu-id="e123e-134">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-136">int</span><span class="sxs-lookup"><span data-stu-id="e123e-136">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-137">Tremulação máxima da rede durante a sessão de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e123e-137">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-138"><strong>Aproxima</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-138"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-139">int</span><span class="sxs-lookup"><span data-stu-id="e123e-139">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-140">Tempo de ida e volta de estatísticas RTCP.</span><span class="sxs-lookup"><span data-stu-id="e123e-140">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-141"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-141"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-142">int</span><span class="sxs-lookup"><span data-stu-id="e123e-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-143">Tempo máximo de ida e volta para o fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e123e-143">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-144"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-144"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-145">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="e123e-145">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-146">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="e123e-146">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-147"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-147"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-148">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="e123e-148">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-149">Perda máxima de pacotes observada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="e123e-149">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-151">int</span><span class="sxs-lookup"><span data-stu-id="e123e-151">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-152">Contagem de pacotes do stream de vídeo (Protocolo de Transporte em Tempo Real, RTP).</span><span class="sxs-lookup"><span data-stu-id="e123e-152">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-153"><strong>Mais largura de banda</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-154">int</span><span class="sxs-lookup"><span data-stu-id="e123e-154">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-155">Estimativas de largura de banda para o fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e123e-155">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-156"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-156"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-157">caractere (9)</span><span class="sxs-lookup"><span data-stu-id="e123e-157">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-p103">Resolução de vídeo obtida através da multiplicação dos pixel de altura e de largura. Relatada como uma sequência de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e123e-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-160"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-160"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-161">int</span><span class="sxs-lookup"><span data-stu-id="e123e-161">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-162">Taxa de transmissão do stream de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e123e-162">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-163"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-163"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-164">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e123e-164">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-165">A taxa de quadros de vídeo recebida.</span><span class="sxs-lookup"><span data-stu-id="e123e-165">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-166"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-166"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-167">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e123e-167">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-168">A taxa de quadros de vídeo enviada.</span><span class="sxs-lookup"><span data-stu-id="e123e-168">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-169"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-169"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-170">int</span><span class="sxs-lookup"><span data-stu-id="e123e-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-171">A taxa máxima de bits de vídeo durante a sessão de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e123e-171">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-172"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-172"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-173">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e123e-173">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-174">A porcentagem do total de quadros de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="e123e-174">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-175"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-175"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-176">bits</span><span class="sxs-lookup"><span data-stu-id="e123e-176">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-177">Indisponível.</span><span class="sxs-lookup"><span data-stu-id="e123e-177">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-179">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e123e-179">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-180">A porcentagem do total de quadros de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="e123e-180">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-181"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-181"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-182">tinyint</span><span class="sxs-lookup"><span data-stu-id="e123e-182">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-183">A porcentagem da chamada que estava na resolução de CIF (Common Interchange Format).</span><span class="sxs-lookup"><span data-stu-id="e123e-183">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-184"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-184"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-185">tinyint</span><span class="sxs-lookup"><span data-stu-id="e123e-185">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-186">A porcentagem da chamada que estava na resolução VGA.</span><span class="sxs-lookup"><span data-stu-id="e123e-186">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-187"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-187"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="e123e-188">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-189">A porcentagem da chamada que estava na resolução HD720.</span><span class="sxs-lookup"><span data-stu-id="e123e-189">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-190"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-190"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="e123e-191">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-192">Porcentagem de duração da chamada sem queda de quadro.</span><span class="sxs-lookup"><span data-stu-id="e123e-192">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-193"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-193"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-194">tinyint</span><span class="sxs-lookup"><span data-stu-id="e123e-194">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-195">Porcentagem de duração da chamada com queda de quadro B.</span><span class="sxs-lookup"><span data-stu-id="e123e-195">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-196"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-196"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-197">tinyint</span><span class="sxs-lookup"><span data-stu-id="e123e-197">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-198">Porcentagem de duração da chamada com depósito de quadro BP.</span><span class="sxs-lookup"><span data-stu-id="e123e-198">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-199"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-199"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="e123e-200">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-201">Porcentagem de duração da chamada com descarte de quadro remoção.</span><span class="sxs-lookup"><span data-stu-id="e123e-201">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-202"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-202"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="e123e-203">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-204">Porcentagem de duração da chamada com descarte de quadro BPSP.</span><span class="sxs-lookup"><span data-stu-id="e123e-204">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-205"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-205"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-206">bits</span><span class="sxs-lookup"><span data-stu-id="e123e-206">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-207">Dados de fluxo no lado do destinatário são recebidos.</span><span class="sxs-lookup"><span data-stu-id="e123e-207">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-208"><strong>Saída</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-208"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-209">bits</span><span class="sxs-lookup"><span data-stu-id="e123e-209">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-210">Dados de fluxo no lado do remetente são recebidos.</span><span class="sxs-lookup"><span data-stu-id="e123e-210">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-211"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-211"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-212">bits</span><span class="sxs-lookup"><span data-stu-id="e123e-212">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e123e-213">1 significa que a direção do fluxo é do chamador para o receptor.</span><span class="sxs-lookup"><span data-stu-id="e123e-213">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="e123e-214">0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="e123e-214">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-215"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-215"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-216">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-216">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-217">Indica a porcentagem de tempo em que a chamada estava em um estado de congestionamento de perda.</span><span class="sxs-lookup"><span data-stu-id="e123e-217">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="e123e-218">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-218">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-219"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-219"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-220">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-220">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-221">Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada de pacotes de rede.</span><span class="sxs-lookup"><span data-stu-id="e123e-221">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="e123e-222">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-222">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-223"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-223"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-224">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-224">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-225">Indica a porcentagem de tempo em que a chamada estava competindo por recursos de rede.</span><span class="sxs-lookup"><span data-stu-id="e123e-225">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="e123e-226">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-227"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-227"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-228">int</span><span class="sxs-lookup"><span data-stu-id="e123e-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-229">Quantidade mínima de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="e123e-229">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="e123e-230">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-231"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-231"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-232">int</span><span class="sxs-lookup"><span data-stu-id="e123e-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-233">Quantidade máxima de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="e123e-233">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="e123e-234">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-235"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-235"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-236">int</span><span class="sxs-lookup"><span data-stu-id="e123e-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-237">O desvio padrão da estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="e123e-237">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="e123e-238">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-239"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-239"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-240">int</span><span class="sxs-lookup"><span data-stu-id="e123e-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-241">Quantidade média de estimativa de largura de banda medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="e123e-241">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="e123e-242">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-243"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-243"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-244">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-245">Porcentagem da chamada em que o ponto de extremidade determinou que a conexão de rede não pôde suportar vídeo MultiView.</span><span class="sxs-lookup"><span data-stu-id="e123e-245">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="e123e-246">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-247"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-247"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-248">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-p104">Quantidade total de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="e123e-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="e123e-251">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-252"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-252"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-253">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-p105">Quantidade média de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="e123e-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="e123e-256">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-256">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-257"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-257"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-258">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-p106">Quantidade máxima de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="e123e-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="e123e-261">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-261">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-262"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-262"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-263">int</span><span class="sxs-lookup"><span data-stu-id="e123e-263">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-p107">Total de ocorrências de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="e123e-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e123e-267">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-268"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-268"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-269">int</span><span class="sxs-lookup"><span data-stu-id="e123e-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-p108">Densidade total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="e123e-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e123e-273">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-273">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-274"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-274"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-275">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-275">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-p109">Duração total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="e123e-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e123e-279">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-280"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-280"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-281">int</span><span class="sxs-lookup"><span data-stu-id="e123e-281">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-p110">Total de ocorrências de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="e123e-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e123e-285">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-285">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-286"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-286"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-287">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-287">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-p111">Densidade total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="e123e-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e123e-291">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-291">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-292"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-292"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-293">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-293">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-p112">Duração total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="e123e-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="e123e-297">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-297">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-298"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-298"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-299">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e123e-299">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-300">Taxa de perda dos pacotes de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e123e-300">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="e123e-301">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-301">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-302"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-302"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-303">int</span><span class="sxs-lookup"><span data-stu-id="e123e-303">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-304">Valor médio da largura de banda alocada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="e123e-304">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="e123e-305">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-306"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-306"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-307">smallint</span><span class="sxs-lookup"><span data-stu-id="e123e-307">smallint</span></span></p></td>
<td><p><span data-ttu-id="e123e-308">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="e123e-308">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e123e-309">Tipo de codecs de vídeo usados pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="e123e-309">Type of video codecs used by the sender.</span></span> <span data-ttu-id="e123e-310">Consulte a <a href="lync-server-2013-codecdescription-table.md">tabela CodecDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e123e-310">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="e123e-311">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-312"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-312"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-313">int</span><span class="sxs-lookup"><span data-stu-id="e123e-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-314">Largura da resolução usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="e123e-314">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="e123e-315">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-315">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-316"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-316"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-317">int</span><span class="sxs-lookup"><span data-stu-id="e123e-317">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-318">Altura da resolução usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="e123e-318">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="e123e-319">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-320"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-320"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-321">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-322">Taxa média de transmissão de quadros de vídeo usada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="e123e-322">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="e123e-323">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-324"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-324"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-325">int</span><span class="sxs-lookup"><span data-stu-id="e123e-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-326">Taxa de bits máxima para o remetente.</span><span class="sxs-lookup"><span data-stu-id="e123e-326">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="e123e-327">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-327">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-328"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-328"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-329">int</span><span class="sxs-lookup"><span data-stu-id="e123e-329">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-330">Taxa de bits média para o remetente.</span><span class="sxs-lookup"><span data-stu-id="e123e-330">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-331"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-331"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-332">int</span><span class="sxs-lookup"><span data-stu-id="e123e-332">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-333">Número máximo de fluxos de vídeo usados pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="e123e-333">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="e123e-334">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-335"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-335"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-336">smallint</span><span class="sxs-lookup"><span data-stu-id="e123e-336">smallint</span></span></p></td>
<td><p><span data-ttu-id="e123e-337">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="e123e-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e123e-338">Códigos de vídeo usados pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="e123e-338">Video codes used by the receiver.</span></span> <span data-ttu-id="e123e-339">Consulte a <a href="lync-server-2013-codecdescription-table.md">tabela CodecDescription no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e123e-339">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="e123e-340">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-341"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-341"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-342">int</span><span class="sxs-lookup"><span data-stu-id="e123e-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-343">Largura da resolução usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="e123e-343">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="e123e-344">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-344">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-345"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-345"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-346">int</span><span class="sxs-lookup"><span data-stu-id="e123e-346">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-347">Altura da resolução usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="e123e-347">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="e123e-348">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-348">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-349"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-349"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-350">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-350">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-351">Taxa média de quadros de vídeo usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="e123e-351">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="e123e-352">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-352">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-353"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-353"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-354">int</span><span class="sxs-lookup"><span data-stu-id="e123e-354">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-355">Taxa de bits máxima para o receptor.</span><span class="sxs-lookup"><span data-stu-id="e123e-355">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="e123e-356">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-356">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-357"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-357"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-358">int</span><span class="sxs-lookup"><span data-stu-id="e123e-358">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-359">Taxa de bits média para o receptor.</span><span class="sxs-lookup"><span data-stu-id="e123e-359">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="e123e-360">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-360">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-361"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-361"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-362">int</span><span class="sxs-lookup"><span data-stu-id="e123e-362">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-363">Máximo de fluxos de vídeo para o receptor.</span><span class="sxs-lookup"><span data-stu-id="e123e-363">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="e123e-364">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-364">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-365"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-365"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-366">int</span><span class="sxs-lookup"><span data-stu-id="e123e-366">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-367">Fluxos de vídeo mínimos para o receptor.</span><span class="sxs-lookup"><span data-stu-id="e123e-367">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="e123e-368">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-368">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-369"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-369"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-370">int</span><span class="sxs-lookup"><span data-stu-id="e123e-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-371">Modo de vídeo (por exemplo, galeria ou fluxo único) para o receptor.</span><span class="sxs-lookup"><span data-stu-id="e123e-371">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="e123e-372">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-372">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-373"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-373"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-374">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-374">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-375">Taxa de perda de pacote após a correção de erro encaminhar ter sido aplicada.</span><span class="sxs-lookup"><span data-stu-id="e123e-375">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="e123e-376">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-376">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-377"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-377"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-378">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-378">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-379">Porcentagem de tempo em que o sinalizador de recurso dinâmico estava ativo.</span><span class="sxs-lookup"><span data-stu-id="e123e-379">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="e123e-380">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-380">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-381"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-381"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-382">caractere (9)</span><span class="sxs-lookup"><span data-stu-id="e123e-382">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-383">Resolução mínima medida durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="e123e-383">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="e123e-384">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-384">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-385"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-385"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-386">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-386">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-387">Porcentagem da chamada abaixo do limite de taxa de bits baixa (70 kilobits por segundo).</span><span class="sxs-lookup"><span data-stu-id="e123e-387">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="e123e-388">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-388">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-389"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-389"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-390">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-391">Porcentagem da chamada abaixo do limite de baixa taxa de quadros (7,5 quadros por segundo, entrada).</span><span class="sxs-lookup"><span data-stu-id="e123e-391">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="e123e-392">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-392">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-393"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-393"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-394">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-395">Porcentagem da chamada que ocorreu na resolução mais baixa.</span><span class="sxs-lookup"><span data-stu-id="e123e-395">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="e123e-396">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="e123e-397">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-397">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e123e-398"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-398"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-399">flutuação</span><span class="sxs-lookup"><span data-stu-id="e123e-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-400">Duração da chamada em segundos.</span><span class="sxs-lookup"><span data-stu-id="e123e-400">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="e123e-401">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-401">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e123e-402"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="e123e-402"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="e123e-403">bits</span><span class="sxs-lookup"><span data-stu-id="e123e-403">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e123e-404">Indica se os dados foram agregados a várias chamadas.</span><span class="sxs-lookup"><span data-stu-id="e123e-404">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="e123e-405">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e123e-405">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

