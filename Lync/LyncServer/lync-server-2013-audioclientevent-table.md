---
title: 'Lync Server 2013: tabela AudioClientEvent'
description: 'Lync Server 2013: tabela AudioClientEvent.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2200cd9567bdd10ac4ad8f5c269062c2f5614dcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568777"
---
# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="b0563-103">Tabela AudioClientEvent no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0563-103">AudioClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0563-104">_**Última modificação do tópico:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="b0563-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="b0563-105">Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada de áudio.</span><span class="sxs-lookup"><span data-stu-id="b0563-105">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="b0563-106">Normalmente, uma chamada tem dois registros, um para o chamador e um para o receptor.</span><span class="sxs-lookup"><span data-stu-id="b0563-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0563-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b0563-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b0563-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b0563-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0563-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-112">datetime</span><span class="sxs-lookup"><span data-stu-id="b0563-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="b0563-113">Primário</span><span class="sxs-lookup"><span data-stu-id="b0563-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b0563-114">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b0563-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0563-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-116">int</span><span class="sxs-lookup"><span data-stu-id="b0563-116">int</span></span></p></td>
<td><p><span data-ttu-id="b0563-117">Primário</span><span class="sxs-lookup"><span data-stu-id="b0563-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="b0563-118">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b0563-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0563-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="b0563-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b0563-121">Primário</span><span class="sxs-lookup"><span data-stu-id="b0563-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="b0563-122">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b0563-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0563-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-124">bits</span><span class="sxs-lookup"><span data-stu-id="b0563-124">bit</span></span></p></td>
<td><p><span data-ttu-id="b0563-125">Primário</span><span class="sxs-lookup"><span data-stu-id="b0563-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="b0563-126">0: dados do receptor</span><span class="sxs-lookup"><span data-stu-id="b0563-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="b0563-127">1: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="b0563-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0563-128"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-128"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-129">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-129">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-130">Porcentagem da sessão que o evento NetworkSendQuality foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="b0563-130">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="b0563-131">A qualidade da rede em termos de tremulação ou perda de pacote é grave e afeta a qualidade do áudio que está sendo enviado.</span><span class="sxs-lookup"><span data-stu-id="b0563-131">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0563-132"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-132"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-133">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-133">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-134">Porcentagem da sessão que o evento ReceiveSendQuality foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="b0563-134">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="b0563-135">A qualidade da rede em termos de tremulação ou perda de pacote é grave e afeta a qualidade do áudio que está sendo recebido.</span><span class="sxs-lookup"><span data-stu-id="b0563-135">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0563-136"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-136"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-137">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-137">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-138">Porcentagem da sessão em que o evento Delay foi acionado para o estado "ruim".</span><span class="sxs-lookup"><span data-stu-id="b0563-138">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="b0563-139">A latência da rede é grave e afeta a experiência ao impedir a comunicação interativa</span><span class="sxs-lookup"><span data-stu-id="b0563-139">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0563-140"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-140"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-141">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-141">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-142">Porcentagem da sessão que o evento LowBandwidth foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="b0563-142">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="b0563-143">A largura de banda disponível é insuficiente para uma experiência de voz aceitável.</span><span class="sxs-lookup"><span data-stu-id="b0563-143">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0563-144"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-144"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-145">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-145">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-146">Porcentagem de sessão o evento de CPU insuficiente foi acionado para o estado ' ruim '.</span><span class="sxs-lookup"><span data-stu-id="b0563-146">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="b0563-147">Há ciclos de CPU insuficientes para processamento com as modalidades atuais e os aplicativos em uso.</span><span class="sxs-lookup"><span data-stu-id="b0563-147">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="b0563-148">Isso causa distorções com o canal de áudio.</span><span class="sxs-lookup"><span data-stu-id="b0563-148">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0563-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-150">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-150">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-151">Porcentagem da sessão que o evento DeviceHalfDuplexAEC foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="b0563-151">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="b0563-152">Para evitar o eco, o sistema digitou Half duplex.</span><span class="sxs-lookup"><span data-stu-id="b0563-152">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0563-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-154">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-154">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-155">Porcentagem da sessão que o evento DeviceRenderNotFunctioning foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="b0563-155">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="b0563-156">O dispositivo de renderização que está sendo usado atualmente para a sessão não está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="b0563-156">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="b0563-157">Isso pode causar problemas de áudio unidirecionais.</span><span class="sxs-lookup"><span data-stu-id="b0563-157">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0563-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-159">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-159">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-160">Porcentagem da sessão que o evento DeviceCaptureNotFunctioning foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="b0563-160">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="b0563-161">O dispositivo de captura que está sendo usado atualmente para a sessão não está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="b0563-161">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="b0563-162">Isso pode causar problemas de áudio unidirecionais.</span><span class="sxs-lookup"><span data-stu-id="b0563-162">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0563-163"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-163"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-164">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-164">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-165">Porcentagem da sessão que o evento DeviceGlitches foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="b0563-165">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="b0563-166">Há problemas sérios na renderização de áudio que está causando distorções.</span><span class="sxs-lookup"><span data-stu-id="b0563-166">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="b0563-167">Essas falhas podem ser causadas por problemas de driver, Storm (chamadas de procedimento adiadas) (DPC) e alto uso da CPU.</span><span class="sxs-lookup"><span data-stu-id="b0563-167">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0563-168"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-168"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-169">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-169">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-170">Porcentagem da sessão que o evento DeviceLowSNR foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="b0563-170">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="b0563-171">A qualidade de captura é muito ruim, ou seja, muito ruidosa ou o usuário está falando muito longe do microfone.</span><span class="sxs-lookup"><span data-stu-id="b0563-171">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="b0563-172">Isso causará distorções.</span><span class="sxs-lookup"><span data-stu-id="b0563-172">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0563-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-174">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-174">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-175">Porcentagem da sessão que o evento DeviceLowSpeechLevel foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="b0563-175">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="b0563-176">O nível de fala do usuário é muito baixo e o sistema não pode aumentar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="b0563-176">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="b0563-177">Isso pode causar distorções ou ser percebido como um áudio unidirecional.</span><span class="sxs-lookup"><span data-stu-id="b0563-177">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0563-178"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-178"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-179">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-179">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-180">Porcentagem da sessão que o evento DeviceClipping foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="b0563-180">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="b0563-181">Quando os clipes de fala near-end, o microfone é distorção de escuta de ponta devido ao recorte.</span><span class="sxs-lookup"><span data-stu-id="b0563-181">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="b0563-182">É importante evitar o recorte de microfone near-end.</span><span class="sxs-lookup"><span data-stu-id="b0563-182">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0563-183"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-183"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-184">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-184">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-185">Porcentagem da sessão que o evento por que deviceechoevent foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="b0563-185">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="b0563-186">O dispositivo ou a instalação está causando eco além da capacidade do sistema de compensar.</span><span class="sxs-lookup"><span data-stu-id="b0563-186">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0563-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-188">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-188">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-189">Porcentagem da sessão que o evento DeviceNearEndToEchoRatio foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="b0563-189">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="b0563-190">A fala do usuário é muito baixa em comparação com o eco que está sendo capturado, o que afeta a experiência dos usuários porque limita como é fácil interromper um usuário.</span><span class="sxs-lookup"><span data-stu-id="b0563-190">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="b0563-191">Reduzir volume do alto-falante, mova o microfone para perto do Talker.</span><span class="sxs-lookup"><span data-stu-id="b0563-191">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0563-192"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-192"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-193">int</span><span class="sxs-lookup"><span data-stu-id="b0563-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0563-194">Número de vezes durante a sessão em que o evento DeviceMultipleEndpoints foi acionado para o estado ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="b0563-194">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="b0563-195">Vários pontos de extremidade de áudio na mesma sessão detectados e o sistema compensado pela redução do volume de renderização.</span><span class="sxs-lookup"><span data-stu-id="b0563-195">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0563-196"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-196"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-197">int</span><span class="sxs-lookup"><span data-stu-id="b0563-197">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b0563-198">Número de vezes durante a sessão em que o evento DeviceHowlingEvent foi acionado para o estado ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="b0563-198">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="b0563-199">Loop de comentários de áudio detectado (causado por vários pontos de extremidade que compartilham o caminho de áudio).</span><span class="sxs-lookup"><span data-stu-id="b0563-199">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0563-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-201">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-201">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0563-202">Porcentagem da sessão em que o evento DeviceRenderZeroVolume foi acionado para estar no estado "ruim".</span><span class="sxs-lookup"><span data-stu-id="b0563-202">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="b0563-203">O dispositivo de renderização foi definido como volume zero.</span><span class="sxs-lookup"><span data-stu-id="b0563-203">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="b0563-204">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b0563-204">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0563-205"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="b0563-205"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="b0563-206">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="b0563-206">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b0563-207">Porcentagem da sessão em que o evento DeviceRenderMute foi acionado para estar no estado "ruim".</span><span class="sxs-lookup"><span data-stu-id="b0563-207">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="b0563-208">O dispositivo de renderização estava com mudo ativado.</span><span class="sxs-lookup"><span data-stu-id="b0563-208">The render device was muted.</span></span></p>
<p><span data-ttu-id="b0563-209">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b0563-209">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

