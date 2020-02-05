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
ms.openlocfilehash: 6a153899fd484da861088a8e7672a69707e46a59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="91076-102">Modo de exibição de sessão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91076-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91076-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="91076-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="91076-104">A exibição de sessão armazena informações sobre as sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="91076-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="91076-105">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91076-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91076-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="91076-106">Column</span></span></th>
<th><span data-ttu-id="91076-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="91076-107">Data Type</span></span></th>
<th><span data-ttu-id="91076-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="91076-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91076-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="91076-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="91076-110">datetime</span><span class="sxs-lookup"><span data-stu-id="91076-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="91076-111">Referenciado da tabela de mídia.</span><span class="sxs-lookup"><span data-stu-id="91076-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91076-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="91076-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="91076-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="91076-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="91076-114">URL da conferência se for uma conferência ou caixa de diálogo se for uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="91076-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91076-115">Relation</span><span class="sxs-lookup"><span data-stu-id="91076-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="91076-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="91076-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="91076-117">ID de correlação da sessão.</span><span class="sxs-lookup"><span data-stu-id="91076-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91076-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="91076-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="91076-119">bit</span><span class="sxs-lookup"><span data-stu-id="91076-119">bit</span></span></p></td>
<td><p><span data-ttu-id="91076-120">Categoria da caixa de diálogo; 0 é o servidor do Lync para o segmento do servidor de mediação; 1 é o servidor de mediação para a perna do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="91076-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91076-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="91076-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="91076-122">bit</span><span class="sxs-lookup"><span data-stu-id="91076-122">bit</span></span></p></td>
<td><p><span data-ttu-id="91076-123">Indica se a chamada foi ignorada ou não.</span><span class="sxs-lookup"><span data-stu-id="91076-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91076-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="91076-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="91076-125">int</span><span class="sxs-lookup"><span data-stu-id="91076-125">int</span></span></p></td>
<td><p><span data-ttu-id="91076-126">Esse campo, se presente, indicará por que uma chamada não foi ignorada mesmo se as IDs de bypass forem atendidas.</span><span class="sxs-lookup"><span data-stu-id="91076-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="91076-127">Para o Lync Server, somente um valor é definido:</span><span class="sxs-lookup"><span data-stu-id="91076-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="91076-128">0x0001 – ID de bypass desconhecido para o adaptador de rede padrão</span><span class="sxs-lookup"><span data-stu-id="91076-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91076-129">StartTime </span><span class="sxs-lookup"><span data-stu-id="91076-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="91076-130">datetime</span><span class="sxs-lookup"><span data-stu-id="91076-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="91076-131">Hora de início da chamada.</span><span class="sxs-lookup"><span data-stu-id="91076-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91076-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="91076-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="91076-133">datetime</span><span class="sxs-lookup"><span data-stu-id="91076-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="91076-134">Hora de término da chamada.</span><span class="sxs-lookup"><span data-stu-id="91076-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91076-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="91076-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="91076-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91076-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91076-137">FQDN do pool de chamadas.</span><span class="sxs-lookup"><span data-stu-id="91076-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91076-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="91076-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="91076-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91076-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91076-140">FQDN do pool do chamador.</span><span class="sxs-lookup"><span data-stu-id="91076-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91076-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="91076-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="91076-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="91076-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="91076-143">URI de identidade declarado p do chamador.</span><span class="sxs-lookup"><span data-stu-id="91076-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91076-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="91076-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="91076-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="91076-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="91076-146">URI de identidade declarada do p do chamador.</span><span class="sxs-lookup"><span data-stu-id="91076-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91076-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="91076-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="91076-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91076-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91076-149">Nome do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="91076-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91076-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="91076-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="91076-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91076-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91076-152">Nome do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="91076-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91076-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="91076-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="91076-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91076-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91076-155">Cadeia de caracteres do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="91076-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91076-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="91076-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="91076-157">smallint</span><span class="sxs-lookup"><span data-stu-id="91076-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="91076-158">Tipo de agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="91076-158">Type of caller’s user agent.</span></span> <span data-ttu-id="91076-159">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="91076-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91076-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="91076-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="91076-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="91076-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="91076-162">Categoria do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="91076-162">Category of caller’s user agent.</span></span> <span data-ttu-id="91076-163">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="91076-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91076-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="91076-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="91076-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91076-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91076-166">Cadeia de caracteres do agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="91076-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91076-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="91076-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="91076-168">smallint</span><span class="sxs-lookup"><span data-stu-id="91076-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="91076-169">Tipo de agente do usuário para o chamador.</span><span class="sxs-lookup"><span data-stu-id="91076-169">Type of user agent for the callee.</span></span> <span data-ttu-id="91076-170">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="91076-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91076-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="91076-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="91076-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="91076-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="91076-173">Categoria do agente do usuário para o chamador.</span><span class="sxs-lookup"><span data-stu-id="91076-173">User agent category for the callee.</span></span> <span data-ttu-id="91076-174">Consulte a <a href="lync-server-2013-useragentdef-table-qoe.md">tabela UserAgentDef (QoE) no Lync Server 2013</a> para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="91076-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91076-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="91076-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="91076-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="91076-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="91076-177">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="91076-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91076-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="91076-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="91076-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="91076-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="91076-180">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="91076-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91076-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="91076-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="91076-182">int</span><span class="sxs-lookup"><span data-stu-id="91076-182">int</span></span></p></td>
<td><p><span data-ttu-id="91076-183">Prioridade da chamada.</span><span class="sxs-lookup"><span data-stu-id="91076-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

