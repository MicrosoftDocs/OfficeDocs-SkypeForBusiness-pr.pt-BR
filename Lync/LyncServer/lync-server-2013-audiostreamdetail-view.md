---
title: 'Lync Server 2013: modo de exibição AudioStreamDetail'
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
ms.openlocfilehash: fe995d08bf334308603512b4812b02c672d400f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="95562-102">Exibição AudioStreamDetail no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95562-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95562-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="95562-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="95562-104">A exibição AudioStreamDetail armazena informações sobre cada fluxo de áudio no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="95562-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="95562-105">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="95562-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95562-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="95562-106">Column</span></span></th>
<th><span data-ttu-id="95562-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="95562-107">Data Type</span></span></th>
<th><span data-ttu-id="95562-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="95562-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95562-109">Sessiontime</span><span class="sxs-lookup"><span data-stu-id="95562-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="95562-110">datetime</span><span class="sxs-lookup"><span data-stu-id="95562-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="95562-111">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="95562-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="95562-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="95562-113">int</span><span class="sxs-lookup"><span data-stu-id="95562-113">int</span></span></p></td>
<td><p><span data-ttu-id="95562-114">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="95562-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-115">Streamid</span><span class="sxs-lookup"><span data-stu-id="95562-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="95562-116">int</span><span class="sxs-lookup"><span data-stu-id="95562-116">int</span></span></p></td>
<td><p><span data-ttu-id="95562-117">Identificação exclusiva em uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="95562-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="95562-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="95562-119">datetime</span><span class="sxs-lookup"><span data-stu-id="95562-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="95562-120">Hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="95562-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="95562-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="95562-122">datetime</span><span class="sxs-lookup"><span data-stu-id="95562-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="95562-123">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="95562-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="95562-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="95562-125">bits</span><span class="sxs-lookup"><span data-stu-id="95562-125">bit</span></span></p></td>
<td><p><span data-ttu-id="95562-126">Categoria da caixa de diálogo: 0 é o servidor do Lync para o trecho do servidor de mediação; 1 é o servidor de mediação para o trecho do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="95562-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="95562-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="95562-128">bits</span><span class="sxs-lookup"><span data-stu-id="95562-128">bit</span></span></p></td>
<td><p><span data-ttu-id="95562-129">Sinalizador que indica se a chamada foi ignorada ou não.</span><span class="sxs-lookup"><span data-stu-id="95562-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="95562-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="95562-131">int</span><span class="sxs-lookup"><span data-stu-id="95562-131">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p102">Se presente, indica porque uma chamada não foi ignorada, mesmo se as IDs de desvio correspondem. Apenas um valor é definido:</span><span class="sxs-lookup"><span data-stu-id="95562-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="95562-134">0x0001 - ID de desvio desconhecida ao adaptador de rede padrão.</span><span class="sxs-lookup"><span data-stu-id="95562-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="95562-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="95562-136">int</span><span class="sxs-lookup"><span data-stu-id="95562-136">int</span></span></p></td>
<td><p><span data-ttu-id="95562-137">Prioridade da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="95562-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="95562-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95562-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95562-140">Pool FQDN do chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="95562-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="95562-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95562-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95562-143">FQDN do pool do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-144">Chamador</span><span class="sxs-lookup"><span data-stu-id="95562-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="95562-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="95562-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="95562-146">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-147">Receptor</span><span class="sxs-lookup"><span data-stu-id="95562-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="95562-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="95562-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="95562-149">URI do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="95562-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="95562-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95562-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95562-152">String do agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="95562-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="95562-154">smallint</span><span class="sxs-lookup"><span data-stu-id="95562-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="95562-155">Tipo de agente do usuário do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="95562-156">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="95562-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="95562-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="95562-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="95562-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="95562-159">Categoria o agente do usuário do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="95562-160">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="95562-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="95562-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="95562-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95562-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95562-163">String de agente de usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="95562-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="95562-165">smallint</span><span class="sxs-lookup"><span data-stu-id="95562-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="95562-166">Tipo de agente do usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-166">Type of callee’s user agent.</span></span> <span data-ttu-id="95562-167">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="95562-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="95562-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="95562-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="95562-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="95562-170">Categoria do agente do usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-170">Category of callee’s user agent.</span></span> <span data-ttu-id="95562-171">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="95562-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="95562-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="95562-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95562-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95562-174">Nome de ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="95562-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="95562-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="95562-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95562-177">Nome do ponto de extremidade do receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="95562-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="95562-179">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="95562-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="95562-180">Sistema operacional (OS) do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="95562-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="95562-182">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="95562-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="95562-183">Sistema operacional (OS) do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="95562-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="95562-185">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="95562-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="95562-186">Nome da CPU do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="95562-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="95562-188">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="95562-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="95562-189">Nome da CPU do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="95562-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="95562-191">smallint</span><span class="sxs-lookup"><span data-stu-id="95562-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="95562-192">Número de núcleos da CPU no ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="95562-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="95562-194">smallint</span><span class="sxs-lookup"><span data-stu-id="95562-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="95562-195">Número de núcleos da CPU no ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="95562-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="95562-197">int</span><span class="sxs-lookup"><span data-stu-id="95562-197">int</span></span></p></td>
<td><p><span data-ttu-id="95562-198">Velocidade do processador da CPU do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="95562-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="95562-200">int</span><span class="sxs-lookup"><span data-stu-id="95562-200">int</span></span></p></td>
<td><p><span data-ttu-id="95562-201">Velocidade do processador da CPU do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="95562-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="95562-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="95562-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="95562-204">Indica se o sistema do autor da chamada está funcionando em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="95562-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="95562-205">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="95562-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="95562-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="95562-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="95562-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="95562-208">Indica que o sistema do receptor da chamada está funcionando em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="95562-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="95562-209">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="95562-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="95562-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="95562-211">Chave de correlação.</span><span class="sxs-lookup"><span data-stu-id="95562-211">Correlation key.</span></span> <span data-ttu-id="95562-212">Referenciado da <a href="lync-server-2013-sessioncorrelation-table.md">tabela SessionCorrelation no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="95562-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="95562-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="95562-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="95562-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="95562-215">Informações sobre o caminho de mídia, como direto ou retransmitido.</span><span class="sxs-lookup"><span data-stu-id="95562-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="95562-216">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="95562-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="95562-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="95562-218">int</span><span class="sxs-lookup"><span data-stu-id="95562-218">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p111">Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do autor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="95562-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="95562-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="95562-222">int</span><span class="sxs-lookup"><span data-stu-id="95562-222">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p112">Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do receptor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="95562-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-225">Transport</span><span class="sxs-lookup"><span data-stu-id="95562-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="95562-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="95562-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="95562-227">Tipo de transporte: 0 é UDP, 1 é TCP.</span><span class="sxs-lookup"><span data-stu-id="95562-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="95562-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="95562-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="95562-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="95562-230">Endereço IP do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-230">IP address of the caller.</span></span> <span data-ttu-id="95562-231">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="95562-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="95562-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="95562-233">int</span><span class="sxs-lookup"><span data-stu-id="95562-233">int</span></span></p></td>
<td><p><span data-ttu-id="95562-234">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="95562-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="95562-236">bits</span><span class="sxs-lookup"><span data-stu-id="95562-236">bit</span></span></p></td>
<td><p><span data-ttu-id="95562-237">Indica se o chamador está na rede de intervalo: 1 significa que o chamador está na rede empresarial, 0 significa que está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="95562-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="95562-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="95562-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="95562-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="95562-240">Endereço IP do receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-240">IP address of the callee.</span></span> <span data-ttu-id="95562-241">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="95562-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="95562-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="95562-243">int</span><span class="sxs-lookup"><span data-stu-id="95562-243">int</span></span></p></td>
<td><p><span data-ttu-id="95562-244">Porta usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="95562-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="95562-246">bits</span><span class="sxs-lookup"><span data-stu-id="95562-246">bit</span></span></p></td>
<td><p><span data-ttu-id="95562-247">Indica se o receptor está na rede de intervalo: 1 significa que o receptor está na rede empresarial, 0 significa que está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="95562-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="95562-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="95562-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="95562-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="95562-250">Nome do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="95562-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="95562-252">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="95562-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="95562-253">Nome do país/região do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="95562-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="95562-255">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="95562-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="95562-256">Nome do site do receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="95562-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="95562-258">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="95562-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="95562-259">Nome o país/região do site do receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="95562-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="95562-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="95562-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="95562-262">Endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="95562-263">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="95562-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="95562-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="95562-265">int</span><span class="sxs-lookup"><span data-stu-id="95562-265">int</span></span></p></td>
<td><p><span data-ttu-id="95562-266">Port used on the A/V Edge service used by the caller.</span><span class="sxs-lookup"><span data-stu-id="95562-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="95562-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="95562-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="95562-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="95562-269">Chave de endereço IP do serviço de borda A/V usado pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="95562-270">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="95562-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="95562-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="95562-272">int</span><span class="sxs-lookup"><span data-stu-id="95562-272">int</span></span></p></td>
<td><p><span data-ttu-id="95562-273">Porta usada no serviço de borda A/V usado pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="95562-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="95562-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="95562-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95562-276">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="95562-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="95562-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="95562-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95562-279">Nome do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="95562-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="95562-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="95562-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95562-282">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="95562-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="95562-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="95562-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95562-285">Nome do driver do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="95562-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="95562-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="95562-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95562-288">Nome do dispositivo de captura do receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="95562-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="95562-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="95562-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95562-291">Nome do dispositivo de renderização do receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="95562-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="95562-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="95562-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95562-294">Nome do driver do dispositivo de captura do receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="95562-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="95562-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="95562-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="95562-297">Nome do driver do dispositivo de renderização do receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="95562-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="95562-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="95562-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="95562-300">Tipo de conexão de rede do chamador: 0 é por fio, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="95562-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="95562-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="95562-302">bits</span><span class="sxs-lookup"><span data-stu-id="95562-302">bit</span></span></p></td>
<td><p><span data-ttu-id="95562-303">Indica se o autor da chamada se conectou por uma rede privada virtual: 1 é a rede privada virtual (VPN), 0 é não VPN.</span><span class="sxs-lookup"><span data-stu-id="95562-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="95562-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="95562-305">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="95562-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="95562-306">Velocidade da rede dos pontos de extremidade do chamador em bps.</span><span class="sxs-lookup"><span data-stu-id="95562-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="95562-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="95562-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="95562-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="95562-309">Tipo de conexão de rede do receptor: 0 é por fio, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="95562-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="95562-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="95562-311">bits</span><span class="sxs-lookup"><span data-stu-id="95562-311">bit</span></span></p></td>
<td><p><span data-ttu-id="95562-312">Indica se o autor da chamada se conectou por uma rede privada virtual: 1 é a rede privada virtual (VPN), 0 é não VPN.</span><span class="sxs-lookup"><span data-stu-id="95562-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="95562-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="95562-314">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="95562-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="95562-315">Velocidade de rede do ponto de extremidade do receptor em bps.</span><span class="sxs-lookup"><span data-stu-id="95562-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="95562-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="95562-317">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-318">MOS da Conversa de Banda Estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="95562-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="95562-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="95562-320">int</span><span class="sxs-lookup"><span data-stu-id="95562-320">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p117">Largura de banda aplicada a determinado fluxo de envio considerando várias configurações de política (TURN, API, SDP, Servidor de política etc.). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma menor largura de banda efetiva com base na estimativa de largura de banda. Isso é basicamente a largura de banda máxima a qual o fluxo de envio pode aceitar limites de bloqueio impostos pela estimativa de largura de banda</span><span class="sxs-lookup"><span data-stu-id="95562-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="95562-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="95562-325">int</span><span class="sxs-lookup"><span data-stu-id="95562-325">int</span></span></p></td>
<td><p><span data-ttu-id="95562-326">Média de tremulação de rede a partir da estatística do protocolo RTCP.</span><span class="sxs-lookup"><span data-stu-id="95562-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="95562-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="95562-328">int</span><span class="sxs-lookup"><span data-stu-id="95562-328">int</span></span></p></td>
<td><p><span data-ttu-id="95562-329">Tremulação máxima da rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="95562-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="95562-331">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="95562-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="95562-332">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="95562-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="95562-334">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="95562-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="95562-335">Perda máxima de pacotes observada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="95562-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="95562-337">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="95562-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="95562-338">Densidade média de perda de pacote durante picos de perdas em uma chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="95562-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="95562-340">int</span><span class="sxs-lookup"><span data-stu-id="95562-340">int</span></span></p></td>
<td><p><span data-ttu-id="95562-341">Duração média de perda de pacote durante picos de perdas durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="95562-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="95562-343">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="95562-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="95562-344">Densidade média de perda de pacote durante intervalos entre picos de perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="95562-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="95562-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="95562-346">int</span><span class="sxs-lookup"><span data-stu-id="95562-346">int</span></span></p></td>
<td><p><span data-ttu-id="95562-347">Duração média de intervalos entre picos de perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="95562-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="95562-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="95562-349">int</span><span class="sxs-lookup"><span data-stu-id="95562-349">int</span></span></p></td>
<td><p><span data-ttu-id="95562-350">Contagem de pacotes para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="95562-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-351">Mais largura de banda</span><span class="sxs-lookup"><span data-stu-id="95562-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="95562-352">int</span><span class="sxs-lookup"><span data-stu-id="95562-352">int</span></span></p></td>
<td><p><span data-ttu-id="95562-353">Estimativas de largura de banda para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="95562-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="95562-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="95562-355">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-p118">Degradação de MOS de rede para a chamada completa. O intervalo vai de 0,0 a 5,0. Essa métrica mostra o quanto o MOS de rede foi reduzido por causa de tremulação e perda de pacote. Para obter a qualidade aceitável, o MOS da rede deve ser menor que 0,5.</span><span class="sxs-lookup"><span data-stu-id="95562-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="95562-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="95562-361">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-362">Degradação máxima de MOS de rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="95562-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="95562-364">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-365">Degradação de MOS de rede causada por tremulação.</span><span class="sxs-lookup"><span data-stu-id="95562-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="95562-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="95562-367">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-368">Degradação de MOS de rede causada por perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="95562-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="95562-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="95562-370">int</span><span class="sxs-lookup"><span data-stu-id="95562-370">int</span></span></p></td>
<td><p><span data-ttu-id="95562-371">O codec de áudio usado para a chamada, referenciado pela <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="95562-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="95562-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="95562-373">int</span><span class="sxs-lookup"><span data-stu-id="95562-373">int</span></span></p></td>
<td><p><span data-ttu-id="95562-374">Taxa de amostragem para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="95562-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="95562-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="95562-376">int</span><span class="sxs-lookup"><span data-stu-id="95562-376">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p119">Nível do sinal de áudio de controle de ganho pós-analógico do áudio enviado pelo chamador. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="95562-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="95562-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="95562-382">int</span><span class="sxs-lookup"><span data-stu-id="95562-382">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p120">Nível do sinal de áudio do áudio recebido pelo chamador. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="95562-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="95562-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="95562-388">int</span><span class="sxs-lookup"><span data-stu-id="95562-388">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p121">Nível de ruído de áudio de controle de ganho pós-analógico do áudio enviado pelo chamador. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="95562-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="95562-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="95562-394">int</span><span class="sxs-lookup"><span data-stu-id="95562-394">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p122">Nível de ruído de áudio de controle de ganho pós-analógico do áudio recebido pelo chamado. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="95562-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="95562-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="95562-400">int</span><span class="sxs-lookup"><span data-stu-id="95562-400">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p123">Aprimoramento de perda e retorno de eco do chamador. A unidade desta medida é o dB. Valores mais baixos representam menos eco. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="95562-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="95562-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="95562-406">int</span><span class="sxs-lookup"><span data-stu-id="95562-406">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p124">Média de falhar por cinco minutos da renderização de alto-falante do chamador. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="95562-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="95562-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="95562-411">int</span><span class="sxs-lookup"><span data-stu-id="95562-411">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p125">Média de falhas por cinco minutos da captura de microfone do chamador. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="95562-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="95562-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="95562-416">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-417">Taxa de descompasso de relógio do dispositivo de microfone do chamador, relativo ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="95562-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="95562-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="95562-419">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-420">Taxa de descompasso de relógio de dispositivo do de alto-falante do chamador, relativo ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="95562-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="95562-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="95562-422">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-423">Média de erro de registro de hora de fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="95562-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="95562-425">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-426">Média de erros de carimbo de data/hora do fluxo de renderização de alto-falante do chamador, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="95562-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="95562-428">smallint</span><span class="sxs-lookup"><span data-stu-id="95562-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="95562-429">Opção de voz é um modo meio-duplex com capacidade de interrupção reduzida.</span><span class="sxs-lookup"><span data-stu-id="95562-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="95562-430">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="95562-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="95562-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="95562-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="95562-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="95562-433">Causas de um evento de eco para o chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="95562-434">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="95562-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="95562-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="95562-436">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-p128">Porcentagem de tempo quando ecos são detectados no fluxo de captura do microfone do chamador. Caso seja utilizado headset, o valor deve ser baixo.</span><span class="sxs-lookup"><span data-stu-id="95562-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="95562-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="95562-440">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-p129">Porcentagem de tempo quando ecos são detectados no fluxo enviado pelo chamador. Uma alta porcentagem de eco em fluxos enviados indica um vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="95562-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="95562-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="95562-444">int</span><span class="sxs-lookup"><span data-stu-id="95562-444">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p130">Nível de sinal recebido no Servidor de mediação do Gateway para o áudio do chamador; isso se aplica apenas ao Servidor de mediação. A unidade desta medida é o dBoV. Para obter uma boa qualidade, o intervalo aceitável deve ser entre -30 a -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="95562-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="95562-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="95562-449">int</span><span class="sxs-lookup"><span data-stu-id="95562-449">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p131">Nível de sinal recebido na Servidor de mediação do Gateway para o áudio do chamador. Se aplica apenas ao Servidor de Mediação. A unidade desta medida é o dBoV. Para uma boa qualidade, a faixa aceitável deve ser menor do que -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="95562-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="95562-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="95562-455">int</span><span class="sxs-lookup"><span data-stu-id="95562-455">int</span></span></p></td>
<td><p><span data-ttu-id="95562-456">Controle de ganho automático (AGC) no Servidor de mediação aplicado ao áudio do chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="95562-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="95562-458">float</span><span class="sxs-lookup"><span data-stu-id="95562-458">float</span></span></p></td>
<td><p><span data-ttu-id="95562-459">Raiz quadrada média (RMS) o sinal de entrada para o chamador pelos 30 primeiros segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="95562-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="95562-461">int</span><span class="sxs-lookup"><span data-stu-id="95562-461">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p132">Representa o nível de sinal de áudio de controle de ganho pós-analógico do áudio enviado pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="95562-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="95562-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="95562-467">int</span><span class="sxs-lookup"><span data-stu-id="95562-467">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p133">Nível do sinal de áudio do áudio recebido pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="95562-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="95562-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="95562-473">int</span><span class="sxs-lookup"><span data-stu-id="95562-473">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p134">Nível de ruído de áudio de controle de ganho pós-analógico do áudio enviado pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="95562-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="95562-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="95562-479">int</span><span class="sxs-lookup"><span data-stu-id="95562-479">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p135">Nível de ruído de áudio de controle de ganho pós-analógico do áudio recebido pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="95562-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="95562-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="95562-485">int</span><span class="sxs-lookup"><span data-stu-id="95562-485">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p136">Aprimoramento de perda e retorno de eco do receptor. A unidade desta medida é o dB. Valores mais baixos representam menos eco. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="95562-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="95562-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="95562-491">int</span><span class="sxs-lookup"><span data-stu-id="95562-491">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p137">Média de falhas por cinco minutos da renderização de alto-falante do receptor. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="95562-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="95562-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="95562-496">int</span><span class="sxs-lookup"><span data-stu-id="95562-496">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p138">Média de falhas por cinco minutos da captura de microfone do receptor. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="95562-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="95562-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="95562-501">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-502">Taxa de descompasso do relógio do dispositivo de microfone do receptor, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="95562-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="95562-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="95562-504">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-505">Taxa de descompasso do relógio do dispositivo de alto-falante do receptor, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="95562-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="95562-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="95562-507">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-508">Média de erro de registro de hora de fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="95562-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="95562-510">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-511">Médio de erro de carimbo de data/hora do fluxo de renderização de alto-falante do receptor, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="95562-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="95562-513">smallint</span><span class="sxs-lookup"><span data-stu-id="95562-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="95562-514">Opção de voz é um modo meio-duplex com capacidade de interrupção reduzida.</span><span class="sxs-lookup"><span data-stu-id="95562-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="95562-515">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="95562-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="95562-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="95562-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="95562-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="95562-518">Causa um evento de eco para o receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="95562-519">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="95562-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="95562-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="95562-521">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-p141">Porcentagem de tempo quando ecos são detectados no fluxo de captura do microfone do receptor. Caso seja utilizado headset, o valor deve ser baixo.</span><span class="sxs-lookup"><span data-stu-id="95562-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="95562-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="95562-525">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-p142">Porcentagem de tempo quando ecos são detectados no fluxo de envio do receptor. Uma alta porcentagem de eco em fluxos enviados indica um vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="95562-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="95562-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="95562-529">int</span><span class="sxs-lookup"><span data-stu-id="95562-529">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p143">Nível de sinal recebido no Servidor de mediação do Gateway para o áudio do receptor; isso se aplica apenas ao Servidor de mediação. A unidade desta medida é o dBoV. Para uma boa qualidade, a faixa aceitável deve ser de [-30 a -18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="95562-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="95562-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="95562-534">int</span><span class="sxs-lookup"><span data-stu-id="95562-534">int</span></span></p></td>
<td><p><span data-ttu-id="95562-p144">Nível de sinal recebido no Servidor de mediação do Gateway para o áudio do receptor. Se aplica apenas ao Servidor de Mediação. A unidade desta medida é o dBoV. Para uma boa qualidade, a faixa aceitável deve ser menor do que -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="95562-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="95562-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="95562-540">int</span><span class="sxs-lookup"><span data-stu-id="95562-540">int</span></span></p></td>
<td><p><span data-ttu-id="95562-541">Controle de ganho automático (AGC) no Servidor de mediação aplicado ao áudio do receptor.</span><span class="sxs-lookup"><span data-stu-id="95562-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="95562-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="95562-543">float</span><span class="sxs-lookup"><span data-stu-id="95562-543">float</span></span></p></td>
<td><p><span data-ttu-id="95562-544">Raiz quadrada média (RMS) do sinal de entrada para o receptor durante os 30 primeiros segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="95562-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="95562-546">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-547">Taxa média de amostras escondidas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="95562-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="95562-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="95562-549">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-550">Taxa média de amostras corrigidas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="95562-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="95562-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="95562-552">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-553">Taxa média de amostras compactadas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="95562-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-554">Aproxima</span><span class="sxs-lookup"><span data-stu-id="95562-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="95562-555">int</span><span class="sxs-lookup"><span data-stu-id="95562-555">int</span></span></p></td>
<td><p><span data-ttu-id="95562-556">Tempo de ida e volta de estatísticas RTCP.</span><span class="sxs-lookup"><span data-stu-id="95562-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="95562-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="95562-558">int</span><span class="sxs-lookup"><span data-stu-id="95562-558">int</span></span></p></td>
<td><p><span data-ttu-id="95562-559">Tempo máximo de ida e volta para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="95562-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="95562-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="95562-561">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-p145">Média de MOS de rede de banda ampla para a chamada. Essa métrica depende da perda de pacote, da tremulação e do codec usado. O intervalo é de 1.0 a 5.0.</span><span class="sxs-lookup"><span data-stu-id="95562-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="95562-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="95562-566">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-567">Mínimo de MOS de rede de banda ampla para a chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="95562-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="95562-569">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-570">Pontuação média prevista de MOS de escuta de banda larga do áudio enviado, incluindo nível de fala, nível de ruído e características de dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="95562-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="95562-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="95562-572">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-573">SendListenMOS mínimo da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="95562-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="95562-575">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-576">Pontuação média prevista de MOS de escuta de banda larga do áudio recebido da rede, incluindo nível de fala, nível de ruído, codec, condições da rede e características do dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="95562-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="95562-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="95562-578">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="95562-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="95562-579">RecvListenMOS mínimo da chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95562-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="95562-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="95562-581">bits</span><span class="sxs-lookup"><span data-stu-id="95562-581">bit</span></span></p></td>
<td><p><span data-ttu-id="95562-582">Indica se o FEC de áudio foi usado para a chamada.</span><span class="sxs-lookup"><span data-stu-id="95562-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95562-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="95562-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="95562-584">bits</span><span class="sxs-lookup"><span data-stu-id="95562-584">bit</span></span></p></td>
<td><p><span data-ttu-id="95562-585">Indica a direção das informações de identidade declarada; 1 significa que a direção do fluxo é do chamador para o receptor; 0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="95562-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

