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
ms.openlocfilehash: de07393ef9f43346d0c1b4c96dcfdcf33f00513a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="a302e-102">Tabela AudioSignal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a302e-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a302e-103">_**Última modificação do tópico:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="a302e-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="a302e-104">Cada registro representa as métricas do sinal de áudio para um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a302e-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="a302e-105">Geralmente, cada chamada tem dois registros, um é para o chamador e um é para o receptor.</span><span class="sxs-lookup"><span data-stu-id="a302e-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a302e-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a302e-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a302e-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a302e-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a302e-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a302e-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a302e-112">Primário</span><span class="sxs-lookup"><span data-stu-id="a302e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a302e-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a302e-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-115">int</span><span class="sxs-lookup"><span data-stu-id="a302e-115">int</span></span></p></td>
<td><p><span data-ttu-id="a302e-116">Primário</span><span class="sxs-lookup"><span data-stu-id="a302e-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="a302e-117">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a302e-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="a302e-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a302e-120">Primário</span><span class="sxs-lookup"><span data-stu-id="a302e-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="a302e-121">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a302e-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-123">bits</span><span class="sxs-lookup"><span data-stu-id="a302e-123">bit</span></span></p></td>
<td><p><span data-ttu-id="a302e-124">Primário</span><span class="sxs-lookup"><span data-stu-id="a302e-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="a302e-125">0: dados do receptor</span><span class="sxs-lookup"><span data-stu-id="a302e-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="a302e-126">1: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="a302e-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-128">int</span><span class="sxs-lookup"><span data-stu-id="a302e-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-129">Representa o nível de sinal de áudio de controle de ganho de pós-instantâneo.</span><span class="sxs-lookup"><span data-stu-id="a302e-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="a302e-130">A unidade desta medida é o dBmo.</span><span class="sxs-lookup"><span data-stu-id="a302e-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="a302e-131">Para uma qualidade aceitável, deve ser ao menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="a302e-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="a302e-132">Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="a302e-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-134">int</span><span class="sxs-lookup"><span data-stu-id="a302e-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-135">Consulte SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="a302e-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-137">int</span><span class="sxs-lookup"><span data-stu-id="a302e-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-138">Representa o nível de ruído de áudio de controle de ganho de pós-instantâneo.</span><span class="sxs-lookup"><span data-stu-id="a302e-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="a302e-139">A unidade desta medida é o dBmo.</span><span class="sxs-lookup"><span data-stu-id="a302e-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="a302e-140">Para uma qualidade aceitável, deve ser menor que 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="a302e-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="a302e-141">Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="a302e-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-143">int</span><span class="sxs-lookup"><span data-stu-id="a302e-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-144">Consulte SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="a302e-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-146">int</span><span class="sxs-lookup"><span data-stu-id="a302e-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-147">Métrica de aprimoramento de perda de retorno de eco.</span><span class="sxs-lookup"><span data-stu-id="a302e-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="a302e-148">A unidade desta medida é o dB.</span><span class="sxs-lookup"><span data-stu-id="a302e-148">The unit for this metric is dB.</span></span> <span data-ttu-id="a302e-149">Valores mais baixos representam menos eco.</span><span class="sxs-lookup"><span data-stu-id="a302e-149">Lower values represent less echo.</span></span> <span data-ttu-id="a302e-150">Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="a302e-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-152">int</span><span class="sxs-lookup"><span data-stu-id="a302e-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-153">Falhas médias por cinco minutos para a renderização Loudspeaker.</span><span class="sxs-lookup"><span data-stu-id="a302e-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="a302e-154">Para uma boa qualidade, deve ser menos de um a cada cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="a302e-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="a302e-155">Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="a302e-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-157">int</span><span class="sxs-lookup"><span data-stu-id="a302e-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-158">Falhas médias por cinco minutos para a captura do microfone.</span><span class="sxs-lookup"><span data-stu-id="a302e-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="a302e-159">Para uma boa qualidade, deve ser menos de um a cada cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="a302e-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="a302e-160">Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="a302e-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-162">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a302e-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-163">Taxa de descompasso do relógio do dispositivo de microfone, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="a302e-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-165">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a302e-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-166">Taxa de descompasso do relógio do dispositivo de alto-falante, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="a302e-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-168">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a302e-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-169">Taxa de descompasso do relógio do dispositivo de alto-falante, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="a302e-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="a302e-170">Média de erro de registro de hora de fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="a302e-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-172">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a302e-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-173">Erro de carimbo de data/hora médio do fluxo de alto-falante, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="a302e-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-175">smallint</span><span class="sxs-lookup"><span data-stu-id="a302e-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-176">Opção de voz é um modo meio-duplex com capacidade de interrupção reduzida.</span><span class="sxs-lookup"><span data-stu-id="a302e-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="a302e-177">Causas da entrada da opção de voz:</span><span class="sxs-lookup"><span data-stu-id="a302e-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="a302e-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="a302e-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="a302e-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="a302e-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="a302e-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="a302e-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="a302e-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="a302e-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="a302e-182">A causa pode ser uma combinação dessas causas individuais.</span><span class="sxs-lookup"><span data-stu-id="a302e-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="a302e-183">ENTER_VS_FORCEORCONVERGENCE só pode ser habilitado por RegKey para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="a302e-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="a302e-184">O tipo de dados desta coluna foi alterado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a302e-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="a302e-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-187">Causas de um evento Echo:</span><span class="sxs-lookup"><span data-stu-id="a302e-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="a302e-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="a302e-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="a302e-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="a302e-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="a302e-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="a302e-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="a302e-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="a302e-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="a302e-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="a302e-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="a302e-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="a302e-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="a302e-194">A causa pode ser uma combinação dessas causas individuais.</span><span class="sxs-lookup"><span data-stu-id="a302e-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-196">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a302e-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-197">Porcentagem de tempo em que o eco foi detectado no fluxo de captura do microfone.</span><span class="sxs-lookup"><span data-stu-id="a302e-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="a302e-198">Normalmente, os valores são baixos para fones de ouvido ou fones, e mais altos para telefones do alto-falante ou alto-falantes autônomos.</span><span class="sxs-lookup"><span data-stu-id="a302e-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="a302e-199">Para dispositivos que suportam cancelamento de eco acústico integrado, valores altos indicam vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="a302e-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="a302e-200">Para outros dispositivos, essa métrica não deve ser usada para avaliar a qualidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a302e-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-202">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a302e-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a302e-203">Porcentagem de tempo quando o eco é detectado no fluxo enviado.</span><span class="sxs-lookup"><span data-stu-id="a302e-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="a302e-204">Uma alta porcentagem de eco em fluxos enviados indica um vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="a302e-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-206">int</span><span class="sxs-lookup"><span data-stu-id="a302e-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-207">Nível de sinal recebido no servidor de mediação do gateway; Isso se aplica apenas ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a302e-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="a302e-208">A unidade desta medida é o dBoV.</span><span class="sxs-lookup"><span data-stu-id="a302e-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="a302e-209">Para uma boa qualidade, a faixa aceitável deve ser de [-30 a -18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="a302e-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-211">int</span><span class="sxs-lookup"><span data-stu-id="a302e-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-212">Nível de sinal recebido no servidor de mediação do gateway.</span><span class="sxs-lookup"><span data-stu-id="a302e-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="a302e-213">Se aplica apenas ao Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="a302e-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="a302e-214">A unidade desta medida é o dBoV.</span><span class="sxs-lookup"><span data-stu-id="a302e-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="a302e-215">Para uma boa qualidade, a faixa aceitável deve ser menor do que -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="a302e-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-217">int</span><span class="sxs-lookup"><span data-stu-id="a302e-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-218">Controle de ganho automático (AGC) no lado do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a302e-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-220">float</span><span class="sxs-lookup"><span data-stu-id="a302e-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a302e-221">O quadrado de raiz média (RMS) do sinal de entrada de até os primeiros 30 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="a302e-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-223">int</span><span class="sxs-lookup"><span data-stu-id="a302e-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a302e-224">Nível de sinal como recebido no canal 1.</span><span class="sxs-lookup"><span data-stu-id="a302e-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="a302e-225">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a302e-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-227">int</span><span class="sxs-lookup"><span data-stu-id="a302e-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a302e-228">Nível de sinal como recebido no canal 2.</span><span class="sxs-lookup"><span data-stu-id="a302e-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="a302e-229">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a302e-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-231">int</span><span class="sxs-lookup"><span data-stu-id="a302e-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a302e-232">Nível de ruído como recebido no canal 1.</span><span class="sxs-lookup"><span data-stu-id="a302e-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="a302e-233">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a302e-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-235">int</span><span class="sxs-lookup"><span data-stu-id="a302e-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a302e-236">Nível de ruído como recebido no canal 2.</span><span class="sxs-lookup"><span data-stu-id="a302e-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="a302e-237">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a302e-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-239">int</span><span class="sxs-lookup"><span data-stu-id="a302e-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a302e-240">Nível de sinal como enviado no canal 1.</span><span class="sxs-lookup"><span data-stu-id="a302e-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="a302e-241">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a302e-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-243">int</span><span class="sxs-lookup"><span data-stu-id="a302e-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a302e-244">Nível de sinal como enviado no canal 2.</span><span class="sxs-lookup"><span data-stu-id="a302e-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="a302e-245">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a302e-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a302e-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-247">int</span><span class="sxs-lookup"><span data-stu-id="a302e-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a302e-248">Nível de ruído como enviado no canal 1.</span><span class="sxs-lookup"><span data-stu-id="a302e-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="a302e-249">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a302e-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a302e-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="a302e-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="a302e-251">int</span><span class="sxs-lookup"><span data-stu-id="a302e-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a302e-252">Nível de ruído como enviado no canal 2.</span><span class="sxs-lookup"><span data-stu-id="a302e-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="a302e-253">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a302e-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

