---
title: 'Lync Server 2013: modo de exibição de sessão'
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
ms.openlocfilehash: 80b9c7c9b54deb28b70c8ee2386359bec37d5a69
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="fcb8c-102">Exibição de sessão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fcb8c-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcb8c-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="fcb8c-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="fcb8c-104">O Modo de exibição do servidor armazena informações sobre sessões que foram registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="fcb8c-105">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcb8c-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="fcb8c-106">Column</span></span></th>
<th><span data-ttu-id="fcb8c-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="fcb8c-107">Data Type</span></span></th>
<th><span data-ttu-id="fcb8c-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="fcb8c-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcb8c-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="fcb8c-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-110">datetime</span><span class="sxs-lookup"><span data-stu-id="fcb8c-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-111">Referenciado da tabela MediaLine.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb8c-112">Conferenceui</span><span class="sxs-lookup"><span data-stu-id="fcb8c-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fcb8c-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-114">URI de Conferência é uma conferência, ou DialogID se é uma sessão peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb8c-115">Correlation</span><span class="sxs-lookup"><span data-stu-id="fcb8c-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="fcb8c-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-117">ID de correlação da sessão.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb8c-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="fcb8c-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-119">bits</span><span class="sxs-lookup"><span data-stu-id="fcb8c-119">bit</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-120">Categoria da caixa de diálogo; 0 é o servidor do Lync Server para o trecho do servidor de mediação; 1 é o servidor de mediação para o segmento de gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb8c-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="fcb8c-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-122">bits</span><span class="sxs-lookup"><span data-stu-id="fcb8c-122">bit</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-123">Indica se uma ligação foi ou não ignorada.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb8c-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="fcb8c-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-125">int</span><span class="sxs-lookup"><span data-stu-id="fcb8c-125">int</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-126">Caso presente, este campo indica o motivo de uma chamada não ter sido ignorada, mesmo se as IDs de bypass correspondessem.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="fcb8c-127">Para o Lync Server, apenas um valor é definido:</span><span class="sxs-lookup"><span data-stu-id="fcb8c-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="fcb8c-128">0x0001 – ID de bypass desconhecido para o adaptador de rede padrão</span><span class="sxs-lookup"><span data-stu-id="fcb8c-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb8c-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="fcb8c-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-130">datetime</span><span class="sxs-lookup"><span data-stu-id="fcb8c-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-131">Hora do início da chamada.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb8c-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="fcb8c-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-133">datetime</span><span class="sxs-lookup"><span data-stu-id="fcb8c-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-134">Hora da finalização da chamada.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb8c-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="fcb8c-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fcb8c-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-137">Pool FQDN do chamador.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb8c-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="fcb8c-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fcb8c-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-140">Pool FQDN do receptor.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb8c-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="fcb8c-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fcb8c-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-143">Identidade URI declarada p do chamador.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb8c-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="fcb8c-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fcb8c-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-146">Identidade URI declarada p do receptor.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb8c-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="fcb8c-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fcb8c-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-149">Nome do ponto de extremidade do autor da chamada.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb8c-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="fcb8c-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fcb8c-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-152">Nome de ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb8c-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="fcb8c-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fcb8c-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-155">String do agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb8c-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="fcb8c-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-157">smallint</span><span class="sxs-lookup"><span data-stu-id="fcb8c-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-158">Tipo de agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-158">Type of caller’s user agent.</span></span> <span data-ttu-id="fcb8c-159">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb8c-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="fcb8c-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="fcb8c-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-162">Categoria do agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-162">Category of caller’s user agent.</span></span> <span data-ttu-id="fcb8c-163">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb8c-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="fcb8c-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fcb8c-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-166">String de agente de usuário do receptor.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb8c-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="fcb8c-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-168">smallint</span><span class="sxs-lookup"><span data-stu-id="fcb8c-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-169">Tipo de agente de usuário para o receptor.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-169">Type of user agent for the callee.</span></span> <span data-ttu-id="fcb8c-170">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb8c-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="fcb8c-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="fcb8c-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-173">Categoria do agente de usuário para o receptor.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-173">User agent category for the callee.</span></span> <span data-ttu-id="fcb8c-174">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb8c-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="fcb8c-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fcb8c-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-177">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb8c-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="fcb8c-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fcb8c-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-180">URI do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb8c-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="fcb8c-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-182">int</span><span class="sxs-lookup"><span data-stu-id="fcb8c-182">int</span></span></p></td>
<td><p><span data-ttu-id="fcb8c-183">Prioridade da chamada.</span><span class="sxs-lookup"><span data-stu-id="fcb8c-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

