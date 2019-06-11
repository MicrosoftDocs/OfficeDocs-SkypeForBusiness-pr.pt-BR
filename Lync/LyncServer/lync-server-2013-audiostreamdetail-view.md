---
title: 'Lync Server 2013: modo de exibição AudioStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10992007c76321f8ed3b436b9786cbef840173ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="ba330-102">Exibição AudioStreamDetail no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba330-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba330-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ba330-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ba330-104">A exibição AudioStreamDetail armazena informações sobre cada fluxo de áudio no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ba330-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="ba330-105">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba330-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba330-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="ba330-106">Column</span></span></th>
<th><span data-ttu-id="ba330-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="ba330-107">Data Type</span></span></th>
<th><span data-ttu-id="ba330-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ba330-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba330-109">Sessiontime</span><span class="sxs-lookup"><span data-stu-id="ba330-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="ba330-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ba330-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ba330-111">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ba330-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="ba330-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="ba330-113">int</span><span class="sxs-lookup"><span data-stu-id="ba330-113">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-114">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ba330-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-115">Streamid</span><span class="sxs-lookup"><span data-stu-id="ba330-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="ba330-116">int</span><span class="sxs-lookup"><span data-stu-id="ba330-116">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-117">ID exclusiva dentro de uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="ba330-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-118">StartTime </span><span class="sxs-lookup"><span data-stu-id="ba330-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="ba330-119">datetime</span><span class="sxs-lookup"><span data-stu-id="ba330-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="ba330-120">Hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="ba330-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="ba330-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="ba330-122">datetime</span><span class="sxs-lookup"><span data-stu-id="ba330-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="ba330-123">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="ba330-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="ba330-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="ba330-125">bit</span><span class="sxs-lookup"><span data-stu-id="ba330-125">bit</span></span></p></td>
<td><p><span data-ttu-id="ba330-126">Categoria do diálogo: 0 é o servidor do Lync para o trecho do servidor de mediação; 1 é o servidor de mediação para a perna do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="ba330-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="ba330-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="ba330-128">bit</span><span class="sxs-lookup"><span data-stu-id="ba330-128">bit</span></span></p></td>
<td><p><span data-ttu-id="ba330-129">Sinalizador que indica se a chamada foi ignorada ou não.</span><span class="sxs-lookup"><span data-stu-id="ba330-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="ba330-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="ba330-131">int</span><span class="sxs-lookup"><span data-stu-id="ba330-131">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-132">Se presente, indica por que uma chamada não foi ignorada mesmo se as IDs de bypass forem atendidas.</span><span class="sxs-lookup"><span data-stu-id="ba330-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="ba330-133">Somente um valor é definido:</span><span class="sxs-lookup"><span data-stu-id="ba330-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="ba330-134">0x0001 – ID de bypass desconhecido para o adaptador de rede padrão.</span><span class="sxs-lookup"><span data-stu-id="ba330-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="ba330-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="ba330-136">int</span><span class="sxs-lookup"><span data-stu-id="ba330-136">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-137">Prioridade da chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="ba330-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="ba330-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba330-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba330-140">FQDN do pool de chamadas.</span><span class="sxs-lookup"><span data-stu-id="ba330-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="ba330-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="ba330-142">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba330-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba330-143">FQDN do pool do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-144">Chamador</span><span class="sxs-lookup"><span data-stu-id="ba330-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="ba330-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ba330-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ba330-146">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-147">Receptor</span><span class="sxs-lookup"><span data-stu-id="ba330-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="ba330-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ba330-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ba330-149">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="ba330-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="ba330-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba330-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba330-152">Cadeia de caracteres do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="ba330-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="ba330-154">smallint</span><span class="sxs-lookup"><span data-stu-id="ba330-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="ba330-155">Tipo de agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="ba330-156">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="ba330-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="ba330-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="ba330-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ba330-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ba330-159">Categoria do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="ba330-160">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="ba330-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="ba330-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="ba330-162">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba330-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba330-163">Cadeia de caracteres do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="ba330-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="ba330-165">smallint</span><span class="sxs-lookup"><span data-stu-id="ba330-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="ba330-166">Tipo de agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-166">Type of callee’s user agent.</span></span> <span data-ttu-id="ba330-167">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="ba330-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="ba330-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="ba330-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ba330-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ba330-170">Categoria do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-170">Category of callee’s user agent.</span></span> <span data-ttu-id="ba330-171">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="ba330-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="ba330-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="ba330-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba330-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba330-174">Nome do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="ba330-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="ba330-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba330-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba330-177">Nome do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="ba330-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="ba330-179">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba330-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba330-180">Sistema operacional (SO) do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="ba330-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="ba330-182">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba330-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba330-183">Sistema operacional (SO) do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="ba330-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="ba330-185">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba330-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba330-186">Nome da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="ba330-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="ba330-188">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba330-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba330-189">Nome da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="ba330-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="ba330-191">smallint</span><span class="sxs-lookup"><span data-stu-id="ba330-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="ba330-192">Número de núcleos da CPU no ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="ba330-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="ba330-194">smallint</span><span class="sxs-lookup"><span data-stu-id="ba330-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="ba330-195">Número de núcleos da CPU no ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="ba330-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="ba330-197">int</span><span class="sxs-lookup"><span data-stu-id="ba330-197">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-198">Velocidade do processador da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="ba330-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="ba330-200">int</span><span class="sxs-lookup"><span data-stu-id="ba330-200">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-201">Velocidade do processador da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="ba330-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="ba330-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba330-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba330-204">Indica se o sistema do chamador está em execução em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="ba330-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="ba330-205">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ba330-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="ba330-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="ba330-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba330-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba330-208">Indica se o sistema do chamador está em execução em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="ba330-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="ba330-209">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ba330-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="ba330-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba330-211">Chave de correlação.</span><span class="sxs-lookup"><span data-stu-id="ba330-211">Correlation key.</span></span> <span data-ttu-id="ba330-212">Referenciado pela <a href="lync-server-2013-sessioncorrelation-table.md">tabela SessionCorrelation no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ba330-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="ba330-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="ba330-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba330-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba330-215">Informações sobre o caminho de mídia, como direta ou retransmitida.</span><span class="sxs-lookup"><span data-stu-id="ba330-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="ba330-216">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ba330-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="ba330-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="ba330-218">int</span><span class="sxs-lookup"><span data-stu-id="ba330-218">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-219">Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-219">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="ba330-220">Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.</span><span class="sxs-lookup"><span data-stu-id="ba330-220">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="ba330-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="ba330-222">int</span><span class="sxs-lookup"><span data-stu-id="ba330-222">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-223">Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-223">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="ba330-224">Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.</span><span class="sxs-lookup"><span data-stu-id="ba330-224">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-225">SMTP</span><span class="sxs-lookup"><span data-stu-id="ba330-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="ba330-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba330-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba330-227">Tipo de transporte: 0 é UDP; 1 é o TCP.</span><span class="sxs-lookup"><span data-stu-id="ba330-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="ba330-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ba330-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="ba330-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ba330-230">Endereço IP do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-230">IP address of the caller.</span></span> <span data-ttu-id="ba330-231">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="ba330-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="ba330-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="ba330-233">int</span><span class="sxs-lookup"><span data-stu-id="ba330-233">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-234">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="ba330-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="ba330-236">bit</span><span class="sxs-lookup"><span data-stu-id="ba330-236">bit</span></span></p></td>
<td><p><span data-ttu-id="ba330-237">Indica se o chamador está dentro da rede de intervalo: 1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="ba330-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="ba330-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ba330-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="ba330-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ba330-240">Endereço IP do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-240">IP address of the callee.</span></span> <span data-ttu-id="ba330-241">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="ba330-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="ba330-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="ba330-243">int</span><span class="sxs-lookup"><span data-stu-id="ba330-243">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-244">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="ba330-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="ba330-246">bit</span><span class="sxs-lookup"><span data-stu-id="ba330-246">bit</span></span></p></td>
<td><p><span data-ttu-id="ba330-247">Indica se a chamada está dentro do intervalo de rede: 1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="ba330-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="ba330-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="ba330-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba330-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba330-250">Nome do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="ba330-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="ba330-252">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba330-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba330-253">Nome do país/região do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="ba330-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="ba330-255">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba330-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba330-256">Nome do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="ba330-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="ba330-258">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="ba330-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ba330-259">Nome do país/região do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="ba330-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ba330-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="ba330-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ba330-262">Endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="ba330-263">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ba330-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="ba330-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="ba330-265">int</span><span class="sxs-lookup"><span data-stu-id="ba330-265">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-266">Porta usada no serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="ba330-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ba330-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="ba330-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ba330-269">Chave de endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="ba330-270">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ba330-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="ba330-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="ba330-272">int</span><span class="sxs-lookup"><span data-stu-id="ba330-272">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-273">Porta usada no serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="ba330-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="ba330-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba330-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba330-276">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="ba330-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="ba330-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba330-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba330-279">Nome do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="ba330-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ba330-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba330-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba330-282">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="ba330-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="ba330-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba330-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba330-285">O nome do driver de dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="ba330-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="ba330-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba330-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba330-288">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="ba330-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="ba330-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba330-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba330-291">Nome do dispositivo de renderização do Calle.</span><span class="sxs-lookup"><span data-stu-id="ba330-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="ba330-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ba330-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba330-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba330-294">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="ba330-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ba330-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ba330-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ba330-297">Chame o nome do driver do dispositivo de processamento do recurso.</span><span class="sxs-lookup"><span data-stu-id="ba330-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="ba330-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="ba330-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba330-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba330-300">Tipo de conexão de rede do chamador: 0 é cabeado, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="ba330-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="ba330-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="ba330-302">bit</span><span class="sxs-lookup"><span data-stu-id="ba330-302">bit</span></span></p></td>
<td><p><span data-ttu-id="ba330-303">Indica se o chamador está conectado por meio de uma rede privada virtual: 1 é uma rede virtual privada (VPN), 0 não é VPN.</span><span class="sxs-lookup"><span data-stu-id="ba330-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="ba330-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="ba330-305">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="ba330-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="ba330-306">Velocidade do link de rede para o ponto de extremidade do chamador em bps.</span><span class="sxs-lookup"><span data-stu-id="ba330-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="ba330-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="ba330-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba330-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba330-309">Tipo de conexão de rede do chamador: 0 é cabeado, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="ba330-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="ba330-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="ba330-311">bit</span><span class="sxs-lookup"><span data-stu-id="ba330-311">bit</span></span></p></td>
<td><p><span data-ttu-id="ba330-312">Indica se o chamador está conectado por meio de uma rede privada virtual: 1 é uma rede virtual privada (VPN), 0 não é VPN.</span><span class="sxs-lookup"><span data-stu-id="ba330-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="ba330-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="ba330-314">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="ba330-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="ba330-315">Velocidade do link de rede para o ponto de extremidade do chamador em bps.</span><span class="sxs-lookup"><span data-stu-id="ba330-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="ba330-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="ba330-317">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-318">O MOS de conversa de banda estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="ba330-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="ba330-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="ba330-320">int</span><span class="sxs-lookup"><span data-stu-id="ba330-320">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-321">A largura de banda real aplicada ao fluxo de envio do lado fornecido tem várias configurações de política (ativar, API, SDP, servidor de política e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="ba330-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="ba330-322">Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda mais econômica com base na estimativa de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="ba330-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="ba330-323">Isso é basicamente a largura de banda máxima que o fluxo de envio pode ter limites de bloqueio impostos pela estimativa da largura de banda</span><span class="sxs-lookup"><span data-stu-id="ba330-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="ba330-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="ba330-325">int</span><span class="sxs-lookup"><span data-stu-id="ba330-325">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-326">Tremulação média de rede de estatísticas de protocolo de controle de tempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="ba330-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="ba330-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="ba330-328">int</span><span class="sxs-lookup"><span data-stu-id="ba330-328">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-329">Maior tremulação de rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="ba330-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="ba330-331">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ba330-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="ba330-332">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="ba330-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="ba330-334">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ba330-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="ba330-335">Perda máxima de pacote observado durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="ba330-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="ba330-337">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ba330-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="ba330-338">Densidade média de perda de pacote durante intermitências de perdas durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="ba330-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="ba330-340">int</span><span class="sxs-lookup"><span data-stu-id="ba330-340">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-341">Duração média da perda de pacote durante intermitências de perdas durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="ba330-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="ba330-343">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ba330-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="ba330-344">Densidade média de perda de pacote durante intervalos entre intermitências de perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="ba330-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="ba330-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="ba330-346">int</span><span class="sxs-lookup"><span data-stu-id="ba330-346">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-347">Duração média de lacunas entre intermitências de perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="ba330-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="ba330-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="ba330-349">int</span><span class="sxs-lookup"><span data-stu-id="ba330-349">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-350">Contagem de pacotes para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="ba330-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-351">Largura de banda</span><span class="sxs-lookup"><span data-stu-id="ba330-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="ba330-352">int</span><span class="sxs-lookup"><span data-stu-id="ba330-352">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-353">Estimativas de largura de banda para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="ba330-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="ba330-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="ba330-355">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-356">Degradação do MOS de rede para toda a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="ba330-357">O intervalo é de 0,0 a 5,0.</span><span class="sxs-lookup"><span data-stu-id="ba330-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="ba330-358">Essa métrica mostra o valor que o MOS de rede foi reduzido devido à instabilidade e à perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="ba330-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="ba330-359">Para ter uma qualidade aceitável, ele deve ser menor do que 0,5.</span><span class="sxs-lookup"><span data-stu-id="ba330-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="ba330-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="ba330-361">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-362">Degradação do MOS de rede máxima durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="ba330-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="ba330-364">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-365">Degradação de MOS de rede causada pela tremulação.</span><span class="sxs-lookup"><span data-stu-id="ba330-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="ba330-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="ba330-367">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-368">Degradação de MOS de rede causada por perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="ba330-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="ba330-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="ba330-370">int</span><span class="sxs-lookup"><span data-stu-id="ba330-370">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-371">O codec de áudio usado para a chamada, referenciado pela <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="ba330-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="ba330-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="ba330-373">int</span><span class="sxs-lookup"><span data-stu-id="ba330-373">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-374">Taxa de amostragem do fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="ba330-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="ba330-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ba330-376">int</span><span class="sxs-lookup"><span data-stu-id="ba330-376">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-377">O nível de sinal de áudio pós-analógico de controle de ganho para o áudio enviado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="ba330-378">A unidade para essa métrica é dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="ba330-379">Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="ba330-380">Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba330-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="ba330-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ba330-382">int</span><span class="sxs-lookup"><span data-stu-id="ba330-382">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-383">Nível de sinal de áudio para o áudio recebido pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="ba330-384">A unidade para essa métrica é dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="ba330-385">Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="ba330-386">Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba330-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="ba330-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ba330-388">int</span><span class="sxs-lookup"><span data-stu-id="ba330-388">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-389">Nível de ruído de áudio de controle de ganho analógico-analógico para o áudio enviado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="ba330-390">A unidade para essa métrica é dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="ba330-391">Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="ba330-392">Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba330-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="ba330-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ba330-394">int</span><span class="sxs-lookup"><span data-stu-id="ba330-394">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-395">Nível de ruído de áudio de controle de ganho analógico-analógico para o áudio recebido pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="ba330-396">A unidade para essa métrica é dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="ba330-397">Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="ba330-398">Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba330-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="ba330-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="ba330-400">int</span><span class="sxs-lookup"><span data-stu-id="ba330-400">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-401">Aprimoramento da perda de retorno de eco para o chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="ba330-402">A unidade para essa métrica é dB.</span><span class="sxs-lookup"><span data-stu-id="ba330-402">The unit for this metric is dB.</span></span> <span data-ttu-id="ba330-403">Valores inferiores representam menos eco.</span><span class="sxs-lookup"><span data-stu-id="ba330-403">Lower values represent less echo.</span></span> <span data-ttu-id="ba330-404">Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba330-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="ba330-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="ba330-406">int</span><span class="sxs-lookup"><span data-stu-id="ba330-406">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-407">Média de falhas por cinco minutos para a renderização de alto-falante do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="ba330-408">Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="ba330-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="ba330-409">Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba330-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="ba330-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="ba330-411">int</span><span class="sxs-lookup"><span data-stu-id="ba330-411">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-412">Média de falhas por cinco minutos para a captura de microfone do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="ba330-413">Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="ba330-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="ba330-414">Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba330-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="ba330-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="ba330-416">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-417">Taxa de descompasso do relógio do dispositivo de microfone do chamador, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="ba330-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="ba330-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="ba330-419">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-420">Taxa de descompasso do relógio do dispositivo de alto-falante do chamador em relação ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="ba330-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="ba330-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="ba330-422">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-423">Erro de carimbo de data/hora médio do fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="ba330-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="ba330-425">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-426">Média do alto-falante do chamador processar carimbo de data/hora do fluxo, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="ba330-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="ba330-428">smallint</span><span class="sxs-lookup"><span data-stu-id="ba330-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="ba330-429">A opção de voz é um modo Half-duplex com capacidade de interrupção reduzida.</span><span class="sxs-lookup"><span data-stu-id="ba330-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="ba330-430">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ba330-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="ba330-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="ba330-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba330-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba330-433">Causa de um evento de eco para o chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="ba330-434">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ba330-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="ba330-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="ba330-436">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-437">Porcentagem de tempo em que o eco é detectado no fluxo de captura de microfone do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="ba330-438">Se o fone de ouvido estiver sendo usado, o valor deve ser baixo.</span><span class="sxs-lookup"><span data-stu-id="ba330-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="ba330-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="ba330-440">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-441">Porcentagem de tempo em que o eco é detectado no fluxo de envio do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="ba330-442">Alta porcentagem de eco em enviar transmite uma indicação de vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="ba330-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="ba330-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ba330-444">int</span><span class="sxs-lookup"><span data-stu-id="ba330-444">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-445">Nível de sinal recebido no servidor de mediação do gateway para o áudio do chamador; Isso se aplica apenas ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="ba330-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="ba330-446">A unidade desta métrica é dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba330-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="ba330-447">Para ter uma boa qualidade, o intervalo aceitável deve ser de-30 a-18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba330-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="ba330-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ba330-449">int</span><span class="sxs-lookup"><span data-stu-id="ba330-449">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-450">Nível de sinal recebido no servidor de mediação do gateway para o áudio do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="ba330-451">Isso se aplica apenas ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="ba330-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="ba330-452">A unidade desta métrica é dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba330-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="ba330-453">Para ter uma boa qualidade, o intervalo aceitável deve ser menor do que-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba330-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="ba330-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="ba330-455">int</span><span class="sxs-lookup"><span data-stu-id="ba330-455">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-456">Controle de ganho automático (AGC) no lado do servidor de mediação aplicado ao áudio do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="ba330-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="ba330-458">float</span><span class="sxs-lookup"><span data-stu-id="ba330-458">float</span></span></p></td>
<td><p><span data-ttu-id="ba330-459">A base média (RMS) do sinal de entrada para o chamador para até os primeiros 30 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="ba330-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ba330-461">int</span><span class="sxs-lookup"><span data-stu-id="ba330-461">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-462">Representa o nível de sinal de áudio de controle de ganho de cruz analógico para o áudio enviado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="ba330-463">A unidade para essa métrica é dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="ba330-464">Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="ba330-465">Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba330-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="ba330-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ba330-467">int</span><span class="sxs-lookup"><span data-stu-id="ba330-467">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-468">Nível de sinal de áudio para o áudio que o chama recebido.</span><span class="sxs-lookup"><span data-stu-id="ba330-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="ba330-469">A unidade para essa métrica é dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="ba330-470">Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="ba330-471">Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba330-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="ba330-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ba330-473">int</span><span class="sxs-lookup"><span data-stu-id="ba330-473">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-474">Nível de ruído de áudio de controle de ganho analógico-analógico para o áudio enviado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="ba330-475">A unidade para essa métrica é dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="ba330-476">Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="ba330-477">Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba330-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="ba330-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ba330-479">int</span><span class="sxs-lookup"><span data-stu-id="ba330-479">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-480">Nível de ruído de áudio de controle de ganho analógico-analógico para o áudio que o chamador recebeu.</span><span class="sxs-lookup"><span data-stu-id="ba330-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="ba330-481">A unidade para essa métrica é dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="ba330-482">Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo.</span><span class="sxs-lookup"><span data-stu-id="ba330-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="ba330-483">Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba330-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="ba330-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="ba330-485">int</span><span class="sxs-lookup"><span data-stu-id="ba330-485">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-486">Aprimoramento da perda de retorno de eco para o chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="ba330-487">A unidade para essa métrica é dB.</span><span class="sxs-lookup"><span data-stu-id="ba330-487">The unit for this metric is dB.</span></span> <span data-ttu-id="ba330-488">Valores inferiores representam menos eco.</span><span class="sxs-lookup"><span data-stu-id="ba330-488">Lower values represent less echo.</span></span> <span data-ttu-id="ba330-489">Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba330-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="ba330-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="ba330-491">int</span><span class="sxs-lookup"><span data-stu-id="ba330-491">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-492">Média de falhas por cinco minutos para a renderização do alto-falante do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="ba330-493">Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="ba330-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="ba330-494">Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba330-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="ba330-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="ba330-496">int</span><span class="sxs-lookup"><span data-stu-id="ba330-496">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-497">Média de falhas por cinco minutos para a captura de microfone do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="ba330-498">Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="ba330-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="ba330-499">Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="ba330-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="ba330-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="ba330-501">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-502">Taxa de descompasso do relógio do dispositivo de microfone do chamador, em relação ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="ba330-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="ba330-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="ba330-504">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-505">Taxa de descompasso do relógio do dispositivo de alto-falante do chamador, em relação ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="ba330-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="ba330-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="ba330-507">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-508">Erro de carimbo de data/hora médio do fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="ba330-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="ba330-510">decimal (9; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-511">Média do erro de carimbo de data/hora do fluxo de processamento do palestrante em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="ba330-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="ba330-513">smallint</span><span class="sxs-lookup"><span data-stu-id="ba330-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="ba330-514">A opção de voz é um modo Half-duplex com capacidade de interrupção reduzida.</span><span class="sxs-lookup"><span data-stu-id="ba330-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="ba330-515">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ba330-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="ba330-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="ba330-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba330-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba330-518">Causas de um evento de eco para o chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="ba330-519">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ba330-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="ba330-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="ba330-521">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-522">Porcentagem de tempo em que o eco é detectado no fluxo de captura do microfone do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="ba330-523">Se o fone de ouvido estiver sendo usado, o valor deve ser baixo.</span><span class="sxs-lookup"><span data-stu-id="ba330-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="ba330-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="ba330-525">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-526">Porcentagem de tempo em que o eco é detectado no fluxo enviado do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="ba330-527">Alta porcentagem de eco em enviar transmite uma indicação de vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="ba330-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="ba330-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="ba330-529">int</span><span class="sxs-lookup"><span data-stu-id="ba330-529">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-530">Nível de sinal recebido no servidor de mediação do gateway para o áudio do chamador; Isso se aplica apenas ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="ba330-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="ba330-531">A unidade desta métrica é dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba330-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="ba330-532">Para ter uma boa qualidade, o intervalo aceitável deve ser [-30 a-18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba330-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="ba330-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="ba330-534">int</span><span class="sxs-lookup"><span data-stu-id="ba330-534">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-535">Nível de sinal recebido no servidor de mediação do gateway para o áudio do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="ba330-536">Isso se aplica apenas ao servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="ba330-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="ba330-537">A unidade desta métrica é dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba330-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="ba330-538">Para ter uma boa qualidade, o intervalo aceitável deve ser menor do que-50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="ba330-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="ba330-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="ba330-540">int</span><span class="sxs-lookup"><span data-stu-id="ba330-540">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-541">Controle de ganho automático (AGC) no lado do servidor de mediação aplicado ao áudio do chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="ba330-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="ba330-543">float</span><span class="sxs-lookup"><span data-stu-id="ba330-543">float</span></span></p></td>
<td><p><span data-ttu-id="ba330-544">A base média (RMS) do sinal de entrada para o receptor para até os primeiros 30 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="ba330-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="ba330-546">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-547">Índice médio de amostras ocultas geradas pelo reparo de áudio para amostras típicas.</span><span class="sxs-lookup"><span data-stu-id="ba330-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="ba330-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="ba330-549">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-550">Índice médio de amostras ampliadas geradas pelo reparo de áudio para amostras típicas.</span><span class="sxs-lookup"><span data-stu-id="ba330-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="ba330-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="ba330-552">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-553">Índice médio de amostras compactadas geradas pelo reparo de áudio para amostras típicas.</span><span class="sxs-lookup"><span data-stu-id="ba330-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-554">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="ba330-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="ba330-555">int</span><span class="sxs-lookup"><span data-stu-id="ba330-555">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-556">Tempo de ida e volta das estatísticas do RTCP.</span><span class="sxs-lookup"><span data-stu-id="ba330-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="ba330-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="ba330-558">int</span><span class="sxs-lookup"><span data-stu-id="ba330-558">int</span></span></p></td>
<td><p><span data-ttu-id="ba330-559">Tempo máximo de ida e volta do fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="ba330-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="ba330-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="ba330-561">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-562">Banda larga médio de um MOS de rede para a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="ba330-563">Essa métrica depende da perda de pacotes, da tremulação e do codec usados.</span><span class="sxs-lookup"><span data-stu-id="ba330-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="ba330-564">O intervalo é de 1,0 a 5,0.</span><span class="sxs-lookup"><span data-stu-id="ba330-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="ba330-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="ba330-566">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-567">Banda larga de rede mínima para a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="ba330-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="ba330-569">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-570">Pontuação estimada banda larga de escuta da MOS para áudio enviado, incluindo o nível de fala, o nível de ruído e as características do dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="ba330-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="ba330-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="ba330-572">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-573">SendListenMOS mínima para a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="ba330-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="ba330-575">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-576">Média prevista banda larga ouvindo a Pontuação do MOS para áudio recebido da rede, incluindo o nível de fala, o nível de ruído, o codec, as condições da rede e as características do dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="ba330-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="ba330-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="ba330-578">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="ba330-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ba330-579">RecvListenMOS mínima para a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba330-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="ba330-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="ba330-581">bit</span><span class="sxs-lookup"><span data-stu-id="ba330-581">bit</span></span></p></td>
<td><p><span data-ttu-id="ba330-582">Indica se o FEC de áudio foi usado para a chamada.</span><span class="sxs-lookup"><span data-stu-id="ba330-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba330-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="ba330-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="ba330-584">bit</span><span class="sxs-lookup"><span data-stu-id="ba330-584">bit</span></span></p></td>
<td><p><span data-ttu-id="ba330-585">Indica a direção das informações de identificação p-declaradas; 1 significa que a direção do fluxo é do chamador para o receptor; 0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="ba330-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

