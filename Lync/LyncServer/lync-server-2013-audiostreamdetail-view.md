---
title: 'Lync Server 2013: modo de exibição AudioStreamDetail'
description: 'Lync Server 2013: modo de exibição AudioStreamDetail.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92c4c9bbb4f126e242e28d835222f6ba2af89d8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573043"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="aaed0-103">Exibição AudioStreamDetail no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aaed0-103">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aaed0-104">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="aaed0-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="aaed0-105">A exibição AudioStreamDetail armazena informações sobre cada fluxo de áudio no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aaed0-105">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="aaed0-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aaed0-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aaed0-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="aaed0-107">Column</span></span></th>
<th><span data-ttu-id="aaed0-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="aaed0-108">Data Type</span></span></th>
<th><span data-ttu-id="aaed0-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="aaed0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-110">Sessiontime</span><span class="sxs-lookup"><span data-stu-id="aaed0-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="aaed0-111">datetime</span><span class="sxs-lookup"><span data-stu-id="aaed0-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="aaed0-112">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="aaed0-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="aaed0-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="aaed0-114">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-114">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-115">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="aaed0-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-116">Streamid</span><span class="sxs-lookup"><span data-stu-id="aaed0-116">StreamId</span></span></p></td>
<td><p><span data-ttu-id="aaed0-117">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-117">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-118">Identificação exclusiva em uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="aaed0-118">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-119">StartTime</span><span class="sxs-lookup"><span data-stu-id="aaed0-119">StartTime</span></span></p></td>
<td><p><span data-ttu-id="aaed0-120">datetime</span><span class="sxs-lookup"><span data-stu-id="aaed0-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="aaed0-121">Hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="aaed0-121">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-122">EndTime</span><span class="sxs-lookup"><span data-stu-id="aaed0-122">EndTime</span></span></p></td>
<td><p><span data-ttu-id="aaed0-123">datetime</span><span class="sxs-lookup"><span data-stu-id="aaed0-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="aaed0-124">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="aaed0-124">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-125">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="aaed0-125">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="aaed0-126">bits</span><span class="sxs-lookup"><span data-stu-id="aaed0-126">bit</span></span></p></td>
<td><p><span data-ttu-id="aaed0-127">Categoria da caixa de diálogo: 0 é o servidor do Lync para o trecho do servidor de mediação; 1 é o servidor de mediação para o trecho do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="aaed0-127">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-128">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="aaed0-128">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="aaed0-129">bits</span><span class="sxs-lookup"><span data-stu-id="aaed0-129">bit</span></span></p></td>
<td><p><span data-ttu-id="aaed0-130">Sinalizador que indica se a chamada foi ignorada ou não.</span><span class="sxs-lookup"><span data-stu-id="aaed0-130">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-131">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="aaed0-131">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="aaed0-132">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-132">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p102">Se presente, indica porque uma chamada não foi ignorada, mesmo se as IDs de desvio correspondem. Apenas um valor é definido:</span><span class="sxs-lookup"><span data-stu-id="aaed0-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="aaed0-135">0x0001 - ID de desvio desconhecida ao adaptador de rede padrão.</span><span class="sxs-lookup"><span data-stu-id="aaed0-135">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-136">CallPriority</span><span class="sxs-lookup"><span data-stu-id="aaed0-136">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="aaed0-137">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-137">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-138">Prioridade da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-138">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-139">CallerPool</span><span class="sxs-lookup"><span data-stu-id="aaed0-139">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="aaed0-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aaed0-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-141">Pool FQDN do chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-141">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-142">CalleePool</span><span class="sxs-lookup"><span data-stu-id="aaed0-142">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="aaed0-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aaed0-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-144">FQDN do pool do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-144">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-145">Chamador</span><span class="sxs-lookup"><span data-stu-id="aaed0-145">Caller</span></span></p></td>
<td><p><span data-ttu-id="aaed0-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="aaed0-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-147">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-147">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-148">Receptor</span><span class="sxs-lookup"><span data-stu-id="aaed0-148">Callee</span></span></p></td>
<td><p><span data-ttu-id="aaed0-149">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="aaed0-149">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-150">URI do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-150">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-151">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="aaed0-151">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="aaed0-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aaed0-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-153">String do agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-153">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-154">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="aaed0-154">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="aaed0-155">smallint</span><span class="sxs-lookup"><span data-stu-id="aaed0-155">smallint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-156">Tipo de agente do usuário do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-156">Type of the caller’s user agent.</span></span> <span data-ttu-id="aaed0-157">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="aaed0-157">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-158">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="aaed0-158">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="aaed0-159">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="aaed0-159">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-160">Categoria o agente do usuário do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-160">Category of the caller’s user agent.</span></span> <span data-ttu-id="aaed0-161">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="aaed0-161">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-162">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="aaed0-162">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="aaed0-163">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aaed0-163">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-164">String de agente de usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-164">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-165">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="aaed0-165">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="aaed0-166">smallint</span><span class="sxs-lookup"><span data-stu-id="aaed0-166">smallint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-167">Tipo de agente do usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-167">Type of callee’s user agent.</span></span> <span data-ttu-id="aaed0-168">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="aaed0-168">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-169">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="aaed0-169">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="aaed0-170">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="aaed0-170">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-171">Categoria do agente do usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-171">Category of callee’s user agent.</span></span> <span data-ttu-id="aaed0-172">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="aaed0-172">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-173">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="aaed0-173">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aaed0-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-175">Nome de ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-175">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-176">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="aaed0-176">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="aaed0-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-178">Nome do ponto de extremidade do receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-178">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-179">CallerOS</span><span class="sxs-lookup"><span data-stu-id="aaed0-179">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="aaed0-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="aaed0-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-181">Sistema operacional (OS) do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-181">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-182">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="aaed0-182">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="aaed0-183">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="aaed0-183">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-184">Sistema operacional (OS) do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-184">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-185">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="aaed0-185">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="aaed0-186">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="aaed0-186">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-187">Nome da CPU do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-187">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-188">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="aaed0-188">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="aaed0-189">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="aaed0-189">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-190">Nome da CPU do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-190">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-191">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="aaed0-191">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="aaed0-192">smallint</span><span class="sxs-lookup"><span data-stu-id="aaed0-192">smallint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-193">Número de núcleos da CPU no ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-193">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-194">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="aaed0-194">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="aaed0-195">smallint</span><span class="sxs-lookup"><span data-stu-id="aaed0-195">smallint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-196">Número de núcleos da CPU no ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-196">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-197">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="aaed0-197">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="aaed0-198">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-198">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-199">Velocidade do processador da CPU do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-199">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-200">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="aaed0-200">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="aaed0-201">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-201">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-202">Velocidade do processador da CPU do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-202">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-203">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="aaed0-203">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="aaed0-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="aaed0-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-205">Indica se o sistema do autor da chamada está funcionando em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="aaed0-205">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="aaed0-206">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aaed0-206">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-207">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="aaed0-207">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="aaed0-208">tinyint</span><span class="sxs-lookup"><span data-stu-id="aaed0-208">tinyint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-209">Indica que o sistema do receptor da chamada está funcionando em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="aaed0-209">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="aaed0-210">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aaed0-210">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-211">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="aaed0-211">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aaed0-212">Chave de correlação.</span><span class="sxs-lookup"><span data-stu-id="aaed0-212">Correlation key.</span></span> <span data-ttu-id="aaed0-213">Referenciado da <a href="lync-server-2013-sessioncorrelation-table.md">tabela SessionCorrelation no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="aaed0-213">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-214">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="aaed0-214">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="aaed0-215">tinyint</span><span class="sxs-lookup"><span data-stu-id="aaed0-215">tinyint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-216">Informações sobre o caminho de mídia, como direto ou retransmitido.</span><span class="sxs-lookup"><span data-stu-id="aaed0-216">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="aaed0-217">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aaed0-217">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-218">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="aaed0-218">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="aaed0-219">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-219">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p111">Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do autor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-222">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="aaed0-222">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="aaed0-223">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-223">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p112">Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do receptor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-226">Transport</span><span class="sxs-lookup"><span data-stu-id="aaed0-226">Transport</span></span></p></td>
<td><p><span data-ttu-id="aaed0-227">tinyint</span><span class="sxs-lookup"><span data-stu-id="aaed0-227">tinyint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-228">Tipo de transporte: 0 é UDP, 1 é TCP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-228">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-229">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="aaed0-229">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="aaed0-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="aaed0-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-231">Endereço IP do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-231">IP address of the caller.</span></span> <span data-ttu-id="aaed0-232">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="aaed0-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-233">CallerPort</span><span class="sxs-lookup"><span data-stu-id="aaed0-233">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="aaed0-234">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-234">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-235">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-235">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-236">CallerInside</span><span class="sxs-lookup"><span data-stu-id="aaed0-236">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="aaed0-237">bits</span><span class="sxs-lookup"><span data-stu-id="aaed0-237">bit</span></span></p></td>
<td><p><span data-ttu-id="aaed0-238">Indica se o chamador está na rede de intervalo: 1 significa que o chamador está na rede empresarial, 0 significa que está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="aaed0-238">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-239">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="aaed0-239">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="aaed0-240">var (50)</span><span class="sxs-lookup"><span data-stu-id="aaed0-240">var(50)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-241">Endereço IP do receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-241">IP address of the callee.</span></span> <span data-ttu-id="aaed0-242">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="aaed0-242">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-243">CalleePort</span><span class="sxs-lookup"><span data-stu-id="aaed0-243">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="aaed0-244">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-244">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-245">Porta usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-245">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-246">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="aaed0-246">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="aaed0-247">bits</span><span class="sxs-lookup"><span data-stu-id="aaed0-247">bit</span></span></p></td>
<td><p><span data-ttu-id="aaed0-248">Indica se o receptor está na rede de intervalo: 1 significa que o receptor está na rede empresarial, 0 significa que está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="aaed0-248">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-249">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="aaed0-249">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="aaed0-250">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="aaed0-250">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-251">Nome do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-251">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-252">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="aaed0-252">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="aaed0-253">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="aaed0-253">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-254">Nome do país/região do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-254">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-255">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="aaed0-255">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="aaed0-256">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="aaed0-256">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-257">Nome do site do receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-257">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-258">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="aaed0-258">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="aaed0-259">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="aaed0-259">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-260">Nome o país/região do site do receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-260">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-261">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="aaed0-261">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="aaed0-262">var (50)</span><span class="sxs-lookup"><span data-stu-id="aaed0-262">var(50)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-263">Endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-263">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="aaed0-264">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aaed0-264">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-265">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="aaed0-265">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="aaed0-266">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-266">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-267">Port used on the A/V Edge service used by the caller.</span><span class="sxs-lookup"><span data-stu-id="aaed0-267">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-268">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="aaed0-268">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="aaed0-269">var (50)</span><span class="sxs-lookup"><span data-stu-id="aaed0-269">var(50)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-270">Chave de endereço IP do serviço de borda A/V usado pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-270">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="aaed0-271">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aaed0-271">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-272">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="aaed0-272">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="aaed0-273">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-273">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-274">Porta usada no serviço de borda A/V usado pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-274">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-275">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="aaed0-275">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="aaed0-276">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="aaed0-276">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-277">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-277">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-278">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="aaed0-278">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="aaed0-279">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="aaed0-279">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-280">Nome do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-280">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-281">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="aaed0-281">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="aaed0-282">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="aaed0-282">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-283">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-283">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-284">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="aaed0-284">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="aaed0-285">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="aaed0-285">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-286">Nome do driver do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-286">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-287">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="aaed0-287">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="aaed0-288">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="aaed0-288">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-289">Nome do dispositivo de captura do receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-289">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-290">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="aaed0-290">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="aaed0-291">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="aaed0-291">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-292">Nome do dispositivo de renderização do receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-292">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-293">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="aaed0-293">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="aaed0-294">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="aaed0-294">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-295">Nome do driver do dispositivo de captura do receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-295">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-296">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="aaed0-296">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="aaed0-297">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="aaed0-297">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-298">Nome do driver do dispositivo de renderização do receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-298">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-299">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="aaed0-299">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="aaed0-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="aaed0-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-301">Tipo de conexão de rede do chamador: 0 é por fio, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="aaed0-301">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-302">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="aaed0-302">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="aaed0-303">bits</span><span class="sxs-lookup"><span data-stu-id="aaed0-303">bit</span></span></p></td>
<td><p><span data-ttu-id="aaed0-304">Indica se o autor da chamada se conectou por uma rede privada virtual: 1 é a rede privada virtual (VPN), 0 é não VPN.</span><span class="sxs-lookup"><span data-stu-id="aaed0-304">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-305">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="aaed0-305">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="aaed0-306">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="aaed0-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-307">Velocidade da rede dos pontos de extremidade do chamador em bps.</span><span class="sxs-lookup"><span data-stu-id="aaed0-307">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-308">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="aaed0-308">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="aaed0-309">tinyint</span><span class="sxs-lookup"><span data-stu-id="aaed0-309">tinyint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-310">Tipo de conexão de rede do receptor: 0 é por fio, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="aaed0-310">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-311">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="aaed0-311">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="aaed0-312">bits</span><span class="sxs-lookup"><span data-stu-id="aaed0-312">bit</span></span></p></td>
<td><p><span data-ttu-id="aaed0-313">Indica se o autor da chamada se conectou por uma rede privada virtual: 1 é a rede privada virtual (VPN), 0 é não VPN.</span><span class="sxs-lookup"><span data-stu-id="aaed0-313">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-314">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="aaed0-314">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="aaed0-315">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="aaed0-315">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-316">Velocidade de rede do ponto de extremidade do receptor em bps.</span><span class="sxs-lookup"><span data-stu-id="aaed0-316">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-317">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="aaed0-317">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="aaed0-318">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-318">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-319">MOS da Conversa de Banda Estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="aaed0-319">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-320">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="aaed0-320">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="aaed0-321">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-321">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p117">Largura de banda aplicada a determinado fluxo de envio considerando várias configurações de política (TURN, API, SDP, Servidor de política etc.). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma menor largura de banda efetiva com base na estimativa de largura de banda. Isso é basicamente a largura de banda máxima a qual o fluxo de envio pode aceitar limites de bloqueio impostos pela estimativa de largura de banda</span><span class="sxs-lookup"><span data-stu-id="aaed0-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-325">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="aaed0-325">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="aaed0-326">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-326">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-327">Média de tremulação de rede a partir da estatística do protocolo RTCP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-327">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-328">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="aaed0-328">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="aaed0-329">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-329">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-330">Tremulação máxima da rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-330">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-331">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="aaed0-331">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="aaed0-332">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="aaed0-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-333">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-333">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-334">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="aaed0-334">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="aaed0-335">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="aaed0-335">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-336">Perda máxima de pacotes observada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-336">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-337">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="aaed0-337">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="aaed0-338">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="aaed0-338">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-339">Densidade média de perda de pacote durante picos de perdas em uma chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-339">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-340">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="aaed0-340">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="aaed0-341">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-341">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-342">Duração média de perda de pacote durante picos de perdas durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-342">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-343">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="aaed0-343">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="aaed0-344">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="aaed0-344">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-345">Densidade média de perda de pacote durante intervalos entre picos de perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="aaed0-345">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-346">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="aaed0-346">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="aaed0-347">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-347">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-348">Duração média de intervalos entre picos de perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="aaed0-348">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-349">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="aaed0-349">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="aaed0-350">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-350">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-351">Contagem de pacotes para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="aaed0-351">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-352">Mais largura de banda</span><span class="sxs-lookup"><span data-stu-id="aaed0-352">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="aaed0-353">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-353">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-354">Estimativas de largura de banda para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="aaed0-354">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-355">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="aaed0-355">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="aaed0-356">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-356">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p118">Degradação de MOS de rede para a chamada completa. O intervalo vai de 0,0 a 5,0. Essa métrica mostra o quanto o MOS de rede foi reduzido por causa de tremulação e perda de pacote. Para obter a qualidade aceitável, o MOS da rede deve ser menor que 0,5.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-361">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="aaed0-361">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="aaed0-362">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-362">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-363">Degradação máxima de MOS de rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-363">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-364">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="aaed0-364">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="aaed0-365">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-365">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-366">Degradação de MOS de rede causada por tremulação.</span><span class="sxs-lookup"><span data-stu-id="aaed0-366">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-367">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="aaed0-367">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="aaed0-368">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-368">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-369">Degradação de MOS de rede causada por perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="aaed0-369">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-370">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="aaed0-370">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="aaed0-371">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-371">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-372">O codec de áudio usado para a chamada, referenciado pela <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="aaed0-372">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-373">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="aaed0-373">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="aaed0-374">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-374">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-375">Taxa de amostragem para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="aaed0-375">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-376">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="aaed0-376">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="aaed0-377">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-377">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p119">Nível do sinal de áudio de controle de ganho pós-analógico do áudio enviado pelo chamador. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-382">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="aaed0-382">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="aaed0-383">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-383">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p120">Nível do sinal de áudio do áudio recebido pelo chamador. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-388">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="aaed0-388">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="aaed0-389">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-389">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p121">Nível de ruído de áudio de controle de ganho pós-analógico do áudio enviado pelo chamador. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-394">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="aaed0-394">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="aaed0-395">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-395">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p122">Nível de ruído de áudio de controle de ganho pós-analógico do áudio recebido pelo chamado. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-400">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="aaed0-400">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="aaed0-401">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-401">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p123">Aprimoramento de perda e retorno de eco do chamador. A unidade desta medida é o dB. Valores mais baixos representam menos eco. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-406">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="aaed0-406">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="aaed0-407">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-407">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p124">Média de falhar por cinco minutos da renderização de alto-falante do chamador. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-411">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="aaed0-411">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="aaed0-412">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-412">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p125">Média de falhas por cinco minutos da captura de microfone do chamador. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-416">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="aaed0-416">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="aaed0-417">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-417">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-418">Taxa de descompasso de relógio do dispositivo de microfone do chamador, relativo ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="aaed0-418">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-419">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="aaed0-419">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="aaed0-420">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-420">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-421">Taxa de descompasso de relógio de dispositivo do de alto-falante do chamador, relativo ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="aaed0-421">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-422">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="aaed0-422">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="aaed0-423">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-423">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-424">Média de erro de registro de hora de fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-424">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-425">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="aaed0-425">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="aaed0-426">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-426">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-427">Média de erros de carimbo de data/hora do fluxo de renderização de alto-falante do chamador, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-427">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-428">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="aaed0-428">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="aaed0-429">smallint</span><span class="sxs-lookup"><span data-stu-id="aaed0-429">smallint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-430">Opção de voz é um modo meio-duplex com capacidade de interrupção reduzida.</span><span class="sxs-lookup"><span data-stu-id="aaed0-430">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="aaed0-431">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aaed0-431">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-432">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="aaed0-432">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="aaed0-433">tinyint</span><span class="sxs-lookup"><span data-stu-id="aaed0-433">tinyint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-434">Causas de um evento de eco para o chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-434">Causes of an echo event for the caller.</span></span> <span data-ttu-id="aaed0-435">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aaed0-435">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-436">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="aaed0-436">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="aaed0-437">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-437">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p128">Porcentagem de tempo quando ecos são detectados no fluxo de captura do microfone do chamador. Caso seja utilizado headset, o valor deve ser baixo.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-440">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="aaed0-440">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="aaed0-441">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-441">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p129">Porcentagem de tempo quando ecos são detectados no fluxo enviado pelo chamador. Uma alta porcentagem de eco em fluxos enviados indica um vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-444">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="aaed0-444">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="aaed0-445">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-445">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p130">Nível de sinal recebido no Servidor de mediação do Gateway para o áudio do chamador; isso se aplica apenas ao Servidor de mediação. A unidade desta medida é o dBoV. Para obter uma boa qualidade, o intervalo aceitável deve ser entre -30 a -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-449">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="aaed0-449">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="aaed0-450">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-450">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p131">Nível de sinal recebido na Servidor de mediação do Gateway para o áudio do chamador. Se aplica apenas ao Servidor de Mediação. A unidade desta medida é o dBoV. Para uma boa qualidade, a faixa aceitável deve ser menor do que -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-455">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="aaed0-455">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="aaed0-456">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-456">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-457">Controle de ganho automático (AGC) no Servidor de mediação aplicado ao áudio do chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-457">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-458">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="aaed0-458">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="aaed0-459">flutuação</span><span class="sxs-lookup"><span data-stu-id="aaed0-459">float</span></span></p></td>
<td><p><span data-ttu-id="aaed0-460">Raiz quadrada média (RMS) o sinal de entrada para o chamador pelos 30 primeiros segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-460">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-461">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="aaed0-461">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="aaed0-462">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-462">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p132">Representa o nível de sinal de áudio de controle de ganho pós-analógico do áudio enviado pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-467">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="aaed0-467">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="aaed0-468">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-468">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p133">Nível do sinal de áudio do áudio recebido pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-473">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="aaed0-473">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="aaed0-474">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-474">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p134">Nível de ruído de áudio de controle de ganho pós-analógico do áudio enviado pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-479">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="aaed0-479">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="aaed0-480">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-480">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p135">Nível de ruído de áudio de controle de ganho pós-analógico do áudio recebido pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-485">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="aaed0-485">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="aaed0-486">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-486">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p136">Aprimoramento de perda e retorno de eco do receptor. A unidade desta medida é o dB. Valores mais baixos representam menos eco. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-491">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="aaed0-491">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="aaed0-492">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-492">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p137">Média de falhas por cinco minutos da renderização de alto-falante do receptor. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-496">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="aaed0-496">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="aaed0-497">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-497">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p138">Média de falhas por cinco minutos da captura de microfone do receptor. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-501">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="aaed0-501">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="aaed0-502">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-502">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-503">Taxa de descompasso do relógio do dispositivo de microfone do receptor, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="aaed0-503">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-504">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="aaed0-504">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="aaed0-505">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-505">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-506">Taxa de descompasso do relógio do dispositivo de alto-falante do receptor, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="aaed0-506">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-507">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="aaed0-507">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="aaed0-508">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-508">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-509">Média de erro de registro de hora de fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-509">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-510">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="aaed0-510">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="aaed0-511">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-511">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-512">Médio de erro de carimbo de data/hora do fluxo de renderização de alto-falante do receptor, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-512">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-513">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="aaed0-513">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="aaed0-514">smallint</span><span class="sxs-lookup"><span data-stu-id="aaed0-514">smallint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-515">Opção de voz é um modo meio-duplex com capacidade de interrupção reduzida.</span><span class="sxs-lookup"><span data-stu-id="aaed0-515">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="aaed0-516">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aaed0-516">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-517">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="aaed0-517">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="aaed0-518">tinyint</span><span class="sxs-lookup"><span data-stu-id="aaed0-518">tinyint</span></span></p></td>
<td><p><span data-ttu-id="aaed0-519">Causa um evento de eco para o receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-519">Causes of an echo event for the callee.</span></span> <span data-ttu-id="aaed0-520">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aaed0-520">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-521">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="aaed0-521">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="aaed0-522">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-522">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p141">Porcentagem de tempo quando ecos são detectados no fluxo de captura do microfone do receptor. Caso seja utilizado headset, o valor deve ser baixo.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-525">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="aaed0-525">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="aaed0-526">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-526">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p142">Porcentagem de tempo quando ecos são detectados no fluxo de envio do receptor. Uma alta porcentagem de eco em fluxos enviados indica um vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-529">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="aaed0-529">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="aaed0-530">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-530">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p143">Nível de sinal recebido no Servidor de mediação do Gateway para o áudio do receptor; isso se aplica apenas ao Servidor de mediação. A unidade desta medida é o dBoV. Para uma boa qualidade, a faixa aceitável deve ser de [-30 a -18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-534">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="aaed0-534">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="aaed0-535">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-535">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p144">Nível de sinal recebido no Servidor de mediação do Gateway para o áudio do receptor. Se aplica apenas ao Servidor de Mediação. A unidade desta medida é o dBoV. Para uma boa qualidade, a faixa aceitável deve ser menor do que -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-540">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="aaed0-540">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="aaed0-541">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-541">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-542">Controle de ganho automático (AGC) no Servidor de mediação aplicado ao áudio do receptor.</span><span class="sxs-lookup"><span data-stu-id="aaed0-542">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-543">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="aaed0-543">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="aaed0-544">flutuação</span><span class="sxs-lookup"><span data-stu-id="aaed0-544">float</span></span></p></td>
<td><p><span data-ttu-id="aaed0-545">Raiz quadrada média (RMS) do sinal de entrada para o receptor durante os 30 primeiros segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-545">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-546">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="aaed0-546">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="aaed0-547">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-547">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-548">Taxa média de amostras escondidas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="aaed0-548">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-549">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="aaed0-549">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="aaed0-550">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-550">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-551">Taxa média de amostras corrigidas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="aaed0-551">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-552">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="aaed0-552">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="aaed0-553">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-553">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-554">Taxa média de amostras compactadas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="aaed0-554">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-555">Aproxima</span><span class="sxs-lookup"><span data-stu-id="aaed0-555">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="aaed0-556">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-556">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-557">Tempo de ida e volta de estatísticas RTCP.</span><span class="sxs-lookup"><span data-stu-id="aaed0-557">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-558">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="aaed0-558">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="aaed0-559">int</span><span class="sxs-lookup"><span data-stu-id="aaed0-559">int</span></span></p></td>
<td><p><span data-ttu-id="aaed0-560">Tempo máximo de ida e volta para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="aaed0-560">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-561">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="aaed0-561">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="aaed0-562">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-562">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-p145">Média de MOS de rede de banda ampla para a chamada. Essa métrica depende da perda de pacote, da tremulação e do codec usado. O intervalo é de 1.0 a 5.0.</span><span class="sxs-lookup"><span data-stu-id="aaed0-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-566">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="aaed0-566">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="aaed0-567">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-567">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-568">Mínimo de MOS de rede de banda ampla para a chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-568">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-569">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="aaed0-569">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="aaed0-570">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-570">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-571">Pontuação média prevista de MOS de escuta de banda larga do áudio enviado, incluindo nível de fala, nível de ruído e características de dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="aaed0-571">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-572">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="aaed0-572">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="aaed0-573">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-573">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-574">SendListenMOS mínimo da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-574">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-575">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="aaed0-575">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="aaed0-576">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-576">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-577">Pontuação média prevista de MOS de escuta de banda larga do áudio recebido da rede, incluindo nível de fala, nível de ruído, codec, condições da rede e características do dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="aaed0-577">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-578">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="aaed0-578">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="aaed0-579">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="aaed0-579">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="aaed0-580">RecvListenMOS mínimo da chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-580">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aaed0-581">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="aaed0-581">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="aaed0-582">bits</span><span class="sxs-lookup"><span data-stu-id="aaed0-582">bit</span></span></p></td>
<td><p><span data-ttu-id="aaed0-583">Indica se o FEC de áudio foi usado para a chamada.</span><span class="sxs-lookup"><span data-stu-id="aaed0-583">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aaed0-584">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="aaed0-584">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="aaed0-585">bits</span><span class="sxs-lookup"><span data-stu-id="aaed0-585">bit</span></span></p></td>
<td><p><span data-ttu-id="aaed0-586">Indica a direção das informações de identidade declarada; 1 significa que a direção do fluxo é do chamador para o receptor; 0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="aaed0-586">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

