---
title: 'Lync Server 2013: tabela AudioClientEvent'
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
ms.openlocfilehash: 0f0d37de40340a66e6d87365ce40924f6c6d98f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="f5474-102">Tabela AudioClientEvent no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5474-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5474-103">_**Última modificação do tópico:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="f5474-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="f5474-104">Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada de áudio.</span><span class="sxs-lookup"><span data-stu-id="f5474-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="f5474-105">Normalmente, uma chamada tem dois registros, um para o chamador e um para o receptor.</span><span class="sxs-lookup"><span data-stu-id="f5474-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5474-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f5474-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f5474-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f5474-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5474-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f5474-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f5474-112">Primário</span><span class="sxs-lookup"><span data-stu-id="f5474-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f5474-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5474-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5474-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-115">int</span><span class="sxs-lookup"><span data-stu-id="f5474-115">int</span></span></p></td>
<td><p><span data-ttu-id="f5474-116">Primário</span><span class="sxs-lookup"><span data-stu-id="f5474-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f5474-117">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5474-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5474-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5474-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f5474-120">Primário</span><span class="sxs-lookup"><span data-stu-id="f5474-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="f5474-121">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f5474-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5474-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-123">bits</span><span class="sxs-lookup"><span data-stu-id="f5474-123">bit</span></span></p></td>
<td><p><span data-ttu-id="f5474-124">Primário</span><span class="sxs-lookup"><span data-stu-id="f5474-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="f5474-125">0: dados do receptor</span><span class="sxs-lookup"><span data-stu-id="f5474-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="f5474-126">1: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="f5474-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5474-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-128">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-129">Porcentagem da sessão que o evento NetworkSendQuality foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="f5474-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="f5474-130">A qualidade da rede em termos de tremulação ou perda de pacote é grave e afeta a qualidade do áudio que está sendo enviado.</span><span class="sxs-lookup"><span data-stu-id="f5474-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5474-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-132">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-133">Porcentagem da sessão que o evento ReceiveSendQuality foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="f5474-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="f5474-134">A qualidade da rede em termos de tremulação ou perda de pacote é grave e afeta a qualidade do áudio que está sendo recebido.</span><span class="sxs-lookup"><span data-stu-id="f5474-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5474-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-136">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-137">Porcentagem da sessão em que o evento Delay foi acionado para o estado "ruim".</span><span class="sxs-lookup"><span data-stu-id="f5474-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f5474-138">A latência da rede é grave e afeta a experiência ao impedir a comunicação interativa</span><span class="sxs-lookup"><span data-stu-id="f5474-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5474-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-140">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-141">Porcentagem da sessão que o evento LowBandwidth foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="f5474-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f5474-142">A largura de banda disponível é insuficiente para uma experiência de voz aceitável.</span><span class="sxs-lookup"><span data-stu-id="f5474-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5474-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-144">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-145">Porcentagem de sessão o evento de CPU insuficiente foi acionado para o estado ' ruim '.</span><span class="sxs-lookup"><span data-stu-id="f5474-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f5474-146">Há ciclos de CPU insuficientes para processamento com as modalidades atuais e os aplicativos em uso.</span><span class="sxs-lookup"><span data-stu-id="f5474-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="f5474-147">Isso causa distorções com o canal de áudio.</span><span class="sxs-lookup"><span data-stu-id="f5474-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5474-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-149">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-150">Porcentagem da sessão que o evento DeviceHalfDuplexAEC foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="f5474-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f5474-151">Para evitar o eco, o sistema digitou Half duplex.</span><span class="sxs-lookup"><span data-stu-id="f5474-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5474-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-153">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-154">Porcentagem da sessão que o evento DeviceRenderNotFunctioning foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="f5474-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f5474-155">O dispositivo de renderização que está sendo usado atualmente para a sessão não está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="f5474-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="f5474-156">Isso pode causar problemas de áudio unidirecionais.</span><span class="sxs-lookup"><span data-stu-id="f5474-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5474-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-158">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-159">Porcentagem da sessão que o evento DeviceCaptureNotFunctioning foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="f5474-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f5474-160">O dispositivo de captura que está sendo usado atualmente para a sessão não está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="f5474-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="f5474-161">Isso pode causar problemas de áudio unidirecionais.</span><span class="sxs-lookup"><span data-stu-id="f5474-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5474-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-163">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-164">Porcentagem da sessão que o evento DeviceGlitches foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="f5474-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f5474-165">Há problemas sérios na renderização de áudio que está causando distorções.</span><span class="sxs-lookup"><span data-stu-id="f5474-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="f5474-166">Essas falhas podem ser causadas por problemas de driver, Storm (chamadas de procedimento adiadas) (DPC) e alto uso da CPU.</span><span class="sxs-lookup"><span data-stu-id="f5474-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5474-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-168">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-169">Porcentagem da sessão que o evento DeviceLowSNR foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="f5474-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f5474-170">A qualidade de captura é muito ruim, ou seja, muito ruidosa ou o usuário está falando muito longe do microfone.</span><span class="sxs-lookup"><span data-stu-id="f5474-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="f5474-171">Isso causará distorções.</span><span class="sxs-lookup"><span data-stu-id="f5474-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5474-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-173">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-174">Porcentagem da sessão que o evento DeviceLowSpeechLevel foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="f5474-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f5474-175">O nível de fala do usuário é muito baixo e o sistema não pode aumentar ainda mais.</span><span class="sxs-lookup"><span data-stu-id="f5474-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="f5474-176">Isso pode causar distorções ou ser percebido como um áudio unidirecional.</span><span class="sxs-lookup"><span data-stu-id="f5474-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5474-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-178">Decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-179">Porcentagem da sessão que o evento DeviceClipping foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="f5474-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="f5474-180">Quando os clipes de fala near-end, o microfone é distorção de escuta de ponta devido ao recorte.</span><span class="sxs-lookup"><span data-stu-id="f5474-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="f5474-181">É importante evitar o recorte de microfone near-end.</span><span class="sxs-lookup"><span data-stu-id="f5474-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5474-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-183">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-184">Porcentagem da sessão que o evento por que deviceechoevent foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="f5474-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f5474-185">O dispositivo ou a instalação está causando eco além da capacidade do sistema de compensar.</span><span class="sxs-lookup"><span data-stu-id="f5474-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5474-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-187">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-188">Porcentagem da sessão que o evento DeviceNearEndToEchoRatio foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="f5474-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f5474-189">A fala do usuário é muito baixa em comparação com o eco que está sendo capturado, o que afeta a experiência dos usuários porque limita como é fácil interromper um usuário.</span><span class="sxs-lookup"><span data-stu-id="f5474-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="f5474-190">Reduzir volume do alto-falante, mova o microfone para perto do Talker.</span><span class="sxs-lookup"><span data-stu-id="f5474-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5474-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-192">int</span><span class="sxs-lookup"><span data-stu-id="f5474-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5474-193">Número de vezes durante a sessão em que o evento DeviceMultipleEndpoints foi acionado para o estado ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f5474-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f5474-194">Vários pontos de extremidade de áudio na mesma sessão detectados e o sistema compensado pela redução do volume de renderização.</span><span class="sxs-lookup"><span data-stu-id="f5474-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5474-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-196">int</span><span class="sxs-lookup"><span data-stu-id="f5474-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f5474-197">Número de vezes durante a sessão em que o evento DeviceHowlingEvent foi acionado para o estado ' Bad '.</span><span class="sxs-lookup"><span data-stu-id="f5474-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f5474-198">Loop de comentários de áudio detectado (causado por vários pontos de extremidade que compartilham o caminho de áudio).</span><span class="sxs-lookup"><span data-stu-id="f5474-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5474-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-200">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5474-201">Porcentagem da sessão em que o evento DeviceRenderZeroVolume foi acionado para estar no estado "ruim".</span><span class="sxs-lookup"><span data-stu-id="f5474-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="f5474-202">O dispositivo de renderização foi definido como volume zero.</span><span class="sxs-lookup"><span data-stu-id="f5474-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="f5474-203">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5474-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5474-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f5474-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f5474-205">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f5474-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5474-206">Porcentagem da sessão em que o evento DeviceRenderMute foi acionado para estar no estado "ruim".</span><span class="sxs-lookup"><span data-stu-id="f5474-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="f5474-207">O dispositivo de renderização estava com mudo ativado.</span><span class="sxs-lookup"><span data-stu-id="f5474-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="f5474-208">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5474-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

