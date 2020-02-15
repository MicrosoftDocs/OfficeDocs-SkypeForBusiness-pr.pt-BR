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
ms.openlocfilehash: 9d7dcf9337dceded96679411e575abc888164618
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="15a17-102">Tabela AudioSignal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15a17-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15a17-103">_**Última modificação do tópico:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="15a17-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="15a17-104">Cada registro representa as métricas do sinal de áudio para um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="15a17-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="15a17-105">Geralmente, cada chamada tem dois registros, um é para o chamador e um é para o receptor.</span><span class="sxs-lookup"><span data-stu-id="15a17-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15a17-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="15a17-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="15a17-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="15a17-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15a17-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-111">datetime</span><span class="sxs-lookup"><span data-stu-id="15a17-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="15a17-112">Primário</span><span class="sxs-lookup"><span data-stu-id="15a17-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="15a17-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="15a17-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-115">int</span><span class="sxs-lookup"><span data-stu-id="15a17-115">int</span></span></p></td>
<td><p><span data-ttu-id="15a17-116">Primário</span><span class="sxs-lookup"><span data-stu-id="15a17-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="15a17-117">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="15a17-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="15a17-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="15a17-120">Primário</span><span class="sxs-lookup"><span data-stu-id="15a17-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="15a17-121">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="15a17-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-123">bits</span><span class="sxs-lookup"><span data-stu-id="15a17-123">bit</span></span></p></td>
<td><p><span data-ttu-id="15a17-124">Primário</span><span class="sxs-lookup"><span data-stu-id="15a17-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="15a17-125">0: dados do receptor</span><span class="sxs-lookup"><span data-stu-id="15a17-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="15a17-126">1: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="15a17-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-128">int</span><span class="sxs-lookup"><span data-stu-id="15a17-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-129">Representa o nível de sinal de áudio de controle de ganho de pós-instantâneo.</span><span class="sxs-lookup"><span data-stu-id="15a17-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="15a17-130">A unidade desta medida é o dBmo.</span><span class="sxs-lookup"><span data-stu-id="15a17-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="15a17-131">Para uma qualidade aceitável, deve ser ao menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="15a17-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="15a17-132">Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="15a17-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-134">int</span><span class="sxs-lookup"><span data-stu-id="15a17-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-135">Consulte SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="15a17-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-137">int</span><span class="sxs-lookup"><span data-stu-id="15a17-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-138">Representa o nível de ruído de áudio de controle de ganho de pós-instantâneo.</span><span class="sxs-lookup"><span data-stu-id="15a17-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="15a17-139">A unidade desta medida é o dBmo.</span><span class="sxs-lookup"><span data-stu-id="15a17-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="15a17-140">Para uma qualidade aceitável, deve ser menor que 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="15a17-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="15a17-141">Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="15a17-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-143">int</span><span class="sxs-lookup"><span data-stu-id="15a17-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-144">Consulte SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="15a17-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-146">int</span><span class="sxs-lookup"><span data-stu-id="15a17-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-147">Métrica de aprimoramento de perda de retorno de eco.</span><span class="sxs-lookup"><span data-stu-id="15a17-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="15a17-148">A unidade desta medida é o dB.</span><span class="sxs-lookup"><span data-stu-id="15a17-148">The unit for this metric is dB.</span></span> <span data-ttu-id="15a17-149">Valores mais baixos representam menos eco.</span><span class="sxs-lookup"><span data-stu-id="15a17-149">Lower values represent less echo.</span></span> <span data-ttu-id="15a17-150">Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="15a17-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-152">int</span><span class="sxs-lookup"><span data-stu-id="15a17-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-153">Falhas médias por cinco minutos para a renderização Loudspeaker.</span><span class="sxs-lookup"><span data-stu-id="15a17-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="15a17-154">Para uma boa qualidade, deve ser menos de um a cada cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="15a17-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="15a17-155">Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="15a17-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-157">int</span><span class="sxs-lookup"><span data-stu-id="15a17-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-158">Falhas médias por cinco minutos para a captura do microfone.</span><span class="sxs-lookup"><span data-stu-id="15a17-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="15a17-159">Para uma boa qualidade, deve ser menos de um a cada cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="15a17-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="15a17-160">Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="15a17-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-162">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="15a17-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-163">Taxa de descompasso do relógio do dispositivo de microfone, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="15a17-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-165">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="15a17-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-166">Taxa de descompasso do relógio do dispositivo de alto-falante, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="15a17-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-168">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="15a17-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-169">Taxa de descompasso do relógio do dispositivo de alto-falante, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="15a17-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="15a17-170">Média de erro de registro de hora de fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="15a17-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-172">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="15a17-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-173">Erro de carimbo de data/hora médio do fluxo de alto-falante, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="15a17-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-175">smallint</span><span class="sxs-lookup"><span data-stu-id="15a17-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-176">Opção de voz é um modo meio-duplex com capacidade de interrupção reduzida.</span><span class="sxs-lookup"><span data-stu-id="15a17-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="15a17-177">Causas da entrada da opção de voz:</span><span class="sxs-lookup"><span data-stu-id="15a17-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="15a17-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="15a17-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="15a17-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="15a17-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="15a17-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="15a17-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="15a17-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="15a17-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="15a17-182">A causa pode ser uma combinação dessas causas individuais.</span><span class="sxs-lookup"><span data-stu-id="15a17-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="15a17-183">ENTER_VS_FORCEORCONVERGENCE só pode ser habilitado por RegKey para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="15a17-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="15a17-184">O tipo de dados desta coluna foi alterado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15a17-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="15a17-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-187">Causas de um evento Echo:</span><span class="sxs-lookup"><span data-stu-id="15a17-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="15a17-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="15a17-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="15a17-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="15a17-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="15a17-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="15a17-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="15a17-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="15a17-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="15a17-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="15a17-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="15a17-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="15a17-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="15a17-194">A causa pode ser uma combinação dessas causas individuais.</span><span class="sxs-lookup"><span data-stu-id="15a17-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-196">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="15a17-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-197">Porcentagem de tempo em que o eco foi detectado no fluxo de captura do microfone.</span><span class="sxs-lookup"><span data-stu-id="15a17-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="15a17-198">Normalmente, os valores são baixos para fones de ouvido ou fones, e mais altos para telefones do alto-falante ou alto-falantes autônomos.</span><span class="sxs-lookup"><span data-stu-id="15a17-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="15a17-199">Para dispositivos que suportam cancelamento de eco acústico integrado, valores altos indicam vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="15a17-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="15a17-200">Para outros dispositivos, essa métrica não deve ser usada para avaliar a qualidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15a17-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-202">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="15a17-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15a17-203">Porcentagem de tempo quando o eco é detectado no fluxo enviado.</span><span class="sxs-lookup"><span data-stu-id="15a17-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="15a17-204">Uma alta porcentagem de eco em fluxos enviados indica um vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="15a17-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-206">int</span><span class="sxs-lookup"><span data-stu-id="15a17-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-207">Nível de sinal recebido no servidor de mediação do gateway; Isso se aplica apenas ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="15a17-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="15a17-208">A unidade desta medida é o dBoV.</span><span class="sxs-lookup"><span data-stu-id="15a17-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="15a17-209">Para uma boa qualidade, a faixa aceitável deve ser de [-30 a -18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="15a17-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-211">int</span><span class="sxs-lookup"><span data-stu-id="15a17-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-212">Nível de sinal recebido no servidor de mediação do gateway.</span><span class="sxs-lookup"><span data-stu-id="15a17-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="15a17-213">Se aplica apenas ao Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="15a17-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="15a17-214">A unidade desta medida é o dBoV.</span><span class="sxs-lookup"><span data-stu-id="15a17-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="15a17-215">Para uma boa qualidade, a faixa aceitável deve ser menor do que -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="15a17-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-217">int</span><span class="sxs-lookup"><span data-stu-id="15a17-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-218">Controle de ganho automático (AGC) no lado do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="15a17-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-220">float</span><span class="sxs-lookup"><span data-stu-id="15a17-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="15a17-221">O quadrado de raiz média (RMS) do sinal de entrada de até os primeiros 30 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="15a17-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-223">int</span><span class="sxs-lookup"><span data-stu-id="15a17-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15a17-224">Nível de sinal como recebido no canal 1.</span><span class="sxs-lookup"><span data-stu-id="15a17-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="15a17-225">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15a17-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-227">int</span><span class="sxs-lookup"><span data-stu-id="15a17-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15a17-228">Nível de sinal como recebido no canal 2.</span><span class="sxs-lookup"><span data-stu-id="15a17-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="15a17-229">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15a17-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-231">int</span><span class="sxs-lookup"><span data-stu-id="15a17-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15a17-232">Nível de ruído como recebido no canal 1.</span><span class="sxs-lookup"><span data-stu-id="15a17-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="15a17-233">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15a17-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-235">int</span><span class="sxs-lookup"><span data-stu-id="15a17-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15a17-236">Nível de ruído como recebido no canal 2.</span><span class="sxs-lookup"><span data-stu-id="15a17-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="15a17-237">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15a17-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-239">int</span><span class="sxs-lookup"><span data-stu-id="15a17-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15a17-240">Nível de sinal como enviado no canal 1.</span><span class="sxs-lookup"><span data-stu-id="15a17-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="15a17-241">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15a17-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-243">int</span><span class="sxs-lookup"><span data-stu-id="15a17-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15a17-244">Nível de sinal como enviado no canal 2.</span><span class="sxs-lookup"><span data-stu-id="15a17-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="15a17-245">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15a17-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15a17-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-247">int</span><span class="sxs-lookup"><span data-stu-id="15a17-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15a17-248">Nível de ruído como enviado no canal 1.</span><span class="sxs-lookup"><span data-stu-id="15a17-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="15a17-249">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15a17-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15a17-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="15a17-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="15a17-251">int</span><span class="sxs-lookup"><span data-stu-id="15a17-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15a17-252">Nível de ruído como enviado no canal 2.</span><span class="sxs-lookup"><span data-stu-id="15a17-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="15a17-253">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="15a17-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

