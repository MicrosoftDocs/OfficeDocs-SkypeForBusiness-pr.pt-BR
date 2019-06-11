---
title: 'Lync Server 2013: Tabela AudioSignal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6605a25191906660bbad11908f754a81360c893
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="a6e66-102">Tabela AudioSignal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6e66-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6e66-103">_**Tópico da última modificação:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="a6e66-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="a6e66-104">Cada registro representa as métricas do sinal de áudio para um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a6e66-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="a6e66-105">Geralmente, cada chamada tem dois registros, um é para o chamador e um é para o receptor.</span><span class="sxs-lookup"><span data-stu-id="a6e66-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6e66-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a6e66-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a6e66-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a6e66-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a6e66-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a6e66-112">Primária</span><span class="sxs-lookup"><span data-stu-id="a6e66-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a6e66-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a6e66-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-115">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-115">int</span></span></p></td>
<td><p><span data-ttu-id="a6e66-116">Primária</span><span class="sxs-lookup"><span data-stu-id="a6e66-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="a6e66-117">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a6e66-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="a6e66-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a6e66-120">Primária</span><span class="sxs-lookup"><span data-stu-id="a6e66-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="a6e66-121">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a6e66-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-123">bit</span><span class="sxs-lookup"><span data-stu-id="a6e66-123">bit</span></span></p></td>
<td><p><span data-ttu-id="a6e66-124">Primária</span><span class="sxs-lookup"><span data-stu-id="a6e66-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="a6e66-125">0: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="a6e66-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="a6e66-126">1: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="a6e66-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-128">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-129">Representa o nível de sinal de áudio de controle de ganho de cruz analógico.</span><span class="sxs-lookup"><span data-stu-id="a6e66-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="a6e66-130">A unidade para essa métrica é dBmo.</span><span class="sxs-lookup"><span data-stu-id="a6e66-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="a6e66-131">Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="a6e66-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="a6e66-132">Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</span><span class="sxs-lookup"><span data-stu-id="a6e66-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-134">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-135">Consulte SendSignalLevel.</span><span class="sxs-lookup"><span data-stu-id="a6e66-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-137">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-138">Representa o nível de ruído de áudio de controle de ganho analógicos.</span><span class="sxs-lookup"><span data-stu-id="a6e66-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="a6e66-139">A unidade para essa métrica é dBmo.</span><span class="sxs-lookup"><span data-stu-id="a6e66-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="a6e66-140">Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="a6e66-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="a6e66-141">Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</span><span class="sxs-lookup"><span data-stu-id="a6e66-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-143">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-144">Consulte SendNoiseLevel.</span><span class="sxs-lookup"><span data-stu-id="a6e66-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-146">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-147">Métrica de aprimoramento de perda de retorno de eco.</span><span class="sxs-lookup"><span data-stu-id="a6e66-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="a6e66-148">A unidade para essa métrica é dB.</span><span class="sxs-lookup"><span data-stu-id="a6e66-148">The unit for this metric is dB.</span></span> <span data-ttu-id="a6e66-149">Valores inferiores representam menos eco.</span><span class="sxs-lookup"><span data-stu-id="a6e66-149">Lower values represent less echo.</span></span> <span data-ttu-id="a6e66-150">Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</span><span class="sxs-lookup"><span data-stu-id="a6e66-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-152">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-153">Média de falhas por cinco minutos para a renderização de alto-falante.</span><span class="sxs-lookup"><span data-stu-id="a6e66-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="a6e66-154">Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="a6e66-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="a6e66-155">Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="a6e66-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-157">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-158">Média de falhas por cinco minutos para a captura de microfone.</span><span class="sxs-lookup"><span data-stu-id="a6e66-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="a6e66-159">Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="a6e66-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="a6e66-160">Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="a6e66-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-162">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="a6e66-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-163">Taxa de descompasso do relógio do dispositivo de microfone, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="a6e66-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-165">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="a6e66-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-166">Taxa de descompasso do relógio do dispositivo de alto-falante, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="a6e66-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-168">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="a6e66-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-169">Taxa de descompasso do relógio do dispositivo de alto-falante, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="a6e66-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="a6e66-170">Erro de carimbo de data/hora médio do fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="a6e66-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-172">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="a6e66-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-173">Média de um erro de carimbo de data/hora do fluxo de alto-falante, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="a6e66-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-175">smallint</span><span class="sxs-lookup"><span data-stu-id="a6e66-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-176">A opção de voz é um modo Half-duplex com capacidade de interrupção reduzida.</span><span class="sxs-lookup"><span data-stu-id="a6e66-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="a6e66-177">Causas da entrada da opção de voz:</span><span class="sxs-lookup"><span data-stu-id="a6e66-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="a6e66-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="a6e66-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="a6e66-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="a6e66-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="a6e66-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="a6e66-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="a6e66-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="a6e66-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="a6e66-182">A causa pode ser uma combinação dessas causas individuais.</span><span class="sxs-lookup"><span data-stu-id="a6e66-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="a6e66-183">ENTER_VS_FORCEORCONVERGENCE só pode ser habilitado por RegKey para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="a6e66-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="a6e66-184">O tipo de dados para esta coluna foi alterado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6e66-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="a6e66-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-187">Causas de um evento de eco:</span><span class="sxs-lookup"><span data-stu-id="a6e66-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="a6e66-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="a6e66-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="a6e66-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="a6e66-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="a6e66-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="a6e66-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="a6e66-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="a6e66-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="a6e66-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="a6e66-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="a6e66-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="a6e66-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="a6e66-194">A causa pode ser uma combinação dessas causas individuais.</span><span class="sxs-lookup"><span data-stu-id="a6e66-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-196">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="a6e66-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-p109">Porcentagem de tempo em que o eco foi detectado no fluxo de captura do microfone. Normalmente, os valores são baixos para fones de ouvido ou celulares e mais altos para viva voz e auto falante. Para dispositivos que suportam cancelamento de eco acústico na placa, os altos níveis indicam vazamento de eco. Para outros dispositivos, essa métrica não deve ser utilizada para avaliar a qualidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a6e66-p109">Percentage of time when echo was detected in the microphone capture stream. Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers. For devices that support on-board acoustic echo cancellation, high values indicate echo leak. For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-202">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="a6e66-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6e66-203">Porcentagem de tempo em que o eco é detectado no fluxo de envio.</span><span class="sxs-lookup"><span data-stu-id="a6e66-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="a6e66-204">Alta porcentagem de eco em enviar transmite uma indicação de vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="a6e66-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-206">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-207">Nível de sinal recebido no servidor de mediação do gateway; Isso se aplica apenas ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a6e66-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="a6e66-208">A unidade desta métrica é dBoV.</span><span class="sxs-lookup"><span data-stu-id="a6e66-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="a6e66-209">Para ter uma boa qualidade, o intervalo aceitável deve ser [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="a6e66-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-211">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-212">Nível de sinal recebido no servidor de mediação do gateway.</span><span class="sxs-lookup"><span data-stu-id="a6e66-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="a6e66-213">Isso se aplica apenas ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a6e66-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="a6e66-214">A unidade desta métrica é dBoV.</span><span class="sxs-lookup"><span data-stu-id="a6e66-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="a6e66-215">Para ter uma boa qualidade, o intervalo aceitável deve ser menor do que-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="a6e66-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-217">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-218">Controle de ganho automático (AGC) no lado do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="a6e66-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-220">float</span><span class="sxs-lookup"><span data-stu-id="a6e66-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a6e66-221">O quadrado de raiz média (RMS) do sinal de entrada de até os primeiros 30 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="a6e66-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-223">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6e66-224">Nível de sinal como recebido no canal 1.</span><span class="sxs-lookup"><span data-stu-id="a6e66-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="a6e66-225">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6e66-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-227">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6e66-228">Nível de sinal como recebido no canal 2.</span><span class="sxs-lookup"><span data-stu-id="a6e66-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="a6e66-229">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6e66-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-231">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6e66-232">Nível de ruído como recebido no canal 1.</span><span class="sxs-lookup"><span data-stu-id="a6e66-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="a6e66-233">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6e66-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-235">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6e66-236">Nível de ruído como recebido no canal 2.</span><span class="sxs-lookup"><span data-stu-id="a6e66-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="a6e66-237">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6e66-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-239">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6e66-240">Nível de sinal como enviado no canal 1.</span><span class="sxs-lookup"><span data-stu-id="a6e66-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="a6e66-241">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6e66-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-243">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6e66-244">Nível de sinal como enviado no canal 2.</span><span class="sxs-lookup"><span data-stu-id="a6e66-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="a6e66-245">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6e66-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e66-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-247">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6e66-248">Nível de ruído enviado no canal 1.</span><span class="sxs-lookup"><span data-stu-id="a6e66-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="a6e66-249">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6e66-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e66-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="a6e66-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="a6e66-251">int</span><span class="sxs-lookup"><span data-stu-id="a6e66-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a6e66-252">Nível de ruído enviado no canal 2.</span><span class="sxs-lookup"><span data-stu-id="a6e66-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="a6e66-253">Esta coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6e66-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

