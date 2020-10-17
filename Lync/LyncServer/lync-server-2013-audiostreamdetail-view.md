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
ms.openlocfilehash: 4a9abfbc214e72cf059250910ecec4ad3bcdba33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515778"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="625ca-102">Exibição AudioStreamDetail no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="625ca-102">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="625ca-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="625ca-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="625ca-104">A exibição AudioStreamDetail armazena informações sobre cada fluxo de áudio no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="625ca-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="625ca-105">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="625ca-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="625ca-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="625ca-106">Column</span></span></th>
<th><span data-ttu-id="625ca-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="625ca-107">Data Type</span></span></th>
<th><span data-ttu-id="625ca-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="625ca-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="625ca-109">Sessiontime</span><span class="sxs-lookup"><span data-stu-id="625ca-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="625ca-110">datetime</span><span class="sxs-lookup"><span data-stu-id="625ca-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="625ca-111">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="625ca-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="625ca-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="625ca-113">int</span><span class="sxs-lookup"><span data-stu-id="625ca-113">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-114">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="625ca-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-115">Streamid</span><span class="sxs-lookup"><span data-stu-id="625ca-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="625ca-116">int</span><span class="sxs-lookup"><span data-stu-id="625ca-116">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-117">Identificação exclusiva em uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="625ca-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="625ca-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="625ca-119">datetime</span><span class="sxs-lookup"><span data-stu-id="625ca-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="625ca-120">Hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="625ca-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="625ca-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="625ca-122">datetime</span><span class="sxs-lookup"><span data-stu-id="625ca-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="625ca-123">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="625ca-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="625ca-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="625ca-125">bits</span><span class="sxs-lookup"><span data-stu-id="625ca-125">bit</span></span></p></td>
<td><p><span data-ttu-id="625ca-126">Categoria da caixa de diálogo: 0 é o servidor do Lync para o trecho do servidor de mediação; 1 é o servidor de mediação para o trecho do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="625ca-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="625ca-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="625ca-128">bits</span><span class="sxs-lookup"><span data-stu-id="625ca-128">bit</span></span></p></td>
<td><p><span data-ttu-id="625ca-129">Sinalizador que indica se a chamada foi ignorada ou não.</span><span class="sxs-lookup"><span data-stu-id="625ca-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="625ca-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="625ca-131">int</span><span class="sxs-lookup"><span data-stu-id="625ca-131">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p102">Se presente, indica porque uma chamada não foi ignorada, mesmo se as IDs de desvio correspondem. Apenas um valor é definido:</span><span class="sxs-lookup"><span data-stu-id="625ca-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="625ca-134">0x0001 - ID de desvio desconhecida ao adaptador de rede padrão.</span><span class="sxs-lookup"><span data-stu-id="625ca-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="625ca-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="625ca-136">int</span><span class="sxs-lookup"><span data-stu-id="625ca-136">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-137">Prioridade da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="625ca-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="625ca-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="625ca-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="625ca-140">Pool FQDN do chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="625ca-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="625ca-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="625ca-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="625ca-143">FQDN do pool do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-144">Chamador</span><span class="sxs-lookup"><span data-stu-id="625ca-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="625ca-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="625ca-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="625ca-146">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-147">Receptor</span><span class="sxs-lookup"><span data-stu-id="625ca-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="625ca-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="625ca-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="625ca-149">URI do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="625ca-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="625ca-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="625ca-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="625ca-152">String do agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="625ca-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="625ca-154">smallint</span><span class="sxs-lookup"><span data-stu-id="625ca-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="625ca-155">Tipo de agente do usuário do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="625ca-156">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="625ca-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="625ca-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="625ca-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="625ca-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="625ca-159">Categoria o agente do usuário do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="625ca-160">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="625ca-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="625ca-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="625ca-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="625ca-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="625ca-163">String de agente de usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="625ca-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="625ca-165">smallint</span><span class="sxs-lookup"><span data-stu-id="625ca-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="625ca-166">Tipo de agente do usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-166">Type of callee’s user agent.</span></span> <span data-ttu-id="625ca-167">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="625ca-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="625ca-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="625ca-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="625ca-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="625ca-170">Categoria do agente do usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-170">Category of callee’s user agent.</span></span> <span data-ttu-id="625ca-171">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="625ca-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="625ca-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="625ca-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="625ca-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="625ca-174">Nome de ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="625ca-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="625ca-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="625ca-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="625ca-177">Nome do ponto de extremidade do receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="625ca-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="625ca-179">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="625ca-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="625ca-180">Sistema operacional (OS) do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="625ca-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="625ca-182">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="625ca-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="625ca-183">Sistema operacional (OS) do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="625ca-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="625ca-185">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="625ca-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="625ca-186">Nome da CPU do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="625ca-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="625ca-188">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="625ca-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="625ca-189">Nome da CPU do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="625ca-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="625ca-191">smallint</span><span class="sxs-lookup"><span data-stu-id="625ca-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="625ca-192">Número de núcleos da CPU no ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="625ca-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="625ca-194">smallint</span><span class="sxs-lookup"><span data-stu-id="625ca-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="625ca-195">Número de núcleos da CPU no ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="625ca-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="625ca-197">int</span><span class="sxs-lookup"><span data-stu-id="625ca-197">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-198">Velocidade do processador da CPU do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="625ca-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="625ca-200">int</span><span class="sxs-lookup"><span data-stu-id="625ca-200">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-201">Velocidade do processador da CPU do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="625ca-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="625ca-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="625ca-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="625ca-204">Indica se o sistema do autor da chamada está funcionando em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="625ca-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="625ca-205">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="625ca-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="625ca-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="625ca-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="625ca-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="625ca-208">Indica que o sistema do receptor da chamada está funcionando em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="625ca-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="625ca-209">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="625ca-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="625ca-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="625ca-211">Chave de correlação.</span><span class="sxs-lookup"><span data-stu-id="625ca-211">Correlation key.</span></span> <span data-ttu-id="625ca-212">Referenciado da <a href="lync-server-2013-sessioncorrelation-table.md">tabela SessionCorrelation no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="625ca-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="625ca-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="625ca-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="625ca-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="625ca-215">Informações sobre o caminho de mídia, como direto ou retransmitido.</span><span class="sxs-lookup"><span data-stu-id="625ca-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="625ca-216">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="625ca-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="625ca-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="625ca-218">int</span><span class="sxs-lookup"><span data-stu-id="625ca-218">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p111">Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do autor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="625ca-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="625ca-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="625ca-222">int</span><span class="sxs-lookup"><span data-stu-id="625ca-222">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p112">Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do receptor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="625ca-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-225">Transport</span><span class="sxs-lookup"><span data-stu-id="625ca-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="625ca-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="625ca-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="625ca-227">Tipo de transporte: 0 é UDP, 1 é TCP.</span><span class="sxs-lookup"><span data-stu-id="625ca-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="625ca-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="625ca-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="625ca-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="625ca-230">Endereço IP do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-230">IP address of the caller.</span></span> <span data-ttu-id="625ca-231">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="625ca-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="625ca-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="625ca-233">int</span><span class="sxs-lookup"><span data-stu-id="625ca-233">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-234">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="625ca-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="625ca-236">bits</span><span class="sxs-lookup"><span data-stu-id="625ca-236">bit</span></span></p></td>
<td><p><span data-ttu-id="625ca-237">Indica se o chamador está na rede de intervalo: 1 significa que o chamador está na rede empresarial, 0 significa que está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="625ca-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="625ca-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="625ca-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="625ca-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="625ca-240">Endereço IP do receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-240">IP address of the callee.</span></span> <span data-ttu-id="625ca-241">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="625ca-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="625ca-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="625ca-243">int</span><span class="sxs-lookup"><span data-stu-id="625ca-243">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-244">Porta usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="625ca-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="625ca-246">bits</span><span class="sxs-lookup"><span data-stu-id="625ca-246">bit</span></span></p></td>
<td><p><span data-ttu-id="625ca-247">Indica se o receptor está na rede de intervalo: 1 significa que o receptor está na rede empresarial, 0 significa que está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="625ca-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="625ca-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="625ca-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="625ca-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="625ca-250">Nome do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="625ca-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="625ca-252">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="625ca-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="625ca-253">Nome do país/região do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="625ca-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="625ca-255">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="625ca-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="625ca-256">Nome do site do receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="625ca-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="625ca-258">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="625ca-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="625ca-259">Nome o país/região do site do receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="625ca-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="625ca-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="625ca-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="625ca-262">Endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="625ca-263">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="625ca-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="625ca-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="625ca-265">int</span><span class="sxs-lookup"><span data-stu-id="625ca-265">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-266">Port used on the A/V Edge service used by the caller.</span><span class="sxs-lookup"><span data-stu-id="625ca-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="625ca-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="625ca-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="625ca-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="625ca-269">Chave de endereço IP do serviço de borda A/V usado pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="625ca-270">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="625ca-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="625ca-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="625ca-272">int</span><span class="sxs-lookup"><span data-stu-id="625ca-272">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-273">Porta usada no serviço de borda A/V usado pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="625ca-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="625ca-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="625ca-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="625ca-276">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="625ca-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="625ca-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="625ca-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="625ca-279">Nome do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="625ca-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="625ca-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="625ca-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="625ca-282">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="625ca-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="625ca-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="625ca-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="625ca-285">Nome do driver do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="625ca-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="625ca-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="625ca-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="625ca-288">Nome do dispositivo de captura do receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="625ca-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="625ca-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="625ca-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="625ca-291">Nome do dispositivo de renderização do receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="625ca-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="625ca-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="625ca-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="625ca-294">Nome do driver do dispositivo de captura do receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="625ca-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="625ca-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="625ca-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="625ca-297">Nome do driver do dispositivo de renderização do receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="625ca-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="625ca-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="625ca-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="625ca-300">Tipo de conexão de rede do chamador: 0 é por fio, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="625ca-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="625ca-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="625ca-302">bits</span><span class="sxs-lookup"><span data-stu-id="625ca-302">bit</span></span></p></td>
<td><p><span data-ttu-id="625ca-303">Indica se o autor da chamada se conectou por uma rede privada virtual: 1 é a rede privada virtual (VPN), 0 é não VPN.</span><span class="sxs-lookup"><span data-stu-id="625ca-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="625ca-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="625ca-305">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="625ca-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="625ca-306">Velocidade da rede dos pontos de extremidade do chamador em bps.</span><span class="sxs-lookup"><span data-stu-id="625ca-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="625ca-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="625ca-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="625ca-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="625ca-309">Tipo de conexão de rede do receptor: 0 é por fio, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="625ca-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="625ca-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="625ca-311">bits</span><span class="sxs-lookup"><span data-stu-id="625ca-311">bit</span></span></p></td>
<td><p><span data-ttu-id="625ca-312">Indica se o autor da chamada se conectou por uma rede privada virtual: 1 é a rede privada virtual (VPN), 0 é não VPN.</span><span class="sxs-lookup"><span data-stu-id="625ca-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="625ca-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="625ca-314">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="625ca-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="625ca-315">Velocidade de rede do ponto de extremidade do receptor em bps.</span><span class="sxs-lookup"><span data-stu-id="625ca-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="625ca-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="625ca-317">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-318">MOS da Conversa de Banda Estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="625ca-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="625ca-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="625ca-320">int</span><span class="sxs-lookup"><span data-stu-id="625ca-320">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p117">Largura de banda aplicada a determinado fluxo de envio considerando várias configurações de política (TURN, API, SDP, Servidor de política etc.). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma menor largura de banda efetiva com base na estimativa de largura de banda. Isso é basicamente a largura de banda máxima a qual o fluxo de envio pode aceitar limites de bloqueio impostos pela estimativa de largura de banda</span><span class="sxs-lookup"><span data-stu-id="625ca-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="625ca-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="625ca-325">int</span><span class="sxs-lookup"><span data-stu-id="625ca-325">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-326">Média de tremulação de rede a partir da estatística do protocolo RTCP.</span><span class="sxs-lookup"><span data-stu-id="625ca-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="625ca-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="625ca-328">int</span><span class="sxs-lookup"><span data-stu-id="625ca-328">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-329">Tremulação máxima da rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="625ca-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="625ca-331">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="625ca-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="625ca-332">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="625ca-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="625ca-334">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="625ca-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="625ca-335">Perda máxima de pacotes observada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="625ca-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="625ca-337">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="625ca-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="625ca-338">Densidade média de perda de pacote durante picos de perdas em uma chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="625ca-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="625ca-340">int</span><span class="sxs-lookup"><span data-stu-id="625ca-340">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-341">Duração média de perda de pacote durante picos de perdas durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="625ca-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="625ca-343">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="625ca-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="625ca-344">Densidade média de perda de pacote durante intervalos entre picos de perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="625ca-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="625ca-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="625ca-346">int</span><span class="sxs-lookup"><span data-stu-id="625ca-346">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-347">Duração média de intervalos entre picos de perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="625ca-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="625ca-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="625ca-349">int</span><span class="sxs-lookup"><span data-stu-id="625ca-349">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-350">Contagem de pacotes para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="625ca-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-351">Mais largura de banda</span><span class="sxs-lookup"><span data-stu-id="625ca-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="625ca-352">int</span><span class="sxs-lookup"><span data-stu-id="625ca-352">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-353">Estimativas de largura de banda para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="625ca-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="625ca-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="625ca-355">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-p118">Degradação de MOS de rede para a chamada completa. O intervalo vai de 0,0 a 5,0. Essa métrica mostra o quanto o MOS de rede foi reduzido por causa de tremulação e perda de pacote. Para obter a qualidade aceitável, o MOS da rede deve ser menor que 0,5.</span><span class="sxs-lookup"><span data-stu-id="625ca-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="625ca-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="625ca-361">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-362">Degradação máxima de MOS de rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="625ca-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="625ca-364">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-365">Degradação de MOS de rede causada por tremulação.</span><span class="sxs-lookup"><span data-stu-id="625ca-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="625ca-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="625ca-367">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-368">Degradação de MOS de rede causada por perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="625ca-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="625ca-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="625ca-370">int</span><span class="sxs-lookup"><span data-stu-id="625ca-370">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-371">O codec de áudio usado para a chamada, referenciado pela <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="625ca-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="625ca-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="625ca-373">int</span><span class="sxs-lookup"><span data-stu-id="625ca-373">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-374">Taxa de amostragem para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="625ca-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="625ca-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="625ca-376">int</span><span class="sxs-lookup"><span data-stu-id="625ca-376">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p119">Nível do sinal de áudio de controle de ganho pós-analógico do áudio enviado pelo chamador. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="625ca-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="625ca-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="625ca-382">int</span><span class="sxs-lookup"><span data-stu-id="625ca-382">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p120">Nível do sinal de áudio do áudio recebido pelo chamador. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="625ca-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="625ca-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="625ca-388">int</span><span class="sxs-lookup"><span data-stu-id="625ca-388">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p121">Nível de ruído de áudio de controle de ganho pós-analógico do áudio enviado pelo chamador. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="625ca-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="625ca-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="625ca-394">int</span><span class="sxs-lookup"><span data-stu-id="625ca-394">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p122">Nível de ruído de áudio de controle de ganho pós-analógico do áudio recebido pelo chamado. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="625ca-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="625ca-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="625ca-400">int</span><span class="sxs-lookup"><span data-stu-id="625ca-400">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p123">Aprimoramento de perda e retorno de eco do chamador. A unidade desta medida é o dB. Valores mais baixos representam menos eco. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="625ca-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="625ca-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="625ca-406">int</span><span class="sxs-lookup"><span data-stu-id="625ca-406">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p124">Média de falhar por cinco minutos da renderização de alto-falante do chamador. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="625ca-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="625ca-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="625ca-411">int</span><span class="sxs-lookup"><span data-stu-id="625ca-411">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p125">Média de falhas por cinco minutos da captura de microfone do chamador. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="625ca-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="625ca-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="625ca-416">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-417">Taxa de descompasso de relógio do dispositivo de microfone do chamador, relativo ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="625ca-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="625ca-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="625ca-419">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-420">Taxa de descompasso de relógio de dispositivo do de alto-falante do chamador, relativo ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="625ca-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="625ca-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="625ca-422">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-423">Média de erro de registro de hora de fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="625ca-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="625ca-425">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-426">Média de erros de carimbo de data/hora do fluxo de renderização de alto-falante do chamador, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="625ca-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="625ca-428">smallint</span><span class="sxs-lookup"><span data-stu-id="625ca-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="625ca-429">Opção de voz é um modo meio-duplex com capacidade de interrupção reduzida.</span><span class="sxs-lookup"><span data-stu-id="625ca-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="625ca-430">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="625ca-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="625ca-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="625ca-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="625ca-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="625ca-433">Causas de um evento de eco para o chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="625ca-434">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="625ca-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="625ca-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="625ca-436">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-p128">Porcentagem de tempo quando ecos são detectados no fluxo de captura do microfone do chamador. Caso seja utilizado headset, o valor deve ser baixo.</span><span class="sxs-lookup"><span data-stu-id="625ca-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="625ca-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="625ca-440">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-p129">Porcentagem de tempo quando ecos são detectados no fluxo enviado pelo chamador. Uma alta porcentagem de eco em fluxos enviados indica um vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="625ca-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="625ca-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="625ca-444">int</span><span class="sxs-lookup"><span data-stu-id="625ca-444">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p130">Nível de sinal recebido no Servidor de mediação do Gateway para o áudio do chamador; isso se aplica apenas ao Servidor de mediação. A unidade desta medida é o dBoV. Para obter uma boa qualidade, o intervalo aceitável deve ser entre -30 a -18 dBoV.</span><span class="sxs-lookup"><span data-stu-id="625ca-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="625ca-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="625ca-449">int</span><span class="sxs-lookup"><span data-stu-id="625ca-449">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p131">Nível de sinal recebido na Servidor de mediação do Gateway para o áudio do chamador. Se aplica apenas ao Servidor de Mediação. A unidade desta medida é o dBoV. Para uma boa qualidade, a faixa aceitável deve ser menor do que -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="625ca-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="625ca-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="625ca-455">int</span><span class="sxs-lookup"><span data-stu-id="625ca-455">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-456">Controle de ganho automático (AGC) no Servidor de mediação aplicado ao áudio do chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="625ca-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="625ca-458">flutuação</span><span class="sxs-lookup"><span data-stu-id="625ca-458">float</span></span></p></td>
<td><p><span data-ttu-id="625ca-459">Raiz quadrada média (RMS) o sinal de entrada para o chamador pelos 30 primeiros segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="625ca-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="625ca-461">int</span><span class="sxs-lookup"><span data-stu-id="625ca-461">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p132">Representa o nível de sinal de áudio de controle de ganho pós-analógico do áudio enviado pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="625ca-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="625ca-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="625ca-467">int</span><span class="sxs-lookup"><span data-stu-id="625ca-467">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p133">Nível do sinal de áudio do áudio recebido pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="625ca-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="625ca-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="625ca-473">int</span><span class="sxs-lookup"><span data-stu-id="625ca-473">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p134">Nível de ruído de áudio de controle de ganho pós-analógico do áudio enviado pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="625ca-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="625ca-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="625ca-479">int</span><span class="sxs-lookup"><span data-stu-id="625ca-479">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p135">Nível de ruído de áudio de controle de ganho pós-analógico do áudio recebido pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="625ca-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="625ca-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="625ca-485">int</span><span class="sxs-lookup"><span data-stu-id="625ca-485">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p136">Aprimoramento de perda e retorno de eco do receptor. A unidade desta medida é o dB. Valores mais baixos representam menos eco. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="625ca-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="625ca-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="625ca-491">int</span><span class="sxs-lookup"><span data-stu-id="625ca-491">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p137">Média de falhas por cinco minutos da renderização de alto-falante do receptor. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="625ca-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="625ca-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="625ca-496">int</span><span class="sxs-lookup"><span data-stu-id="625ca-496">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p138">Média de falhas por cinco minutos da captura de microfone do receptor. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.</span><span class="sxs-lookup"><span data-stu-id="625ca-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="625ca-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="625ca-501">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-502">Taxa de descompasso do relógio do dispositivo de microfone do receptor, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="625ca-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="625ca-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="625ca-504">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-505">Taxa de descompasso do relógio do dispositivo de alto-falante do receptor, relativa ao relógio da CPU.</span><span class="sxs-lookup"><span data-stu-id="625ca-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="625ca-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="625ca-507">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-508">Média de erro de registro de hora de fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="625ca-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="625ca-510">decimal (9, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-511">Médio de erro de carimbo de data/hora do fluxo de renderização de alto-falante do receptor, em milissegundos, nos últimos 20 segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="625ca-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="625ca-513">smallint</span><span class="sxs-lookup"><span data-stu-id="625ca-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="625ca-514">Opção de voz é um modo meio-duplex com capacidade de interrupção reduzida.</span><span class="sxs-lookup"><span data-stu-id="625ca-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="625ca-515">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="625ca-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="625ca-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="625ca-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="625ca-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="625ca-518">Causa um evento de eco para o receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="625ca-519">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="625ca-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="625ca-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="625ca-521">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-p141">Porcentagem de tempo quando ecos são detectados no fluxo de captura do microfone do receptor. Caso seja utilizado headset, o valor deve ser baixo.</span><span class="sxs-lookup"><span data-stu-id="625ca-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="625ca-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="625ca-525">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-p142">Porcentagem de tempo quando ecos são detectados no fluxo de envio do receptor. Uma alta porcentagem de eco em fluxos enviados indica um vazamento de eco.</span><span class="sxs-lookup"><span data-stu-id="625ca-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="625ca-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="625ca-529">int</span><span class="sxs-lookup"><span data-stu-id="625ca-529">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p143">Nível de sinal recebido no Servidor de mediação do Gateway para o áudio do receptor; isso se aplica apenas ao Servidor de mediação. A unidade desta medida é o dBoV. Para uma boa qualidade, a faixa aceitável deve ser de [-30 a -18] dBoV.</span><span class="sxs-lookup"><span data-stu-id="625ca-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="625ca-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="625ca-534">int</span><span class="sxs-lookup"><span data-stu-id="625ca-534">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-p144">Nível de sinal recebido no Servidor de mediação do Gateway para o áudio do receptor. Se aplica apenas ao Servidor de Mediação. A unidade desta medida é o dBoV. Para uma boa qualidade, a faixa aceitável deve ser menor do que -50 dBoV.</span><span class="sxs-lookup"><span data-stu-id="625ca-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="625ca-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="625ca-540">int</span><span class="sxs-lookup"><span data-stu-id="625ca-540">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-541">Controle de ganho automático (AGC) no Servidor de mediação aplicado ao áudio do receptor.</span><span class="sxs-lookup"><span data-stu-id="625ca-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="625ca-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="625ca-543">flutuação</span><span class="sxs-lookup"><span data-stu-id="625ca-543">float</span></span></p></td>
<td><p><span data-ttu-id="625ca-544">Raiz quadrada média (RMS) do sinal de entrada para o receptor durante os 30 primeiros segundos da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="625ca-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="625ca-546">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-547">Taxa média de amostras escondidas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="625ca-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="625ca-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="625ca-549">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-550">Taxa média de amostras corrigidas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="625ca-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="625ca-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="625ca-552">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-553">Taxa média de amostras compactadas geradas pelo reparo de áudio para exemplos típicos.</span><span class="sxs-lookup"><span data-stu-id="625ca-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-554">Aproxima</span><span class="sxs-lookup"><span data-stu-id="625ca-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="625ca-555">int</span><span class="sxs-lookup"><span data-stu-id="625ca-555">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-556">Tempo de ida e volta de estatísticas RTCP.</span><span class="sxs-lookup"><span data-stu-id="625ca-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="625ca-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="625ca-558">int</span><span class="sxs-lookup"><span data-stu-id="625ca-558">int</span></span></p></td>
<td><p><span data-ttu-id="625ca-559">Tempo máximo de ida e volta para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="625ca-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="625ca-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="625ca-561">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-p145">Média de MOS de rede de banda ampla para a chamada. Essa métrica depende da perda de pacote, da tremulação e do codec usado. O intervalo é de 1.0 a 5.0.</span><span class="sxs-lookup"><span data-stu-id="625ca-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="625ca-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="625ca-566">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-567">Mínimo de MOS de rede de banda ampla para a chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="625ca-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="625ca-569">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-570">Pontuação média prevista de MOS de escuta de banda larga do áudio enviado, incluindo nível de fala, nível de ruído e características de dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="625ca-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="625ca-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="625ca-572">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-573">SendListenMOS mínimo da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="625ca-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="625ca-575">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-576">Pontuação média prevista de MOS de escuta de banda larga do áudio recebido da rede, incluindo nível de fala, nível de ruído, codec, condições da rede e características do dispositivo de captura.</span><span class="sxs-lookup"><span data-stu-id="625ca-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="625ca-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="625ca-578">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="625ca-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="625ca-579">RecvListenMOS mínimo da chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="625ca-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="625ca-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="625ca-581">bits</span><span class="sxs-lookup"><span data-stu-id="625ca-581">bit</span></span></p></td>
<td><p><span data-ttu-id="625ca-582">Indica se o FEC de áudio foi usado para a chamada.</span><span class="sxs-lookup"><span data-stu-id="625ca-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="625ca-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="625ca-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="625ca-584">bits</span><span class="sxs-lookup"><span data-stu-id="625ca-584">bit</span></span></p></td>
<td><p><span data-ttu-id="625ca-585">Indica a direção das informações de identidade declarada; 1 significa que a direção do fluxo é do chamador para o receptor; 0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="625ca-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

