---
title: 'Lync Server 2013: modo de exibição VideoStreamDetail'
description: 'Lync Server 2013: modo de exibição VideoStreamDetail.'
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
ms.openlocfilehash: a3f420c292627d15fd0d54f2eba01c565a49a72d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567967"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="e6adc-103">Exibição VideoStreamDetail no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6adc-103">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6adc-104">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e6adc-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e6adc-105">A Exibição VideoStreamDetail armazena informações sobre cada stream de vídeo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e6adc-105">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="e6adc-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6adc-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6adc-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="e6adc-107">Column</span></span></th>
<th><span data-ttu-id="e6adc-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e6adc-108">Data Type</span></span></th>
<th><span data-ttu-id="e6adc-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="e6adc-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-110">Sessiontime</span><span class="sxs-lookup"><span data-stu-id="e6adc-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="e6adc-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e6adc-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e6adc-112">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e6adc-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="e6adc-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="e6adc-114">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-114">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-115">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e6adc-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-116">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="e6adc-116">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="e6adc-117">tinyint</span><span class="sxs-lookup"><span data-stu-id="e6adc-117">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e6adc-118">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e6adc-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-119">Streamid</span><span class="sxs-lookup"><span data-stu-id="e6adc-119">StreamId</span></span></p></td>
<td><p><span data-ttu-id="e6adc-120">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-120">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-121">Identificação exclusiva em uma linha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e6adc-121">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="e6adc-122">StartTime</span></span></p></td>
<td><p><span data-ttu-id="e6adc-123">datetime</span><span class="sxs-lookup"><span data-stu-id="e6adc-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="e6adc-124">Hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="e6adc-124">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-125">EndTime</span><span class="sxs-lookup"><span data-stu-id="e6adc-125">EndTime</span></span></p></td>
<td><p><span data-ttu-id="e6adc-126">datetime</span><span class="sxs-lookup"><span data-stu-id="e6adc-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="e6adc-127">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="e6adc-127">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-128">CallPriority</span><span class="sxs-lookup"><span data-stu-id="e6adc-128">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="e6adc-129">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-129">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-130">Prioridade da chamada.</span><span class="sxs-lookup"><span data-stu-id="e6adc-130">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-131">CallerPool</span><span class="sxs-lookup"><span data-stu-id="e6adc-131">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="e6adc-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6adc-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-133">Pool FQDN do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-133">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-134">CalleePool</span><span class="sxs-lookup"><span data-stu-id="e6adc-134">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="e6adc-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6adc-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-136">FQDN do pool do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="e6adc-136">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-137">Chamador</span><span class="sxs-lookup"><span data-stu-id="e6adc-137">Caller</span></span></p></td>
<td><p><span data-ttu-id="e6adc-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e6adc-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-139">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-139">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-140">Receptor</span><span class="sxs-lookup"><span data-stu-id="e6adc-140">Callee</span></span></p></td>
<td><p><span data-ttu-id="e6adc-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e6adc-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-142">URI do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="e6adc-142">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-143">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="e6adc-143">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e6adc-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6adc-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-145">String do agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-145">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-146">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e6adc-146">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e6adc-147">smallint</span><span class="sxs-lookup"><span data-stu-id="e6adc-147">smallint</span></span></p></td>
<td><p><span data-ttu-id="e6adc-148">Tipo de agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-148">Type of caller’s user agent.</span></span> <span data-ttu-id="e6adc-149">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="e6adc-149">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-150">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e6adc-150">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e6adc-151">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e6adc-151">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-152">Categoria do agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-152">Category of caller’s user agent.</span></span> <span data-ttu-id="e6adc-153">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="e6adc-153">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-154">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="e6adc-154">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e6adc-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6adc-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-156">String de agente de usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="e6adc-156">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-157">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e6adc-157">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e6adc-158">smallint</span><span class="sxs-lookup"><span data-stu-id="e6adc-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="e6adc-159">Tipo de agente do usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="e6adc-159">Type of callee’s user agent.</span></span> <span data-ttu-id="e6adc-160">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="e6adc-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-161">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e6adc-161">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e6adc-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e6adc-162">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-163">Categoria do agente do usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="e6adc-163">Category of callee’s user agent.</span></span> <span data-ttu-id="e6adc-164">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter informações.</span><span class="sxs-lookup"><span data-stu-id="e6adc-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-165">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="e6adc-165">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e6adc-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6adc-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-167">Nome de ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-167">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-168">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="e6adc-168">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e6adc-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6adc-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-170">Nome do ponto de extremidade do receptor.</span><span class="sxs-lookup"><span data-stu-id="e6adc-170">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-171">CallerOS</span><span class="sxs-lookup"><span data-stu-id="e6adc-171">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="e6adc-172">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e6adc-172">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-173">Sistema operacional (OS) do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="e6adc-173">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-174">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="e6adc-174">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="e6adc-175">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e6adc-175">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-176">Sistema operacional (OS) do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="e6adc-176">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-177">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="e6adc-177">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="e6adc-178">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e6adc-178">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-179">Nome da CPU do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="e6adc-179">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-180">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="e6adc-180">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="e6adc-181">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e6adc-181">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-182">Nome da CPU do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="e6adc-182">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-183">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e6adc-183">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e6adc-184">smallint</span><span class="sxs-lookup"><span data-stu-id="e6adc-184">smallint</span></span></p></td>
<td><p><span data-ttu-id="e6adc-185">Número de núcleos da CPU do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-185">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-186">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e6adc-186">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e6adc-187">smallint</span><span class="sxs-lookup"><span data-stu-id="e6adc-187">smallint</span></span></p></td>
<td><p><span data-ttu-id="e6adc-188">Número de núcleos da CPU do ponto de extremidade do chamado.</span><span class="sxs-lookup"><span data-stu-id="e6adc-188">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-189">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e6adc-189">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e6adc-190">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-190">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-191">Velocidade do processador da CPU do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="e6adc-191">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-192">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e6adc-192">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e6adc-193">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-193">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-194">Velocidade do processador da CPU do ponto de extremidade do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="e6adc-194">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-195">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e6adc-195">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e6adc-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="e6adc-196">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e6adc-197">Indica se o sistema do autor da chamada está funcionando em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="e6adc-197">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e6adc-198">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e6adc-198">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-199">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e6adc-199">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e6adc-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="e6adc-200">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e6adc-201">Indica que o sistema do receptor da chamada está funcionando em um ambiente virtualizado.</span><span class="sxs-lookup"><span data-stu-id="e6adc-201">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e6adc-202">Consulte a <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e6adc-202">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-203">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="e6adc-203">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="e6adc-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="e6adc-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e6adc-205">Informações sobre o caminho de mídia, como direto ou transmitido.</span><span class="sxs-lookup"><span data-stu-id="e6adc-205">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="e6adc-206">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e6adc-206">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-207">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e6adc-207">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e6adc-208">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-208">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-p109">Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do autor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="e6adc-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-211">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e6adc-211">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e6adc-212">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-212">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-p110">Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do receptor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="e6adc-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-215">Transport</span><span class="sxs-lookup"><span data-stu-id="e6adc-215">Transport</span></span></p></td>
<td><p><span data-ttu-id="e6adc-216">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-216">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-217">Tipo de transporte: 0 é UDP, 1 é TCP.</span><span class="sxs-lookup"><span data-stu-id="e6adc-217">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-218">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="e6adc-218">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e6adc-219">var (50)</span><span class="sxs-lookup"><span data-stu-id="e6adc-219">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-220">Endereço IP do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="e6adc-220">IP address of the caller.</span></span> <span data-ttu-id="e6adc-221">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="e6adc-221">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-222">CallerPort</span><span class="sxs-lookup"><span data-stu-id="e6adc-222">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="e6adc-223">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-223">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-224">Porta usada pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-224">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-225">CallerInside</span><span class="sxs-lookup"><span data-stu-id="e6adc-225">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="e6adc-226">bits</span><span class="sxs-lookup"><span data-stu-id="e6adc-226">bit</span></span></p></td>
<td><p><span data-ttu-id="e6adc-p112">Indica se o chamador está dentro da rede da organização. 1 significa que o chamador está dentro da rede da empresa, 0 significa que o chamador está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="e6adc-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-229">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="e6adc-229">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e6adc-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="e6adc-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-231">Endereço IP do receptor.</span><span class="sxs-lookup"><span data-stu-id="e6adc-231">IP address of the callee.</span></span> <span data-ttu-id="e6adc-232">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="e6adc-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-233">CalleePort</span><span class="sxs-lookup"><span data-stu-id="e6adc-233">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="e6adc-234">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-234">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-235">Porta usada pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="e6adc-235">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-236">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="e6adc-236">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="e6adc-237">bits</span><span class="sxs-lookup"><span data-stu-id="e6adc-237">bit</span></span></p></td>
<td><p><span data-ttu-id="e6adc-238">Indica se o chamado está dentro da rede da organização. 1 significa que o chamado está dentro da rede da empresa, 0 significa que o chamado está fora da rede.</span><span class="sxs-lookup"><span data-stu-id="e6adc-238">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-239">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="e6adc-239">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="e6adc-240">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e6adc-240">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-241">Nome do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-241">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-242">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="e6adc-242">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="e6adc-243">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e6adc-243">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-244">Nome do país/região do site do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-244">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-245">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="e6adc-245">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="e6adc-246">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e6adc-246">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-247">Nome do site do receptor.</span><span class="sxs-lookup"><span data-stu-id="e6adc-247">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-248">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="e6adc-248">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="e6adc-249">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="e6adc-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-250">Nome o país/região do site do receptor.</span><span class="sxs-lookup"><span data-stu-id="e6adc-250">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-251">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e6adc-251">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e6adc-252">var (50)</span><span class="sxs-lookup"><span data-stu-id="e6adc-252">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-253">Endereço IP do serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-253">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="e6adc-254">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e6adc-254">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-255">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="e6adc-255">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e6adc-256">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-256">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-257">Porta no serviço de borda A/V usado pelo chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-257">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-258">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e6adc-258">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e6adc-259">var (50)</span><span class="sxs-lookup"><span data-stu-id="e6adc-259">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-260">Chave de endereço IP do serviço de borda A/V usado pelo receptor.</span><span class="sxs-lookup"><span data-stu-id="e6adc-260">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="e6adc-261">Consulte a <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e6adc-261">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-262">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="e6adc-262">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e6adc-263">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-263">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-264">Porta no serviço de borda A/V usada pelo chamado.</span><span class="sxs-lookup"><span data-stu-id="e6adc-264">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-265">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e6adc-265">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e6adc-266">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6adc-266">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-267">Nome do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-267">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-268">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="e6adc-268">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e6adc-269">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6adc-269">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-270">Nome do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-270">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-271">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e6adc-271">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e6adc-272">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6adc-272">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-273">Nome do driver do dispositivo de captura do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-273">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-274">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="e6adc-274">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e6adc-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6adc-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-276">Nome do driver do dispositivo de renderização do chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-276">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-277">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e6adc-277">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e6adc-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6adc-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-279">Nome do dispositivo de captura do receptor.</span><span class="sxs-lookup"><span data-stu-id="e6adc-279">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-280">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="e6adc-280">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e6adc-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6adc-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-282">Nome do dispositivo de renderização do chamado.</span><span class="sxs-lookup"><span data-stu-id="e6adc-282">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-283">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e6adc-283">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e6adc-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6adc-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-285">Nome do driver do dispositivo de captura do receptor.</span><span class="sxs-lookup"><span data-stu-id="e6adc-285">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-286">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="e6adc-286">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e6adc-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6adc-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-288">Nome do driver do dispositivo de renderização do receptor.</span><span class="sxs-lookup"><span data-stu-id="e6adc-288">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-289">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e6adc-289">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e6adc-290">tinyint</span><span class="sxs-lookup"><span data-stu-id="e6adc-290">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e6adc-291">Tipo de conexão de rede do chamador: 0 é por fio, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="e6adc-291">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-292">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="e6adc-292">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="e6adc-293">bits</span><span class="sxs-lookup"><span data-stu-id="e6adc-293">bit</span></span></p></td>
<td><p><span data-ttu-id="e6adc-p116">Indica se o chamador está conectado ou não através de uma rede virtual privada. 1 é para rede virtual privada (VPN), 0 é para não-VPN.</span><span class="sxs-lookup"><span data-stu-id="e6adc-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-296">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e6adc-296">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e6adc-297">decimal (18,)</span><span class="sxs-lookup"><span data-stu-id="e6adc-297">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-298">Velocidade do link de rede do ponto de extremidade do chamador em bps.</span><span class="sxs-lookup"><span data-stu-id="e6adc-298">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-299">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e6adc-299">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e6adc-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="e6adc-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e6adc-301">Tipo de conexão de rede do receptor: 0 é por fio, 1 é sem fio.</span><span class="sxs-lookup"><span data-stu-id="e6adc-301">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-302">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="e6adc-302">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="e6adc-303">bits</span><span class="sxs-lookup"><span data-stu-id="e6adc-303">bit</span></span></p></td>
<td><p><span data-ttu-id="e6adc-p117">Indica se o chamado está conectado ou não através de uma rede virtual privada. 1 é para rede virtual privada (VPN), 0 é para não-VPN.</span><span class="sxs-lookup"><span data-stu-id="e6adc-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-306">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e6adc-306">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e6adc-307">decimal (18, 0)</span><span class="sxs-lookup"><span data-stu-id="e6adc-307">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-308">Velocidade do link de rede do ponto de extremidade do chamado (em bps).</span><span class="sxs-lookup"><span data-stu-id="e6adc-308">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-309">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="e6adc-309">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="e6adc-310">decimal (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e6adc-310">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-311">MOS da Conversa de Banda Estreita das sessões de áudio (com base nos dois fluxos de áudio).</span><span class="sxs-lookup"><span data-stu-id="e6adc-311">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-312">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="e6adc-312">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="e6adc-313">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-313">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-p118">Largura de banda real aplicada a um determinado stream lateral de envio de acordo com várias configurações de política (TURN, API, SDP, Servidor de políticas, e assim por diante). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda efetiva menor com base na estimativa de largura de banda. Esta é basicamente a largura de banda máxima que o stream de envio pode utilizar dos limites impostos pela estimativa de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="e6adc-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-317">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="e6adc-317">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="e6adc-318">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-318">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-319">Média de tremulação de rede a partir da estatística do protocolo RTCP.</span><span class="sxs-lookup"><span data-stu-id="e6adc-319">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-320">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="e6adc-320">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="e6adc-321">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-321">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-322">Instabilidade máxima da rede durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="e6adc-322">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-323">Aproxima</span><span class="sxs-lookup"><span data-stu-id="e6adc-323">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="e6adc-324">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-324">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-325">Tempo de ida e volta de estatísticas RTCP.</span><span class="sxs-lookup"><span data-stu-id="e6adc-325">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-326">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="e6adc-326">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="e6adc-327">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-327">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-328">Tempo máximo de viagem de ida e volta do stream de áudio.</span><span class="sxs-lookup"><span data-stu-id="e6adc-328">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-329">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="e6adc-329">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="e6adc-330">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="e6adc-330">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-331">Taxa média de perda de pacotes durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="e6adc-331">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-332">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="e6adc-332">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="e6adc-333">decimal (5, 4)</span><span class="sxs-lookup"><span data-stu-id="e6adc-333">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-334">Perda máxima de pacotes observada durante a chamada.</span><span class="sxs-lookup"><span data-stu-id="e6adc-334">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-335">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="e6adc-335">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="e6adc-336">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-336">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-337">Contagem de pacotes do stream de vídeo (Protocolo de Transporte em Tempo Real, RTP).</span><span class="sxs-lookup"><span data-stu-id="e6adc-337">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-338">Mais largura de banda</span><span class="sxs-lookup"><span data-stu-id="e6adc-338">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="e6adc-339">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-339">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-340">Estimativas de largura de banda do stream de áudio.</span><span class="sxs-lookup"><span data-stu-id="e6adc-340">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-341">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="e6adc-341">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="e6adc-342">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-342">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-343">Codec de áudio usado para a chamada, referenciado da <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="e6adc-343">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-344">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="e6adc-344">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="e6adc-345">caractere (9)</span><span class="sxs-lookup"><span data-stu-id="e6adc-345">char(9)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-p119">Resolução de vídeo obtida através da multiplicação dos pixel de altura e de largura. Relatada como uma sequência de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e6adc-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-348">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="e6adc-348">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="e6adc-349">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-349">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-350">Taxa de transmissão do stream de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e6adc-350">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-351">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="e6adc-351">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="e6adc-352">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e6adc-352">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-353">Taxa de frames de vídeo recebidos.</span><span class="sxs-lookup"><span data-stu-id="e6adc-353">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-354">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="e6adc-354">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="e6adc-355">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e6adc-355">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-356">Taxa de frames de vídeo enviados.</span><span class="sxs-lookup"><span data-stu-id="e6adc-356">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-357">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="e6adc-357">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="e6adc-358">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-358">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-359">Taxa de transmissão máxima de vídeo durante a sessão de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e6adc-359">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-360">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="e6adc-360">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="e6adc-361">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e6adc-361">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-362">Taxa de perda dos pacotes de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e6adc-362">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-363">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="e6adc-363">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="e6adc-364">decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="e6adc-364">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-365">Percentual do total de frames de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="e6adc-365">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-366">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="e6adc-366">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="e6adc-367">bits</span><span class="sxs-lookup"><span data-stu-id="e6adc-367">bit</span></span></p></td>
<td><p><span data-ttu-id="e6adc-368">Não usado.</span><span class="sxs-lookup"><span data-stu-id="e6adc-368">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-369">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="e6adc-369">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="e6adc-370">int</span><span class="sxs-lookup"><span data-stu-id="e6adc-370">int</span></span></p></td>
<td><p><span data-ttu-id="e6adc-371">Valor médio da largura de banda alocada para vídeo.</span><span class="sxs-lookup"><span data-stu-id="e6adc-371">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6adc-372">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="e6adc-372">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="e6adc-373">decimal (9.4)</span><span class="sxs-lookup"><span data-stu-id="e6adc-373">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="e6adc-374">Percentual do total de frames de vídeo perdidos.</span><span class="sxs-lookup"><span data-stu-id="e6adc-374">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6adc-375">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="e6adc-375">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="e6adc-376">bits</span><span class="sxs-lookup"><span data-stu-id="e6adc-376">bit</span></span></p></td>
<td><p><span data-ttu-id="e6adc-p120">Direção de stream das informações de identidade declarada. 1 significa que a direção do stream é do chamador para o chamado; 0 significa que a direção do stream é do chamado para o chamador.</span><span class="sxs-lookup"><span data-stu-id="e6adc-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

