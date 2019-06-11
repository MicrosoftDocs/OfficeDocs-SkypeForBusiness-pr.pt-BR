---
title: 'Lync Server 2013: modo de exibição VideoStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95cc003a0e136a4a4c123355548b95c9566b4b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="5566b-102">Exibição VideoStreamDetail no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5566b-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5566b-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="5566b-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="5566b-104">A exibição VideoStreamDetail armazena informações sobre cada fluxo de vídeo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="5566b-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="5566b-105">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5566b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5566b-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="5566b-106">Column</span></span></th>
<th><span data-ttu-id="5566b-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="5566b-107">Data Type</span></span></th>
<th><span data-ttu-id="5566b-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="5566b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5566b-109">Sessiontime</span><span class="sxs-lookup"><span data-stu-id="5566b-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="5566b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="5566b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="5566b-111">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5566b-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="5566b-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="5566b-113">int</span><span class="sxs-lookup"><span data-stu-id="5566b-113">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-114">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5566b-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="5566b-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="5566b-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="5566b-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5566b-117">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5566b-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-118">Streamid</span><span class="sxs-lookup"><span data-stu-id="5566b-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="5566b-119">int</span><span class="sxs-lookup"><span data-stu-id="5566b-119">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-120">ID exclusiva dentro de uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="5566b-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-121">StartTime </span><span class="sxs-lookup"><span data-stu-id="5566b-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="5566b-122">datetime</span><span class="sxs-lookup"><span data-stu-id="5566b-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="5566b-123">Hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="5566b-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="5566b-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="5566b-125">datetime</span><span class="sxs-lookup"><span data-stu-id="5566b-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="5566b-126">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="5566b-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="5566b-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="5566b-128">int</span><span class="sxs-lookup"><span data-stu-id="5566b-128">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-129">Prioridade da chamada.</span><span class="sxs-lookup"><span data-stu-id="5566b-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="5566b-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="5566b-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5566b-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5566b-132">FQDN do pool de chamadas.</span><span class="sxs-lookup"><span data-stu-id="5566b-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="5566b-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="5566b-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5566b-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5566b-135">FQDN do pool do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-136">Chamador</span><span class="sxs-lookup"><span data-stu-id="5566b-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="5566b-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5566b-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5566b-138">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-139">Receptor</span><span class="sxs-lookup"><span data-stu-id="5566b-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="5566b-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5566b-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5566b-141">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="5566b-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="5566b-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5566b-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5566b-144">Cadeia de caracteres do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="5566b-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="5566b-146">smallint</span><span class="sxs-lookup"><span data-stu-id="5566b-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="5566b-147">Tipo de agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-147">Type of caller’s user agent.</span></span> <span data-ttu-id="5566b-148">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="5566b-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="5566b-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="5566b-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5566b-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5566b-151">Categoria do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-151">Category of caller’s user agent.</span></span> <span data-ttu-id="5566b-152">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="5566b-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="5566b-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="5566b-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5566b-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5566b-155">Cadeia de caracteres do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="5566b-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="5566b-157">smallint</span><span class="sxs-lookup"><span data-stu-id="5566b-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="5566b-158">Tipo de agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-158">Type of callee’s user agent.</span></span> <span data-ttu-id="5566b-159">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="5566b-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="5566b-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="5566b-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5566b-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5566b-162">Categoria do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-162">Category of callee’s user agent.</span></span> <span data-ttu-id="5566b-163">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="5566b-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="5566b-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="5566b-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5566b-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5566b-166">Nome do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="5566b-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="5566b-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5566b-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5566b-169">Nome do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="5566b-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="5566b-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5566b-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5566b-172">Sistema operacional (SO) do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="5566b-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="5566b-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5566b-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5566b-175">Sistema operacional (SO) do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="5566b-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="5566b-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5566b-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5566b-178">Nome da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="5566b-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="5566b-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5566b-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5566b-181">Nome da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="5566b-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="5566b-183">smallint</span><span class="sxs-lookup"><span data-stu-id="5566b-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="5566b-184">Número de núcleos da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="5566b-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="5566b-186">smallint</span><span class="sxs-lookup"><span data-stu-id="5566b-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="5566b-187">Número de núcleos da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="5566b-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="5566b-189">int</span><span class="sxs-lookup"><span data-stu-id="5566b-189">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-190">Velocidade do processador da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="5566b-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="5566b-192">int</span><span class="sxs-lookup"><span data-stu-id="5566b-192">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-193">Velocidade do processador da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="5566b-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="5566b-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="5566b-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5566b-196">Indica se o sistema do chamador está em execução em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="5566b-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="5566b-197">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5566b-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="5566b-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="5566b-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="5566b-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5566b-200">Indica se o sistema do chamador está em execução em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="5566b-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="5566b-201">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5566b-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="5566b-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="5566b-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="5566b-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5566b-204">Informações sobre o caminho de mídia, como direta ou retransmitida.</span><span class="sxs-lookup"><span data-stu-id="5566b-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="5566b-205">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5566b-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="5566b-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="5566b-207">int</span><span class="sxs-lookup"><span data-stu-id="5566b-207">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-208">Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-208">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="5566b-209">Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.</span><span class="sxs-lookup"><span data-stu-id="5566b-209">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="5566b-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="5566b-211">int</span><span class="sxs-lookup"><span data-stu-id="5566b-211">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-212">Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-212">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="5566b-213">Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.</span><span class="sxs-lookup"><span data-stu-id="5566b-213">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-214">SMTP</span><span class="sxs-lookup"><span data-stu-id="5566b-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="5566b-215">int</span><span class="sxs-lookup"><span data-stu-id="5566b-215">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-216">Tipo de transporte: 0 é UDP; 1 é o TCP.</span><span class="sxs-lookup"><span data-stu-id="5566b-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="5566b-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5566b-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="5566b-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5566b-219">Endereço IP do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-219">IP address of the caller.</span></span> <span data-ttu-id="5566b-220">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="5566b-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="5566b-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="5566b-222">int</span><span class="sxs-lookup"><span data-stu-id="5566b-222">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-223">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="5566b-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="5566b-225">bit</span><span class="sxs-lookup"><span data-stu-id="5566b-225">bit</span></span></p></td>
<td><p><span data-ttu-id="5566b-226">Indica se o chamador está dentro da rede da organização.</span><span class="sxs-lookup"><span data-stu-id="5566b-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="5566b-227">1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="5566b-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="5566b-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5566b-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="5566b-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5566b-230">Endereço IP do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-230">IP address of the callee.</span></span> <span data-ttu-id="5566b-231">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="5566b-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="5566b-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="5566b-233">int</span><span class="sxs-lookup"><span data-stu-id="5566b-233">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-234">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="5566b-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="5566b-236">bit</span><span class="sxs-lookup"><span data-stu-id="5566b-236">bit</span></span></p></td>
<td><p><span data-ttu-id="5566b-237">Indica se o chamador está dentro da rede da organização. 1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="5566b-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="5566b-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="5566b-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5566b-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5566b-240">Nome do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="5566b-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="5566b-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5566b-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5566b-243">Nome do país/região do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="5566b-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="5566b-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5566b-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5566b-246">Nome do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="5566b-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="5566b-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="5566b-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="5566b-249">Nome do país/região do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="5566b-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5566b-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="5566b-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5566b-252">Endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="5566b-253">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5566b-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="5566b-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="5566b-255">int</span><span class="sxs-lookup"><span data-stu-id="5566b-255">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-256">Porta no serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="5566b-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="5566b-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="5566b-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="5566b-259">Chave de endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="5566b-260">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5566b-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="5566b-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="5566b-262">int</span><span class="sxs-lookup"><span data-stu-id="5566b-262">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-263">Porta no serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="5566b-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="5566b-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5566b-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5566b-266">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="5566b-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="5566b-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5566b-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5566b-269">Nome do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="5566b-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5566b-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5566b-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5566b-272">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="5566b-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5566b-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5566b-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5566b-275">O nome do driver de dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="5566b-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="5566b-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5566b-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5566b-278">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="5566b-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="5566b-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5566b-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5566b-281">Nome do dispositivo de renderização do Calle.</span><span class="sxs-lookup"><span data-stu-id="5566b-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="5566b-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5566b-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5566b-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5566b-284">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="5566b-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="5566b-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="5566b-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5566b-287">Chame o nome do driver do dispositivo de processamento do recurso.</span><span class="sxs-lookup"><span data-stu-id="5566b-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="5566b-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="5566b-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="5566b-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5566b-290">Tipo de conexão de rede do chamador: 0 é cabeado, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="5566b-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="5566b-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="5566b-292">bit</span><span class="sxs-lookup"><span data-stu-id="5566b-292">bit</span></span></p></td>
<td><p><span data-ttu-id="5566b-293">Indica se o chamador se conecta ou não a uma rede virtual privada.</span><span class="sxs-lookup"><span data-stu-id="5566b-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="5566b-294">1 é uma rede virtual privada (VPN), 0 não é VPN.</span><span class="sxs-lookup"><span data-stu-id="5566b-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="5566b-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="5566b-296">decimal (18)</span><span class="sxs-lookup"><span data-stu-id="5566b-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="5566b-297">Velocidade do link de rede para o ponto de extremidade do chamador em bps.</span><span class="sxs-lookup"><span data-stu-id="5566b-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="5566b-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="5566b-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="5566b-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5566b-300">Tipo de conexão de rede do chamador: 0 é cabeado, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="5566b-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="5566b-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="5566b-302">bit</span><span class="sxs-lookup"><span data-stu-id="5566b-302">bit</span></span></p></td>
<td><p><span data-ttu-id="5566b-303">Indica se o chamador se conecta em uma rede virtual privada.</span><span class="sxs-lookup"><span data-stu-id="5566b-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="5566b-304">1 é uma rede virtual privada (VPN), 0 não é VPN.</span><span class="sxs-lookup"><span data-stu-id="5566b-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="5566b-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="5566b-306">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="5566b-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="5566b-307">Velocidade do link de rede para o ponto de extremidade do chamador (em bps).</span><span class="sxs-lookup"><span data-stu-id="5566b-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="5566b-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="5566b-309">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="5566b-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="5566b-310">O MOS de conversa de banda estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="5566b-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="5566b-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="5566b-312">int</span><span class="sxs-lookup"><span data-stu-id="5566b-312">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-313">A largura de banda real aplicada ao fluxo de envio do lado fornecido tem várias configurações de política (ativar, API, SDP, servidor de política e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="5566b-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="5566b-314">Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda mais econômica com base na estimativa de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="5566b-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="5566b-315">Isso é basicamente a largura de banda máxima que o fluxo de envio pode ter limites de bloqueio impostos pela estimativa da largura de banda.</span><span class="sxs-lookup"><span data-stu-id="5566b-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="5566b-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="5566b-317">int</span><span class="sxs-lookup"><span data-stu-id="5566b-317">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-318">Tremulação média de rede de estatísticas de protocolo de controle de tempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="5566b-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="5566b-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="5566b-320">int</span><span class="sxs-lookup"><span data-stu-id="5566b-320">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-321">Maior tremulação de rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="5566b-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-322">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="5566b-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="5566b-323">int</span><span class="sxs-lookup"><span data-stu-id="5566b-323">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-324">Tempo de ida e volta das estatísticas do RTCP.</span><span class="sxs-lookup"><span data-stu-id="5566b-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="5566b-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="5566b-326">int</span><span class="sxs-lookup"><span data-stu-id="5566b-326">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-327">Tempo máximo de ida e volta do fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="5566b-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="5566b-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="5566b-329">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="5566b-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="5566b-330">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="5566b-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="5566b-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="5566b-332">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="5566b-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="5566b-333">Perda máxima de pacote observado durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="5566b-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="5566b-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="5566b-335">int</span><span class="sxs-lookup"><span data-stu-id="5566b-335">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-336">Contagem de pacotes para o fluxo de vídeo (protocolo de transporte em tempo real, RTP).</span><span class="sxs-lookup"><span data-stu-id="5566b-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-337">Largura de banda</span><span class="sxs-lookup"><span data-stu-id="5566b-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="5566b-338">int</span><span class="sxs-lookup"><span data-stu-id="5566b-338">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-339">Estimativas de largura de banda para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="5566b-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="5566b-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="5566b-341">int</span><span class="sxs-lookup"><span data-stu-id="5566b-341">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-342">Codec de áudio usado para a chamada, referenciado pela <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5566b-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="5566b-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="5566b-344">caractere (9)</span><span class="sxs-lookup"><span data-stu-id="5566b-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="5566b-345">Resolução do vídeo em largura de pixels multiplicada pela altura de pixels.</span><span class="sxs-lookup"><span data-stu-id="5566b-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="5566b-346">Relatado como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5566b-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="5566b-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="5566b-348">int</span><span class="sxs-lookup"><span data-stu-id="5566b-348">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-349">Taxa média de bits do fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="5566b-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="5566b-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="5566b-351">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="5566b-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="5566b-352">Taxa de quadro de vídeo recebida.</span><span class="sxs-lookup"><span data-stu-id="5566b-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="5566b-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="5566b-354">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="5566b-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="5566b-355">Taxa de quadro de vídeo enviada.</span><span class="sxs-lookup"><span data-stu-id="5566b-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="5566b-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="5566b-357">int</span><span class="sxs-lookup"><span data-stu-id="5566b-357">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-358">Taxa máxima de bits de vídeo durante a sessão de vídeo.</span><span class="sxs-lookup"><span data-stu-id="5566b-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-359">À</span><span class="sxs-lookup"><span data-stu-id="5566b-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="5566b-360">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="5566b-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="5566b-361">Taxa de perda de pacotes de vídeo.</span><span class="sxs-lookup"><span data-stu-id="5566b-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="5566b-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="5566b-363">decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="5566b-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="5566b-364">Porcentagem total de quadros de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="5566b-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="5566b-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="5566b-366">bit</span><span class="sxs-lookup"><span data-stu-id="5566b-366">bit</span></span></p></td>
<td><p><span data-ttu-id="5566b-367">Não usado.</span><span class="sxs-lookup"><span data-stu-id="5566b-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="5566b-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="5566b-369">int</span><span class="sxs-lookup"><span data-stu-id="5566b-369">int</span></span></p></td>
<td><p><span data-ttu-id="5566b-370">Quantidade média de largura de banda alocada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="5566b-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5566b-371">À</span><span class="sxs-lookup"><span data-stu-id="5566b-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="5566b-372">decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="5566b-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="5566b-373">Porcentagem total de quadros de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="5566b-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5566b-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="5566b-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="5566b-375">bit</span><span class="sxs-lookup"><span data-stu-id="5566b-375">bit</span></span></p></td>
<td><p><span data-ttu-id="5566b-376">Direção de fluxo para informações de identidades p-declaradas.</span><span class="sxs-lookup"><span data-stu-id="5566b-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="5566b-377">1 significa que a direção do fluxo é do chamador para o receptor; 0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="5566b-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

