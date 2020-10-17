---
title: 'Lync Server 2013: modo de exibição de sessão'
description: 'Lync Server 2013: modo de exibição de sessão.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff4bc4abbd55e073006693d28f092f077698ef75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545007"
---
# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="d3a58-103">Exibição de sessão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3a58-103">Session view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3a58-104">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d3a58-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d3a58-105">O Modo de exibição do servidor armazena informações sobre sessões que foram registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d3a58-105">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="d3a58-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3a58-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3a58-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="d3a58-107">Column</span></span></th>
<th><span data-ttu-id="d3a58-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="d3a58-108">Data Type</span></span></th>
<th><span data-ttu-id="d3a58-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d3a58-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3a58-110">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="d3a58-110">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="d3a58-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d3a58-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d3a58-112">Referenciado da tabela MediaLine.</span><span class="sxs-lookup"><span data-stu-id="d3a58-112">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3a58-113">Conferenceui</span><span class="sxs-lookup"><span data-stu-id="d3a58-113">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="d3a58-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d3a58-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d3a58-115">URI de Conferência é uma conferência, ou DialogID se é uma sessão peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="d3a58-115">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3a58-116">Correlation</span><span class="sxs-lookup"><span data-stu-id="d3a58-116">Correlation</span></span></p></td>
<td><p><span data-ttu-id="d3a58-117">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="d3a58-117">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="d3a58-118">ID de correlação da sessão.</span><span class="sxs-lookup"><span data-stu-id="d3a58-118">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3a58-119">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="d3a58-119">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="d3a58-120">bits</span><span class="sxs-lookup"><span data-stu-id="d3a58-120">bit</span></span></p></td>
<td><p><span data-ttu-id="d3a58-121">Categoria da caixa de diálogo; 0 é o servidor do Lync Server para o trecho do servidor de mediação; 1 é o servidor de mediação para o segmento de gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="d3a58-121">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3a58-122">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="d3a58-122">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="d3a58-123">bits</span><span class="sxs-lookup"><span data-stu-id="d3a58-123">bit</span></span></p></td>
<td><p><span data-ttu-id="d3a58-124">Indica se uma ligação foi ou não ignorada.</span><span class="sxs-lookup"><span data-stu-id="d3a58-124">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3a58-125">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="d3a58-125">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="d3a58-126">int</span><span class="sxs-lookup"><span data-stu-id="d3a58-126">int</span></span></p></td>
<td><p><span data-ttu-id="d3a58-127">Caso presente, este campo indica o motivo de uma chamada não ter sido ignorada, mesmo se as IDs de bypass correspondessem.</span><span class="sxs-lookup"><span data-stu-id="d3a58-127">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="d3a58-128">Para o Lync Server, apenas um valor é definido:</span><span class="sxs-lookup"><span data-stu-id="d3a58-128">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="d3a58-129">0x0001 – ID de bypass desconhecido para o adaptador de rede padrão</span><span class="sxs-lookup"><span data-stu-id="d3a58-129">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3a58-130">StartTime</span><span class="sxs-lookup"><span data-stu-id="d3a58-130">StartTime</span></span></p></td>
<td><p><span data-ttu-id="d3a58-131">datetime</span><span class="sxs-lookup"><span data-stu-id="d3a58-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="d3a58-132">Hora do início da chamada.</span><span class="sxs-lookup"><span data-stu-id="d3a58-132">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3a58-133">EndTime</span><span class="sxs-lookup"><span data-stu-id="d3a58-133">EndTime</span></span></p></td>
<td><p><span data-ttu-id="d3a58-134">datetime</span><span class="sxs-lookup"><span data-stu-id="d3a58-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="d3a58-135">Hora da finalização da chamada.</span><span class="sxs-lookup"><span data-stu-id="d3a58-135">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3a58-136">CallerPool</span><span class="sxs-lookup"><span data-stu-id="d3a58-136">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="d3a58-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d3a58-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d3a58-138">Pool FQDN do chamador.</span><span class="sxs-lookup"><span data-stu-id="d3a58-138">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3a58-139">CalleePool</span><span class="sxs-lookup"><span data-stu-id="d3a58-139">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="d3a58-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d3a58-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d3a58-141">Pool FQDN do receptor.</span><span class="sxs-lookup"><span data-stu-id="d3a58-141">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3a58-142">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="d3a58-142">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="d3a58-143">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d3a58-143">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d3a58-144">Identidade URI declarada p do chamador.</span><span class="sxs-lookup"><span data-stu-id="d3a58-144">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3a58-145">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="d3a58-145">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="d3a58-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d3a58-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d3a58-147">Identidade URI declarada p do receptor.</span><span class="sxs-lookup"><span data-stu-id="d3a58-147">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3a58-148">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="d3a58-148">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="d3a58-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d3a58-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d3a58-150">Nome de ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="d3a58-150">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3a58-151">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="d3a58-151">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="d3a58-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d3a58-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d3a58-153">Nome de ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="d3a58-153">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3a58-154">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="d3a58-154">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="d3a58-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d3a58-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d3a58-156">String do agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="d3a58-156">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3a58-157">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="d3a58-157">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="d3a58-158">smallint</span><span class="sxs-lookup"><span data-stu-id="d3a58-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="d3a58-159">Tipo de agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="d3a58-159">Type of caller’s user agent.</span></span> <span data-ttu-id="d3a58-160">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="d3a58-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3a58-161">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="d3a58-161">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="d3a58-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d3a58-162">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="d3a58-163">Categoria do agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="d3a58-163">Category of caller’s user agent.</span></span> <span data-ttu-id="d3a58-164">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="d3a58-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3a58-165">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="d3a58-165">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="d3a58-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d3a58-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d3a58-167">String de agente de usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="d3a58-167">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3a58-168">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="d3a58-168">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="d3a58-169">smallint</span><span class="sxs-lookup"><span data-stu-id="d3a58-169">smallint</span></span></p></td>
<td><p><span data-ttu-id="d3a58-170">Tipo de agente de usuário para o receptor.</span><span class="sxs-lookup"><span data-stu-id="d3a58-170">Type of user agent for the callee.</span></span> <span data-ttu-id="d3a58-171">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="d3a58-171">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3a58-172">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="d3a58-172">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="d3a58-173">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d3a58-173">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="d3a58-174">Categoria do agente de usuário para o receptor.</span><span class="sxs-lookup"><span data-stu-id="d3a58-174">User agent category for the callee.</span></span> <span data-ttu-id="d3a58-175">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="d3a58-175">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3a58-176">CallerURI</span><span class="sxs-lookup"><span data-stu-id="d3a58-176">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="d3a58-177">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d3a58-177">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d3a58-178">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="d3a58-178">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3a58-179">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="d3a58-179">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="d3a58-180">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d3a58-180">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d3a58-181">URI do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="d3a58-181">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3a58-182">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="d3a58-182">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="d3a58-183">int</span><span class="sxs-lookup"><span data-stu-id="d3a58-183">int</span></span></p></td>
<td><p><span data-ttu-id="d3a58-184">Prioridade da chamada.</span><span class="sxs-lookup"><span data-stu-id="d3a58-184">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

