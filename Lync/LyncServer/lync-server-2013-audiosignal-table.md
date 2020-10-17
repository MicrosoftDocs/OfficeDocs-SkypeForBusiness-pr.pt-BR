---
title: 'Lync Server 2013: tabela AudioSignal'
description: 'Lync Server 2013: tabela AudioSignal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82f3b3119eaccfe56c4706cff07469bc3434461f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568757"
---
# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="96852-103">Tabela AudioSignal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96852-103">AudioSignal table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96852-104">_**Última modificação do tópico:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="96852-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="96852-105">Cada registro representa as métricas do sinal de áudio para um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="96852-105">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="96852-106">Geralmente, cada chamada tem dois registros, um é para o chamador e um é para o receptor.</span><span class="sxs-lookup"><span data-stu-id="96852-106">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96852-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="96852-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="96852-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="96852-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="96852-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="96852-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="96852-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="96852-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96852-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="96852-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-112">datetime</span><span class="sxs-lookup"><span data-stu-id="96852-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="96852-113">Primário</span><span class="sxs-lookup"><span data-stu-id="96852-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="96852-114">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="96852-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="96852-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-116">int</span><span class="sxs-lookup"><span data-stu-id="96852-116">int</span></span></p></td>
<td><p><span data-ttu-id="96852-117">Primário</span><span class="sxs-lookup"><span data-stu-id="96852-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="96852-118">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="96852-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="96852-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="96852-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="96852-121">Primário</span><span class="sxs-lookup"><span data-stu-id="96852-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="96852-122">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="96852-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="96852-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-124">bits</span><span class="sxs-lookup"><span data-stu-id="96852-124">bit</span></span></p></td>
<td><p><span data-ttu-id="96852-125">Primário</span><span class="sxs-lookup"><span data-stu-id="96852-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="96852-126">0: dados do receptor</span><span class="sxs-lookup"><span data-stu-id="96852-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="96852-127">1: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="96852-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-128"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="96852-128"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-129">int</span><span class="sxs-lookup"><span data-stu-id="96852-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-130">Representa o nível de sinal de áudio de controle de ganho de pós-instantâneo.</span><span class="sxs-lookup"><span data-stu-id="96852-130">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="96852-131">A unidade desta medida é o dBmo.</span><span class="sxs-lookup"><span data-stu-id="96852-131">The unit for this metric is dBmo.</span></span> <span data-ttu-id="96852-132">Para uma qualidade aceitável, deve ser ao menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="96852-132">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="96852-133">Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="96852-133">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-134"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="96852-134"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-135">int</span><span class="sxs-lookup"><span data-stu-id="96852-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-136">Consulte SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="96852-136">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-137"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="96852-137"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-138">int</span><span class="sxs-lookup"><span data-stu-id="96852-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-139">Representa o nível de ruído de áudio de controle de ganho de pós-instantâneo.</span><span class="sxs-lookup"><span data-stu-id="96852-139">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="96852-140">A unidade desta medida é o dBmo.</span><span class="sxs-lookup"><span data-stu-id="96852-140">The unit for this metric is dBmo.</span></span> <span data-ttu-id="96852-141">Para uma qualidade aceitável, deve ser menor que 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="96852-141">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="96852-142">Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="96852-142">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-143"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="96852-143"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-144">int</span><span class="sxs-lookup"><span data-stu-id="96852-144">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-145">Consulte SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="96852-145">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-146"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="96852-146"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-147">int</span><span class="sxs-lookup"><span data-stu-id="96852-147">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-148">Métrica de aprimoramento de perda de retorno de eco.</span><span class="sxs-lookup"><span data-stu-id="96852-148">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="96852-149">A unidade desta medida é o dB.</span><span class="sxs-lookup"><span data-stu-id="96852-149">The unit for this metric is dB.</span></span> <span data-ttu-id="96852-150">Valores mais baixos representam menos eco.</span><span class="sxs-lookup"><span data-stu-id="96852-150">Lower values represent less echo.</span></span> <span data-ttu-id="96852-151">Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="96852-151">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-152"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="96852-152"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-153">int</span><span class="sxs-lookup"><span data-stu-id="96852-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-154">Falhas médias por cinco minutos para a renderização Loudspeaker.</span><span class="sxs-lookup"><span data-stu-id="96852-154">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="96852-155">Para uma boa qualidade, deve ser menos de um a cada cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="96852-155">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="96852-156">Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="96852-156">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-157"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="96852-157"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-158">int</span><span class="sxs-lookup"><span data-stu-id="96852-158">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-159">Falhas médias por cinco minutos para a captura do microfone.</span><span class="sxs-lookup"><span data-stu-id="96852-159">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="96852-160">Para uma boa qualidade, deve ser menos de um a cada cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="96852-160">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="96852-161">Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="96852-161">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-162"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="96852-162"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-163">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="96852-163">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-164">Taxa de descompasso do relógio do dispositivo de microfone, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="96852-164">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-165"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="96852-165"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-166">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="96852-166">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-167">Taxa de descompasso do relógio do dispositivo de alto-falante, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="96852-167">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-168"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="96852-168"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-169">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="96852-169">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-170">Taxa de descompasso do relógio do dispositivo de alto-falante, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="96852-170">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="96852-171">Média de erro de registro de hora de fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="96852-171">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-172"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="96852-172"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-173">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="96852-173">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-174">Erro de carimbo de data/hora médio do fluxo de alto-falante, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="96852-174">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-175"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="96852-175"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-176">smallint</span><span class="sxs-lookup"><span data-stu-id="96852-176">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-177">Opção de voz é um modo meio-duplex com capacidade de interrupção reduzida.</span><span class="sxs-lookup"><span data-stu-id="96852-177">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="96852-178">Causas da entrada da opção de voz:</span><span class="sxs-lookup"><span data-stu-id="96852-178">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="96852-179">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="96852-179">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="96852-180">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="96852-180">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="96852-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="96852-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="96852-182">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="96852-182">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="96852-183">A causa pode ser uma combinação dessas causas individuais.</span><span class="sxs-lookup"><span data-stu-id="96852-183">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="96852-184">ENTER_VS_FORCEORCONVERGENCE só pode ser habilitado por RegKey para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="96852-184">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="96852-185">O tipo de dados desta coluna foi alterado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96852-185">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-186"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="96852-186"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="96852-187">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-188">Causas de um evento Echo:</span><span class="sxs-lookup"><span data-stu-id="96852-188">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="96852-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="96852-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="96852-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="96852-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="96852-191">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="96852-191">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="96852-192">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="96852-192">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="96852-193">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="96852-193">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="96852-194">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="96852-194">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="96852-195">A causa pode ser uma combinação dessas causas individuais.</span><span class="sxs-lookup"><span data-stu-id="96852-195">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-196"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="96852-196"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-197">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="96852-197">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-198">Porcentagem de tempo em que o eco foi detectado no fluxo de captura do microfone.</span><span class="sxs-lookup"><span data-stu-id="96852-198">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="96852-199">Normalmente, os valores são baixos para fones de ouvido ou fones, e mais altos para telefones do alto-falante ou alto-falantes autônomos.</span><span class="sxs-lookup"><span data-stu-id="96852-199">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="96852-200">Para dispositivos que suportam cancelamento de eco acústico integrado, valores altos indicam vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="96852-200">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="96852-201">Para outros dispositivos, essa métrica não deve ser usada para avaliar a qualidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="96852-201">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-202"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="96852-202"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-203">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="96852-203">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96852-204">Porcentagem de tempo quando o eco é detectado no fluxo enviado.</span><span class="sxs-lookup"><span data-stu-id="96852-204">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="96852-205">Uma alta porcentagem de eco em fluxos enviados indica um vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="96852-205">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-206"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="96852-206"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-207">int</span><span class="sxs-lookup"><span data-stu-id="96852-207">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-208">Nível de sinal recebido no servidor de mediação do gateway; Isso se aplica apenas ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="96852-208">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="96852-209">A unidade desta medida é o dBoV.</span><span class="sxs-lookup"><span data-stu-id="96852-209">The unit of this metric is dBoV.</span></span> <span data-ttu-id="96852-210">Para uma boa qualidade, a faixa aceitável deve ser de [-30 a -18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="96852-210">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-211"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="96852-211"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-212">int</span><span class="sxs-lookup"><span data-stu-id="96852-212">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-213">Nível de sinal recebido no servidor de mediação do gateway.</span><span class="sxs-lookup"><span data-stu-id="96852-213">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="96852-214">Se aplica apenas ao Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="96852-214">This applies only to the Mediation Server.</span></span> <span data-ttu-id="96852-215">A unidade desta medida é o dBoV.</span><span class="sxs-lookup"><span data-stu-id="96852-215">The unit of this metric is dBoV.</span></span> <span data-ttu-id="96852-216">Para uma boa qualidade, a faixa aceitável deve ser menor do que -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="96852-216">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-217"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="96852-217"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-218">int</span><span class="sxs-lookup"><span data-stu-id="96852-218">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-219">Controle de ganho automático (AGC) no lado do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="96852-219">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-220"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="96852-220"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-221">flutuação</span><span class="sxs-lookup"><span data-stu-id="96852-221">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="96852-222">O quadrado de raiz média (RMS) do sinal de entrada de até os primeiros 30 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="96852-222">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-223"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="96852-223"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-224">int</span><span class="sxs-lookup"><span data-stu-id="96852-224">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96852-225">Nível de sinal como recebido no canal 1.</span><span class="sxs-lookup"><span data-stu-id="96852-225">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="96852-226">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96852-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-227"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="96852-227"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-228">int</span><span class="sxs-lookup"><span data-stu-id="96852-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96852-229">Nível de sinal como recebido no canal 2.</span><span class="sxs-lookup"><span data-stu-id="96852-229">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="96852-230">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96852-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-231"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="96852-231"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-232">int</span><span class="sxs-lookup"><span data-stu-id="96852-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96852-233">Nível de ruído como recebido no canal 1.</span><span class="sxs-lookup"><span data-stu-id="96852-233">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="96852-234">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96852-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-235"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="96852-235"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-236">int</span><span class="sxs-lookup"><span data-stu-id="96852-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96852-237">Nível de ruído como recebido no canal 2.</span><span class="sxs-lookup"><span data-stu-id="96852-237">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="96852-238">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96852-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-239"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="96852-239"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-240">int</span><span class="sxs-lookup"><span data-stu-id="96852-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96852-241">Nível de sinal como enviado no canal 1.</span><span class="sxs-lookup"><span data-stu-id="96852-241">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="96852-242">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96852-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-243"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="96852-243"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-244">int</span><span class="sxs-lookup"><span data-stu-id="96852-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96852-245">Nível de sinal como enviado no canal 2.</span><span class="sxs-lookup"><span data-stu-id="96852-245">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="96852-246">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96852-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96852-247"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="96852-247"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-248">int</span><span class="sxs-lookup"><span data-stu-id="96852-248">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96852-249">Nível de ruído como enviado no canal 1.</span><span class="sxs-lookup"><span data-stu-id="96852-249">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="96852-250">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96852-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96852-251"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="96852-251"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="96852-252">int</span><span class="sxs-lookup"><span data-stu-id="96852-252">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96852-253">Nível de ruído como enviado no canal 2.</span><span class="sxs-lookup"><span data-stu-id="96852-253">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="96852-254">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96852-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

