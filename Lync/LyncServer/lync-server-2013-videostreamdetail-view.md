---
title: 'Lync Server 2013: modo de exibição VideoStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfa754fbcc24377b07bab3b13473adb1c5e953ea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="305dd-102">Exibição VideoStreamDetail no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="305dd-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="305dd-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="305dd-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="305dd-104">A exibição VideoStreamDetail armazena informações sobre cada fluxo de vídeo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="305dd-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="305dd-105">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="305dd-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="305dd-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="305dd-106">Column</span></span></th>
<th><span data-ttu-id="305dd-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="305dd-107">Data Type</span></span></th>
<th><span data-ttu-id="305dd-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="305dd-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="305dd-109">Sessiontime</span><span class="sxs-lookup"><span data-stu-id="305dd-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="305dd-110">datetime</span><span class="sxs-lookup"><span data-stu-id="305dd-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="305dd-111">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="305dd-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="305dd-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="305dd-113">int</span><span class="sxs-lookup"><span data-stu-id="305dd-113">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-114">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="305dd-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="305dd-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="305dd-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="305dd-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="305dd-117">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="305dd-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-118">Streamid</span><span class="sxs-lookup"><span data-stu-id="305dd-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="305dd-119">int</span><span class="sxs-lookup"><span data-stu-id="305dd-119">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-120">ID exclusiva dentro de uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="305dd-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-121">StartTime </span><span class="sxs-lookup"><span data-stu-id="305dd-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="305dd-122">datetime</span><span class="sxs-lookup"><span data-stu-id="305dd-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="305dd-123">Hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="305dd-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="305dd-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="305dd-125">datetime</span><span class="sxs-lookup"><span data-stu-id="305dd-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="305dd-126">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="305dd-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="305dd-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="305dd-128">int</span><span class="sxs-lookup"><span data-stu-id="305dd-128">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-129">Prioridade da chamada.</span><span class="sxs-lookup"><span data-stu-id="305dd-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="305dd-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="305dd-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="305dd-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="305dd-132">FQDN do pool de chamadas.</span><span class="sxs-lookup"><span data-stu-id="305dd-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="305dd-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="305dd-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="305dd-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="305dd-135">FQDN do pool do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-136">Chamador</span><span class="sxs-lookup"><span data-stu-id="305dd-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="305dd-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="305dd-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="305dd-138">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-139">Receptor</span><span class="sxs-lookup"><span data-stu-id="305dd-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="305dd-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="305dd-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="305dd-141">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="305dd-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="305dd-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="305dd-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="305dd-144">Cadeia de caracteres do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="305dd-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="305dd-146">smallint</span><span class="sxs-lookup"><span data-stu-id="305dd-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="305dd-147">Tipo de agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-147">Type of caller’s user agent.</span></span> <span data-ttu-id="305dd-148">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="305dd-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="305dd-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="305dd-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="305dd-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="305dd-151">Categoria do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-151">Category of caller’s user agent.</span></span> <span data-ttu-id="305dd-152">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="305dd-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="305dd-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="305dd-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="305dd-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="305dd-155">Cadeia de caracteres do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="305dd-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="305dd-157">smallint</span><span class="sxs-lookup"><span data-stu-id="305dd-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="305dd-158">Tipo de agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-158">Type of callee’s user agent.</span></span> <span data-ttu-id="305dd-159">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="305dd-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="305dd-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="305dd-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="305dd-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="305dd-162">Categoria do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-162">Category of callee’s user agent.</span></span> <span data-ttu-id="305dd-163">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="305dd-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="305dd-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="305dd-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="305dd-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="305dd-166">Nome do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="305dd-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="305dd-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="305dd-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="305dd-169">Nome do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="305dd-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="305dd-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="305dd-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="305dd-172">Sistema operacional (SO) do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="305dd-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="305dd-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="305dd-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="305dd-175">Sistema operacional (SO) do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="305dd-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="305dd-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="305dd-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="305dd-178">Nome da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="305dd-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="305dd-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="305dd-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="305dd-181">Nome da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="305dd-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="305dd-183">smallint</span><span class="sxs-lookup"><span data-stu-id="305dd-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="305dd-184">Número de núcleos da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="305dd-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="305dd-186">smallint</span><span class="sxs-lookup"><span data-stu-id="305dd-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="305dd-187">Número de núcleos da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="305dd-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="305dd-189">int</span><span class="sxs-lookup"><span data-stu-id="305dd-189">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-190">Velocidade do processador da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="305dd-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="305dd-192">int</span><span class="sxs-lookup"><span data-stu-id="305dd-192">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-193">Velocidade do processador da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="305dd-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="305dd-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="305dd-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="305dd-196">Indica se o sistema do chamador está em execução em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="305dd-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="305dd-197">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="305dd-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="305dd-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="305dd-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="305dd-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="305dd-200">Indica se o sistema do chamador está em execução em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="305dd-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="305dd-201">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="305dd-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="305dd-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="305dd-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="305dd-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="305dd-204">Informações sobre o caminho de mídia, como direta ou retransmitida.</span><span class="sxs-lookup"><span data-stu-id="305dd-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="305dd-205">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="305dd-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="305dd-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="305dd-207">int</span><span class="sxs-lookup"><span data-stu-id="305dd-207">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-208">Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-208">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="305dd-209">Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.</span><span class="sxs-lookup"><span data-stu-id="305dd-209">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="305dd-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="305dd-211">int</span><span class="sxs-lookup"><span data-stu-id="305dd-211">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-212">Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-212">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="305dd-213">Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.</span><span class="sxs-lookup"><span data-stu-id="305dd-213">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-214">SMTP</span><span class="sxs-lookup"><span data-stu-id="305dd-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="305dd-215">int</span><span class="sxs-lookup"><span data-stu-id="305dd-215">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-216">Tipo de transporte: 0 é UDP; 1 é o TCP.</span><span class="sxs-lookup"><span data-stu-id="305dd-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="305dd-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="305dd-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="305dd-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="305dd-219">Endereço IP do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-219">IP address of the caller.</span></span> <span data-ttu-id="305dd-220">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="305dd-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="305dd-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="305dd-222">int</span><span class="sxs-lookup"><span data-stu-id="305dd-222">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-223">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="305dd-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="305dd-225">bit</span><span class="sxs-lookup"><span data-stu-id="305dd-225">bit</span></span></p></td>
<td><p><span data-ttu-id="305dd-226">Indica se o chamador está dentro da rede da organização.</span><span class="sxs-lookup"><span data-stu-id="305dd-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="305dd-227">1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="305dd-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="305dd-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="305dd-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="305dd-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="305dd-230">Endereço IP do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-230">IP address of the callee.</span></span> <span data-ttu-id="305dd-231">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="305dd-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="305dd-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="305dd-233">int</span><span class="sxs-lookup"><span data-stu-id="305dd-233">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-234">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="305dd-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="305dd-236">bit</span><span class="sxs-lookup"><span data-stu-id="305dd-236">bit</span></span></p></td>
<td><p><span data-ttu-id="305dd-237">Indica se o chamador está dentro da rede da organização. 1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="305dd-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="305dd-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="305dd-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="305dd-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="305dd-240">Nome do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="305dd-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="305dd-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="305dd-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="305dd-243">Nome do país/região do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="305dd-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="305dd-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="305dd-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="305dd-246">Nome do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="305dd-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="305dd-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="305dd-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="305dd-249">Nome do país/região do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="305dd-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="305dd-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="305dd-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="305dd-252">Endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="305dd-253">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="305dd-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="305dd-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="305dd-255">int</span><span class="sxs-lookup"><span data-stu-id="305dd-255">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-256">Porta no serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="305dd-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="305dd-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="305dd-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="305dd-259">Chave de endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="305dd-260">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="305dd-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="305dd-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="305dd-262">int</span><span class="sxs-lookup"><span data-stu-id="305dd-262">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-263">Porta no serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="305dd-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="305dd-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="305dd-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="305dd-266">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="305dd-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="305dd-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="305dd-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="305dd-269">Nome do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="305dd-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="305dd-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="305dd-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="305dd-272">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="305dd-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="305dd-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="305dd-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="305dd-275">O nome do driver de dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="305dd-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="305dd-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="305dd-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="305dd-278">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="305dd-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="305dd-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="305dd-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="305dd-281">Nome do dispositivo de renderização do Calle.</span><span class="sxs-lookup"><span data-stu-id="305dd-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="305dd-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="305dd-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="305dd-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="305dd-284">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="305dd-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="305dd-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="305dd-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="305dd-287">Chame o nome do driver do dispositivo de processamento do recurso.</span><span class="sxs-lookup"><span data-stu-id="305dd-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="305dd-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="305dd-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="305dd-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="305dd-290">Tipo de conexão de rede do chamador: 0 é cabeado, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="305dd-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="305dd-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="305dd-292">bit</span><span class="sxs-lookup"><span data-stu-id="305dd-292">bit</span></span></p></td>
<td><p><span data-ttu-id="305dd-293">Indica se o chamador se conecta ou não a uma rede virtual privada.</span><span class="sxs-lookup"><span data-stu-id="305dd-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="305dd-294">1 é uma rede virtual privada (VPN), 0 não é VPN.</span><span class="sxs-lookup"><span data-stu-id="305dd-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="305dd-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="305dd-296">decimal (18)</span><span class="sxs-lookup"><span data-stu-id="305dd-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="305dd-297">Velocidade do link de rede para o ponto de extremidade do chamador em bps.</span><span class="sxs-lookup"><span data-stu-id="305dd-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="305dd-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="305dd-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="305dd-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="305dd-300">Tipo de conexão de rede do chamador: 0 é cabeado, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="305dd-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="305dd-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="305dd-302">bit</span><span class="sxs-lookup"><span data-stu-id="305dd-302">bit</span></span></p></td>
<td><p><span data-ttu-id="305dd-303">Indica se o chamador se conecta em uma rede virtual privada.</span><span class="sxs-lookup"><span data-stu-id="305dd-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="305dd-304">1 é uma rede virtual privada (VPN), 0 não é VPN.</span><span class="sxs-lookup"><span data-stu-id="305dd-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="305dd-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="305dd-306">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="305dd-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="305dd-307">Velocidade do link de rede para o ponto de extremidade do chamador (em bps).</span><span class="sxs-lookup"><span data-stu-id="305dd-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="305dd-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="305dd-309">decimal (3; 2)</span><span class="sxs-lookup"><span data-stu-id="305dd-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="305dd-310">O MOS de conversa de banda estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="305dd-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="305dd-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="305dd-312">int</span><span class="sxs-lookup"><span data-stu-id="305dd-312">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-313">A largura de banda real aplicada ao fluxo de envio do lado fornecido tem várias configurações de política (ativar, API, SDP, servidor de política e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="305dd-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="305dd-314">Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda mais econômica com base na estimativa de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="305dd-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="305dd-315">Isso é basicamente a largura de banda máxima que o fluxo de envio pode ter limites de bloqueio impostos pela estimativa da largura de banda.</span><span class="sxs-lookup"><span data-stu-id="305dd-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="305dd-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="305dd-317">int</span><span class="sxs-lookup"><span data-stu-id="305dd-317">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-318">Tremulação média de rede de estatísticas de protocolo de controle de tempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="305dd-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="305dd-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="305dd-320">int</span><span class="sxs-lookup"><span data-stu-id="305dd-320">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-321">Maior tremulação de rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="305dd-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-322">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="305dd-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="305dd-323">int</span><span class="sxs-lookup"><span data-stu-id="305dd-323">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-324">Tempo de ida e volta das estatísticas do RTCP.</span><span class="sxs-lookup"><span data-stu-id="305dd-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="305dd-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="305dd-326">int</span><span class="sxs-lookup"><span data-stu-id="305dd-326">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-327">Tempo máximo de ida e volta do fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="305dd-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="305dd-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="305dd-329">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="305dd-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="305dd-330">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="305dd-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="305dd-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="305dd-332">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="305dd-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="305dd-333">Perda máxima de pacote observado durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="305dd-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="305dd-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="305dd-335">int</span><span class="sxs-lookup"><span data-stu-id="305dd-335">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-336">Contagem de pacotes para o fluxo de vídeo (protocolo de transporte em tempo real, RTP).</span><span class="sxs-lookup"><span data-stu-id="305dd-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-337">Largura de banda</span><span class="sxs-lookup"><span data-stu-id="305dd-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="305dd-338">int</span><span class="sxs-lookup"><span data-stu-id="305dd-338">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-339">Estimativas de largura de banda para o fluxo de áudio.</span><span class="sxs-lookup"><span data-stu-id="305dd-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="305dd-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="305dd-341">int</span><span class="sxs-lookup"><span data-stu-id="305dd-341">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-342">Codec de áudio usado para a chamada, referenciado pela <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="305dd-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="305dd-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="305dd-344">caractere (9)</span><span class="sxs-lookup"><span data-stu-id="305dd-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="305dd-345">Resolução do vídeo em largura de pixels multiplicada pela altura de pixels.</span><span class="sxs-lookup"><span data-stu-id="305dd-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="305dd-346">Relatado como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="305dd-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="305dd-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="305dd-348">int</span><span class="sxs-lookup"><span data-stu-id="305dd-348">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-349">Taxa média de bits do fluxo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="305dd-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="305dd-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="305dd-351">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="305dd-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="305dd-352">Taxa de quadro de vídeo recebida.</span><span class="sxs-lookup"><span data-stu-id="305dd-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="305dd-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="305dd-354">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="305dd-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="305dd-355">Taxa de quadro de vídeo enviada.</span><span class="sxs-lookup"><span data-stu-id="305dd-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="305dd-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="305dd-357">int</span><span class="sxs-lookup"><span data-stu-id="305dd-357">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-358">Taxa máxima de bits de vídeo durante a sessão de vídeo.</span><span class="sxs-lookup"><span data-stu-id="305dd-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-359">À</span><span class="sxs-lookup"><span data-stu-id="305dd-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="305dd-360">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="305dd-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="305dd-361">Taxa de perda de pacotes de vídeo.</span><span class="sxs-lookup"><span data-stu-id="305dd-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="305dd-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="305dd-363">decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="305dd-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="305dd-364">Porcentagem total de quadros de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="305dd-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="305dd-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="305dd-366">bit</span><span class="sxs-lookup"><span data-stu-id="305dd-366">bit</span></span></p></td>
<td><p><span data-ttu-id="305dd-367">Não usado.</span><span class="sxs-lookup"><span data-stu-id="305dd-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="305dd-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="305dd-369">int</span><span class="sxs-lookup"><span data-stu-id="305dd-369">int</span></span></p></td>
<td><p><span data-ttu-id="305dd-370">Quantidade média de largura de banda alocada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="305dd-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="305dd-371">À</span><span class="sxs-lookup"><span data-stu-id="305dd-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="305dd-372">decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="305dd-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="305dd-373">Porcentagem total de quadros de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="305dd-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="305dd-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="305dd-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="305dd-375">bit</span><span class="sxs-lookup"><span data-stu-id="305dd-375">bit</span></span></p></td>
<td><p><span data-ttu-id="305dd-376">Direção de fluxo para informações de identidades p-declaradas.</span><span class="sxs-lookup"><span data-stu-id="305dd-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="305dd-377">1 significa que a direção do fluxo é do chamador para o receptor; 0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="305dd-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

