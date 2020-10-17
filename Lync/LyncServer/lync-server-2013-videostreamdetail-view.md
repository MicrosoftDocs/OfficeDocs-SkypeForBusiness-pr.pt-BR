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
ms.openlocfilehash: 3d419800842fed080efe4005e7282a25c91f29df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518518"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="48994-102">Exibição VideoStreamDetail no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48994-102">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48994-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="48994-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="48994-104">A Exibição VideoStreamDetail armazena informações sobre cada stream de vídeo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="48994-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="48994-105">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48994-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48994-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="48994-106">Column</span></span></th>
<th><span data-ttu-id="48994-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="48994-107">Data Type</span></span></th>
<th><span data-ttu-id="48994-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="48994-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48994-109">Sessiontime</span><span class="sxs-lookup"><span data-stu-id="48994-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="48994-110">datetime</span><span class="sxs-lookup"><span data-stu-id="48994-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="48994-111">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="48994-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="48994-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="48994-113">int</span><span class="sxs-lookup"><span data-stu-id="48994-113">int</span></span></p></td>
<td><p><span data-ttu-id="48994-114">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="48994-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="48994-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="48994-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="48994-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="48994-117">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="48994-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-118">Streamid</span><span class="sxs-lookup"><span data-stu-id="48994-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="48994-119">int</span><span class="sxs-lookup"><span data-stu-id="48994-119">int</span></span></p></td>
<td><p><span data-ttu-id="48994-120">Identificação exclusiva em uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="48994-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="48994-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="48994-122">datetime</span><span class="sxs-lookup"><span data-stu-id="48994-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="48994-123">Hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="48994-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="48994-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="48994-125">datetime</span><span class="sxs-lookup"><span data-stu-id="48994-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="48994-126">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="48994-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="48994-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="48994-128">int</span><span class="sxs-lookup"><span data-stu-id="48994-128">int</span></span></p></td>
<td><p><span data-ttu-id="48994-129">Prioridade da chamada.</span><span class="sxs-lookup"><span data-stu-id="48994-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="48994-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="48994-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="48994-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48994-132">Pool FQDN do chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="48994-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="48994-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="48994-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48994-135">FQDN do pool do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="48994-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-136">Chamador</span><span class="sxs-lookup"><span data-stu-id="48994-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="48994-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="48994-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="48994-138">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-139">Receptor</span><span class="sxs-lookup"><span data-stu-id="48994-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="48994-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="48994-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="48994-141">URI do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="48994-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="48994-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="48994-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="48994-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48994-144">String do agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="48994-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="48994-146">smallint</span><span class="sxs-lookup"><span data-stu-id="48994-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="48994-147">Tipo de agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-147">Type of caller’s user agent.</span></span> <span data-ttu-id="48994-148">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="48994-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="48994-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="48994-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="48994-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="48994-151">Categoria do agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-151">Category of caller’s user agent.</span></span> <span data-ttu-id="48994-152">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="48994-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="48994-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="48994-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="48994-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48994-155">String de agente de usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="48994-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="48994-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="48994-157">smallint</span><span class="sxs-lookup"><span data-stu-id="48994-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="48994-158">Tipo de agente do usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="48994-158">Type of callee’s user agent.</span></span> <span data-ttu-id="48994-159">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="48994-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="48994-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="48994-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="48994-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="48994-162">Categoria do agente do usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="48994-162">Category of callee’s user agent.</span></span> <span data-ttu-id="48994-163">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="48994-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="48994-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="48994-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="48994-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48994-166">Nome de ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="48994-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="48994-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="48994-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48994-169">Nome do ponto de extremidade do receptor.</span><span class="sxs-lookup"><span data-stu-id="48994-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="48994-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="48994-171">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="48994-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="48994-172">Sistema operacional (OS) do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="48994-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="48994-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="48994-174">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="48994-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="48994-175">Sistema operacional (OS) do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="48994-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="48994-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="48994-177">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="48994-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="48994-178">Nome da CPU do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="48994-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="48994-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="48994-180">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="48994-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="48994-181">Nome da CPU do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="48994-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="48994-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="48994-183">smallint</span><span class="sxs-lookup"><span data-stu-id="48994-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="48994-184">Número de núcleos da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="48994-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="48994-186">smallint</span><span class="sxs-lookup"><span data-stu-id="48994-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="48994-187">Número de núcleos da CPU do ponto de extremidade do chamado.</span><span class="sxs-lookup"><span data-stu-id="48994-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="48994-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="48994-189">int</span><span class="sxs-lookup"><span data-stu-id="48994-189">int</span></span></p></td>
<td><p><span data-ttu-id="48994-190">Velocidade do processador da CPU do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="48994-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="48994-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="48994-192">int</span><span class="sxs-lookup"><span data-stu-id="48994-192">int</span></span></p></td>
<td><p><span data-ttu-id="48994-193">Velocidade do processador da CPU do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="48994-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="48994-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="48994-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="48994-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="48994-196">Indica se o sistema do autor da chamada está funcionando em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="48994-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="48994-197">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="48994-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="48994-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="48994-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="48994-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="48994-200">Indica que o sistema do receptor da chamada está funcionando em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="48994-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="48994-201">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="48994-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="48994-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="48994-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="48994-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="48994-204">Informações sobre o caminho de mídia, como direto ou transmitido.</span><span class="sxs-lookup"><span data-stu-id="48994-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="48994-205">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="48994-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="48994-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="48994-207">int</span><span class="sxs-lookup"><span data-stu-id="48994-207">int</span></span></p></td>
<td><p><span data-ttu-id="48994-p109">Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do autor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="48994-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="48994-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="48994-211">int</span><span class="sxs-lookup"><span data-stu-id="48994-211">int</span></span></p></td>
<td><p><span data-ttu-id="48994-p110">Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do receptor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="48994-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-214">Transport</span><span class="sxs-lookup"><span data-stu-id="48994-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="48994-215">int</span><span class="sxs-lookup"><span data-stu-id="48994-215">int</span></span></p></td>
<td><p><span data-ttu-id="48994-216">Tipo de transporte: 0 é UDP, 1 é TCP.</span><span class="sxs-lookup"><span data-stu-id="48994-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="48994-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="48994-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="48994-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="48994-219">Endereço IP do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="48994-219">IP address of the caller.</span></span> <span data-ttu-id="48994-220">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="48994-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="48994-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="48994-222">int</span><span class="sxs-lookup"><span data-stu-id="48994-222">int</span></span></p></td>
<td><p><span data-ttu-id="48994-223">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="48994-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="48994-225">bits</span><span class="sxs-lookup"><span data-stu-id="48994-225">bit</span></span></p></td>
<td><p><span data-ttu-id="48994-p112">Indica se o chamador está dentro da rede da organização. 1 significa que o chamador está dentro da rede da empresa, 0 significa que o chamador está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="48994-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="48994-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="48994-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="48994-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="48994-230">Endereço IP do receptor.</span><span class="sxs-lookup"><span data-stu-id="48994-230">IP address of the callee.</span></span> <span data-ttu-id="48994-231">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="48994-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="48994-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="48994-233">int</span><span class="sxs-lookup"><span data-stu-id="48994-233">int</span></span></p></td>
<td><p><span data-ttu-id="48994-234">Porta usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="48994-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="48994-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="48994-236">bits</span><span class="sxs-lookup"><span data-stu-id="48994-236">bit</span></span></p></td>
<td><p><span data-ttu-id="48994-237">Indica se o chamado está dentro da rede da organização. 1 significa que o chamado está dentro da rede da empresa, 0 significa que o chamado está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="48994-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="48994-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="48994-239">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="48994-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="48994-240">Nome do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="48994-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="48994-242">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="48994-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="48994-243">Nome do país/região do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="48994-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="48994-245">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="48994-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="48994-246">Nome do site do receptor.</span><span class="sxs-lookup"><span data-stu-id="48994-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="48994-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="48994-248">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="48994-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="48994-249">Nome o país/região do site do receptor.</span><span class="sxs-lookup"><span data-stu-id="48994-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="48994-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="48994-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="48994-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="48994-252">Endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="48994-253">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="48994-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="48994-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="48994-255">int</span><span class="sxs-lookup"><span data-stu-id="48994-255">int</span></span></p></td>
<td><p><span data-ttu-id="48994-256">Porta no serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="48994-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="48994-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="48994-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="48994-259">Chave de endereço IP do serviço de borda A/V usado pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="48994-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="48994-260">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="48994-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="48994-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="48994-262">int</span><span class="sxs-lookup"><span data-stu-id="48994-262">int</span></span></p></td>
<td><p><span data-ttu-id="48994-263">Porta no serviço de borda A/V usada pelo chamado.</span><span class="sxs-lookup"><span data-stu-id="48994-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="48994-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="48994-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="48994-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48994-266">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="48994-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="48994-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="48994-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48994-269">Nome do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="48994-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="48994-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="48994-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48994-272">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="48994-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="48994-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="48994-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48994-275">Nome do driver do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="48994-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="48994-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="48994-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48994-278">Nome do dispositivo de captura do receptor.</span><span class="sxs-lookup"><span data-stu-id="48994-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="48994-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="48994-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="48994-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48994-281">Nome do dispositivo de renderização do chamado.</span><span class="sxs-lookup"><span data-stu-id="48994-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="48994-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="48994-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="48994-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48994-284">Nome do driver do dispositivo de captura do receptor.</span><span class="sxs-lookup"><span data-stu-id="48994-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="48994-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="48994-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="48994-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48994-287">Nome do driver do dispositivo de renderização do receptor.</span><span class="sxs-lookup"><span data-stu-id="48994-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="48994-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="48994-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="48994-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="48994-290">Tipo de conexão de rede do chamador: 0 é por fio, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="48994-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="48994-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="48994-292">bits</span><span class="sxs-lookup"><span data-stu-id="48994-292">bit</span></span></p></td>
<td><p><span data-ttu-id="48994-p116">Indica se o chamador está conectado ou não através de uma rede virtual privada. 1 é para rede virtual privada (VPN), 0 é para não-VPN.</span><span class="sxs-lookup"><span data-stu-id="48994-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="48994-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="48994-296">decimal (18,)</span><span class="sxs-lookup"><span data-stu-id="48994-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="48994-297">Velocidade do link de rede do ponto de extremidade do chamador em bps.</span><span class="sxs-lookup"><span data-stu-id="48994-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="48994-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="48994-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="48994-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="48994-300">Tipo de conexão de rede do receptor: 0 é por fio, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="48994-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="48994-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="48994-302">bits</span><span class="sxs-lookup"><span data-stu-id="48994-302">bit</span></span></p></td>
<td><p><span data-ttu-id="48994-p117">Indica se o chamado está conectado ou não através de uma rede virtual privada. 1 é para rede virtual privada (VPN), 0 é para não-VPN.</span><span class="sxs-lookup"><span data-stu-id="48994-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="48994-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="48994-306">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="48994-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="48994-307">Velocidade do link de rede do ponto de extremidade do chamado (em bps).</span><span class="sxs-lookup"><span data-stu-id="48994-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="48994-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="48994-309">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="48994-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="48994-310">MOS da Conversa de Banda Estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="48994-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="48994-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="48994-312">int</span><span class="sxs-lookup"><span data-stu-id="48994-312">int</span></span></p></td>
<td><p><span data-ttu-id="48994-p118">Largura de banda real aplicada a um determinado stream lateral de envio de acordo com várias configurações de política (TURN, API, SDP, Servidor de políticas, e assim por diante). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda efetiva menor com base na estimativa de largura de banda. Esta é basicamente a largura de banda máxima que o stream de envio pode utilizar dos limites impostos pela estimativa de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="48994-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="48994-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="48994-317">int</span><span class="sxs-lookup"><span data-stu-id="48994-317">int</span></span></p></td>
<td><p><span data-ttu-id="48994-318">Média de tremulação de rede a partir da estatística do protocolo RTCP.</span><span class="sxs-lookup"><span data-stu-id="48994-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="48994-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="48994-320">int</span><span class="sxs-lookup"><span data-stu-id="48994-320">int</span></span></p></td>
<td><p><span data-ttu-id="48994-321">Instabilidade máxima da rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="48994-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-322">Aproxima</span><span class="sxs-lookup"><span data-stu-id="48994-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="48994-323">int</span><span class="sxs-lookup"><span data-stu-id="48994-323">int</span></span></p></td>
<td><p><span data-ttu-id="48994-324">Tempo de ida e volta de estatísticas RTCP.</span><span class="sxs-lookup"><span data-stu-id="48994-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="48994-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="48994-326">int</span><span class="sxs-lookup"><span data-stu-id="48994-326">int</span></span></p></td>
<td><p><span data-ttu-id="48994-327">Tempo máximo de viagem de ida e volta do stream de áudio.</span><span class="sxs-lookup"><span data-stu-id="48994-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="48994-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="48994-329">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="48994-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="48994-330">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="48994-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="48994-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="48994-332">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="48994-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="48994-333">Perda máxima de pacotes observada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="48994-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="48994-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="48994-335">int</span><span class="sxs-lookup"><span data-stu-id="48994-335">int</span></span></p></td>
<td><p><span data-ttu-id="48994-336">Contagem de pacotes do stream de vídeo (Protocolo de Transporte em Tempo Real, RTP).</span><span class="sxs-lookup"><span data-stu-id="48994-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-337">Mais largura de banda</span><span class="sxs-lookup"><span data-stu-id="48994-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="48994-338">int</span><span class="sxs-lookup"><span data-stu-id="48994-338">int</span></span></p></td>
<td><p><span data-ttu-id="48994-339">Estimativas de largura de banda do stream de áudio.</span><span class="sxs-lookup"><span data-stu-id="48994-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="48994-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="48994-341">int</span><span class="sxs-lookup"><span data-stu-id="48994-341">int</span></span></p></td>
<td><p><span data-ttu-id="48994-342">Codec de áudio usado para a chamada, referenciado da <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="48994-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="48994-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="48994-344">caractere (9)</span><span class="sxs-lookup"><span data-stu-id="48994-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="48994-p119">Resolução de vídeo obtida através da multiplicação dos pixel de altura e de largura. Relatada como uma sequência de caracteres.</span><span class="sxs-lookup"><span data-stu-id="48994-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="48994-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="48994-348">int</span><span class="sxs-lookup"><span data-stu-id="48994-348">int</span></span></p></td>
<td><p><span data-ttu-id="48994-349">Taxa de transmissão do stream de vídeo.</span><span class="sxs-lookup"><span data-stu-id="48994-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="48994-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="48994-351">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="48994-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="48994-352">Taxa de frames de vídeo recebidos.</span><span class="sxs-lookup"><span data-stu-id="48994-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="48994-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="48994-354">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="48994-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="48994-355">Taxa de frames de vídeo enviados.</span><span class="sxs-lookup"><span data-stu-id="48994-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="48994-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="48994-357">int</span><span class="sxs-lookup"><span data-stu-id="48994-357">int</span></span></p></td>
<td><p><span data-ttu-id="48994-358">Taxa de transmissão máxima de vídeo durante a sessão de vídeo.</span><span class="sxs-lookup"><span data-stu-id="48994-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="48994-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="48994-360">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="48994-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="48994-361">Taxa de perda dos pacotes de vídeo.</span><span class="sxs-lookup"><span data-stu-id="48994-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="48994-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="48994-363">decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="48994-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="48994-364">Percentual do total de frames de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="48994-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="48994-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="48994-366">bits</span><span class="sxs-lookup"><span data-stu-id="48994-366">bit</span></span></p></td>
<td><p><span data-ttu-id="48994-367">Não usado.</span><span class="sxs-lookup"><span data-stu-id="48994-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="48994-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="48994-369">int</span><span class="sxs-lookup"><span data-stu-id="48994-369">int</span></span></p></td>
<td><p><span data-ttu-id="48994-370">Valor médio da largura de banda alocada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="48994-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48994-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="48994-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="48994-372">decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="48994-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="48994-373">Percentual do total de frames de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="48994-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48994-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="48994-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="48994-375">bits</span><span class="sxs-lookup"><span data-stu-id="48994-375">bit</span></span></p></td>
<td><p><span data-ttu-id="48994-p120">Direção de stream das informações de identidade declarada. 1 significa que a direção do stream é do chamador para o chamado; 0 significa que a direção do stream é do chamado para o chamador.</span><span class="sxs-lookup"><span data-stu-id="48994-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

