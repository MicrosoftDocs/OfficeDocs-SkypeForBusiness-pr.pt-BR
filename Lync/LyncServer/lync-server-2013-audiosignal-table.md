---
title: 'Lync Server 2013: tabela AudioSignal'
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
ms.openlocfilehash: 2605bfbd3e1d4023c013557aea2bcf75404fb23c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533508"
---
# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="ba746-102">Tabela AudioSignal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba746-102">AudioSignal table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba746-103">_**Última modificação do tópico:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="ba746-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="ba746-104">Cada registro representa as métricas do sinal de áudio para um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ba746-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="ba746-105">Geralmente, cada chamada tem dois registros, um é para o chamador e um é para o receptor.</span><span class="sxs-lookup"><span data-stu-id="ba746-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba746-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ba746-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ba746-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ba746-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba746-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ba746-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ba746-112">Primário</span><span class="sxs-lookup"><span data-stu-id="ba746-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ba746-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ba746-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-115">int</span><span class="sxs-lookup"><span data-stu-id="ba746-115">int</span></span></p></td>
<td><p><span data-ttu-id="ba746-116">Primário</span><span class="sxs-lookup"><span data-stu-id="ba746-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="ba746-117">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ba746-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba746-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba746-120">Primário</span><span class="sxs-lookup"><span data-stu-id="ba746-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="ba746-121">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ba746-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-123">bits</span><span class="sxs-lookup"><span data-stu-id="ba746-123">bit</span></span></p></td>
<td><p><span data-ttu-id="ba746-124">Primário</span><span class="sxs-lookup"><span data-stu-id="ba746-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="ba746-125">0: dados do receptor</span><span class="sxs-lookup"><span data-stu-id="ba746-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="ba746-126">1: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="ba746-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-128">int</span><span class="sxs-lookup"><span data-stu-id="ba746-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-129">Representa o nível de sinal de áudio de controle de ganho de pós-instantâneo.</span><span class="sxs-lookup"><span data-stu-id="ba746-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="ba746-130">A unidade desta medida é o dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba746-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="ba746-131">Para uma qualidade aceitável, deve ser ao menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba746-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="ba746-132">Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba746-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-134">int</span><span class="sxs-lookup"><span data-stu-id="ba746-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-135">Consulte SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="ba746-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-137">int</span><span class="sxs-lookup"><span data-stu-id="ba746-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-138">Representa o nível de ruído de áudio de controle de ganho de pós-instantâneo.</span><span class="sxs-lookup"><span data-stu-id="ba746-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="ba746-139">A unidade desta medida é o dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba746-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="ba746-140">Para uma qualidade aceitável, deve ser menor que 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba746-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="ba746-141">Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba746-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-143">int</span><span class="sxs-lookup"><span data-stu-id="ba746-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-144">Consulte SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="ba746-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-146">int</span><span class="sxs-lookup"><span data-stu-id="ba746-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-147">Métrica de aprimoramento de perda de retorno de eco.</span><span class="sxs-lookup"><span data-stu-id="ba746-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="ba746-148">A unidade desta medida é o dB.</span><span class="sxs-lookup"><span data-stu-id="ba746-148">The unit for this metric is dB.</span></span> <span data-ttu-id="ba746-149">Valores mais baixos representam menos eco.</span><span class="sxs-lookup"><span data-stu-id="ba746-149">Lower values represent less echo.</span></span> <span data-ttu-id="ba746-150">Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba746-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-152">int</span><span class="sxs-lookup"><span data-stu-id="ba746-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-153">Falhas médias por cinco minutos para a renderização Loudspeaker.</span><span class="sxs-lookup"><span data-stu-id="ba746-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="ba746-154">Para uma boa qualidade, deve ser menos de um a cada cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="ba746-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="ba746-155">Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba746-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-157">int</span><span class="sxs-lookup"><span data-stu-id="ba746-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-158">Falhas médias por cinco minutos para a captura do microfone.</span><span class="sxs-lookup"><span data-stu-id="ba746-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="ba746-159">Para uma boa qualidade, deve ser menos de um a cada cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="ba746-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="ba746-160">Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba746-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-162">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ba746-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-163">Taxa de descompasso do relógio do dispositivo de microfone, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="ba746-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-165">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ba746-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-166">Taxa de descompasso do relógio do dispositivo de alto-falante, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="ba746-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-168">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ba746-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-169">Taxa de descompasso do relógio do dispositivo de alto-falante, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="ba746-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="ba746-170">Média de erro de registro de hora de fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="ba746-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-172">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="ba746-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-173">Erro de carimbo de data/hora médio do fluxo de alto-falante, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="ba746-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-175">smallint</span><span class="sxs-lookup"><span data-stu-id="ba746-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-176">Opção de voz é um modo meio-duplex com capacidade de interrupção reduzida.</span><span class="sxs-lookup"><span data-stu-id="ba746-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="ba746-177">Causas da entrada da opção de voz:</span><span class="sxs-lookup"><span data-stu-id="ba746-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="ba746-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="ba746-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="ba746-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="ba746-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="ba746-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="ba746-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="ba746-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="ba746-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="ba746-182">A causa pode ser uma combinação dessas causas individuais.</span><span class="sxs-lookup"><span data-stu-id="ba746-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="ba746-183">ENTER_VS_FORCEORCONVERGENCE só pode ser habilitado por RegKey para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="ba746-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="ba746-184">O tipo de dados desta coluna foi alterado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba746-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba746-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-187">Causas de um evento Echo:</span><span class="sxs-lookup"><span data-stu-id="ba746-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="ba746-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="ba746-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="ba746-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="ba746-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="ba746-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="ba746-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="ba746-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="ba746-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="ba746-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="ba746-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="ba746-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="ba746-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="ba746-194">A causa pode ser uma combinação dessas causas individuais.</span><span class="sxs-lookup"><span data-stu-id="ba746-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-196">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ba746-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-197">Porcentagem de tempo em que o eco foi detectado no fluxo de captura do microfone.</span><span class="sxs-lookup"><span data-stu-id="ba746-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="ba746-198">Normalmente, os valores são baixos para fones de ouvido ou fones, e mais altos para telefones do alto-falante ou alto-falantes autônomos.</span><span class="sxs-lookup"><span data-stu-id="ba746-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="ba746-199">Para dispositivos que suportam cancelamento de eco acústico integrado, valores altos indicam vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="ba746-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="ba746-200">Para outros dispositivos, essa métrica não deve ser usada para avaliar a qualidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba746-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-202">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ba746-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba746-203">Porcentagem de tempo quando o eco é detectado no fluxo enviado.</span><span class="sxs-lookup"><span data-stu-id="ba746-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="ba746-204">Uma alta porcentagem de eco em fluxos enviados indica um vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="ba746-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-206">int</span><span class="sxs-lookup"><span data-stu-id="ba746-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-207">Nível de sinal recebido no servidor de mediação do gateway; Isso se aplica apenas ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="ba746-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="ba746-208">A unidade desta medida é o dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba746-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="ba746-209">Para uma boa qualidade, a faixa aceitável deve ser de [-30 a -18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba746-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-211">int</span><span class="sxs-lookup"><span data-stu-id="ba746-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-212">Nível de sinal recebido no servidor de mediação do gateway.</span><span class="sxs-lookup"><span data-stu-id="ba746-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="ba746-213">Se aplica apenas ao Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="ba746-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="ba746-214">A unidade desta medida é o dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba746-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="ba746-215">Para uma boa qualidade, a faixa aceitável deve ser menor do que -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba746-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-217">int</span><span class="sxs-lookup"><span data-stu-id="ba746-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-218">Controle de ganho automático (AGC) no lado do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="ba746-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-220">flutuação</span><span class="sxs-lookup"><span data-stu-id="ba746-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ba746-221">O quadrado de raiz média (RMS) do sinal de entrada de até os primeiros 30 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="ba746-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-223">int</span><span class="sxs-lookup"><span data-stu-id="ba746-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba746-224">Nível de sinal como recebido no canal 1.</span><span class="sxs-lookup"><span data-stu-id="ba746-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="ba746-225">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba746-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-227">int</span><span class="sxs-lookup"><span data-stu-id="ba746-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba746-228">Nível de sinal como recebido no canal 2.</span><span class="sxs-lookup"><span data-stu-id="ba746-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="ba746-229">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba746-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-231">int</span><span class="sxs-lookup"><span data-stu-id="ba746-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba746-232">Nível de ruído como recebido no canal 1.</span><span class="sxs-lookup"><span data-stu-id="ba746-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="ba746-233">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba746-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-235">int</span><span class="sxs-lookup"><span data-stu-id="ba746-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba746-236">Nível de ruído como recebido no canal 2.</span><span class="sxs-lookup"><span data-stu-id="ba746-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="ba746-237">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba746-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-239">int</span><span class="sxs-lookup"><span data-stu-id="ba746-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba746-240">Nível de sinal como enviado no canal 1.</span><span class="sxs-lookup"><span data-stu-id="ba746-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="ba746-241">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba746-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-243">int</span><span class="sxs-lookup"><span data-stu-id="ba746-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba746-244">Nível de sinal como enviado no canal 2.</span><span class="sxs-lookup"><span data-stu-id="ba746-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="ba746-245">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba746-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba746-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-247">int</span><span class="sxs-lookup"><span data-stu-id="ba746-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba746-248">Nível de ruído como enviado no canal 1.</span><span class="sxs-lookup"><span data-stu-id="ba746-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="ba746-249">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba746-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba746-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="ba746-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="ba746-251">int</span><span class="sxs-lookup"><span data-stu-id="ba746-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba746-252">Nível de ruído como enviado no canal 2.</span><span class="sxs-lookup"><span data-stu-id="ba746-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="ba746-253">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba746-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

