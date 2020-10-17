---
title: 'Lync Server 2013: tabela SessionDetails'
description: 'Lync Server 2013: tabela SessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd927f784fb0f2a835c896824105fe8bb112c7a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569927"
---
# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="c6829-103">Tabela SessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6829-103">SessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6829-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c6829-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c6829-105">Cada registro representa uma sessão ponto a ponto, que poderia ser uma chamada telefônica VoIP-VoIP, uma sessão de IM de duas partes ou outro tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-105">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="c6829-106">Você pode executar uma junção de tabela com a [tabela de mídia no Lync Server 2013](lync-server-2013-media-table.md) para encontrar os detalhes de cada mídia envolvida nesta sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-106">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="c6829-107">Observe que os campos IsUser1IntegratedWithDeskPhone e IsUser2IntegratedWithDeskPhone foram descartados da tabela SessionDetails usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6829-107">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6829-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="c6829-108">Column</span></span></th>
<th><span data-ttu-id="c6829-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c6829-109">Data Type</span></span></th>
<th><span data-ttu-id="c6829-110">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="c6829-110">Key/Index</span></span></th>
<th><span data-ttu-id="c6829-111">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c6829-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6829-112"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-112"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-113">datetime</span><span class="sxs-lookup"><span data-stu-id="c6829-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="c6829-114">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="c6829-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-115">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-115">Time of session request.</span></span> <span data-ttu-id="c6829-116">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-116">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c6829-117">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-117">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-118"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-118"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-119">int</span><span class="sxs-lookup"><span data-stu-id="c6829-119">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-120">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="c6829-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-121">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-121">ID number to identify the session.</span></span> <span data-ttu-id="c6829-122">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma sessão. \* consulte a <a href="lync-server-2013-dialogs-table.md">tabela Dialogs no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-122">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-123"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-123"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-124">identificador</span><span class="sxs-lookup"><span data-stu-id="c6829-124">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-125">Um GUID para correlacionar várias sessões.</span><span class="sxs-lookup"><span data-stu-id="c6829-125">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-126"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-126"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-127">datetime</span><span class="sxs-lookup"><span data-stu-id="c6829-127">datetime</span></span></p></td>
<td><p><span data-ttu-id="c6829-128">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-129">O número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual.</span><span class="sxs-lookup"><span data-stu-id="c6829-129">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="c6829-130">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-130">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-131"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-131"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-132">int</span><span class="sxs-lookup"><span data-stu-id="c6829-132">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-133">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-134">O número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-134">ID number to identify the session.</span></span> <span data-ttu-id="c6829-135">Usado em conjunto com <strong>ReplacesDialogIdTime </strong> para identificar exclusivamente uma sessão que é substituída por esta sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-135">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="c6829-136">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-136">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-137"><strong>Usuário1id</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-137"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-138">int</span><span class="sxs-lookup"><span data-stu-id="c6829-138">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-139">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-140">A ID de um usuário na sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-140">ID of one user in the session.</span></span> <span data-ttu-id="c6829-141">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-141">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-142"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-142"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-143">int</span><span class="sxs-lookup"><span data-stu-id="c6829-143">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-144">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-145">A ID de outro usuário na sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-145">ID of the other user in the session.</span></span> <span data-ttu-id="c6829-146">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-146">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-147"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-147"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-148">Identificador</span><span class="sxs-lookup"><span data-stu-id="c6829-148">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-149">GUID que identifica o ponto de extremidade usado pelo primeiro usuário na sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-149">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="c6829-150">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6829-150">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-151"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-151"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-152">Identificador</span><span class="sxs-lookup"><span data-stu-id="c6829-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-153">GUID que identifica o ponto de extremidade usado pelo segundo usuário na sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-153">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="c6829-154">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6829-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-155"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-155"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-156">int</span><span class="sxs-lookup"><span data-stu-id="c6829-156">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-157">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-157">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-158">A solicitação original Para o URI do usuário no SIP.</span><span class="sxs-lookup"><span data-stu-id="c6829-158">The original To user URI in the SIP request.</span></span> <span data-ttu-id="c6829-159">consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-159">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-160"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-160"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-161">int</span><span class="sxs-lookup"><span data-stu-id="c6829-161">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-162">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-163">A ID do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-163">ID of the user who started the session.</span></span> <span data-ttu-id="c6829-164">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-164">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-165"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-165"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-166">int</span><span class="sxs-lookup"><span data-stu-id="c6829-166">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-167">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-167">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-168">Indica a ID do usuário que está em nome do chamador.</span><span class="sxs-lookup"><span data-stu-id="c6829-168">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="c6829-169">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-169">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-170"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-170"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-171">int</span><span class="sxs-lookup"><span data-stu-id="c6829-171">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-172">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-172">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-173">A ID do usuário a quem se refere a chamada.</span><span class="sxs-lookup"><span data-stu-id="c6829-173">ID of the user by who the call is referred.</span></span> <span data-ttu-id="c6829-174">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-174">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-175"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-175"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-176">int</span><span class="sxs-lookup"><span data-stu-id="c6829-176">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-177">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-177">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-178">A ID do servidor Front-End usado para esta sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-178">ID of the front-end server used for this session.</span></span> <span data-ttu-id="c6829-179">Consulte a <a href="lync-server-2013-servers-table.md">tabela de servidores no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-179">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-180"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-180"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-181">int</span><span class="sxs-lookup"><span data-stu-id="c6829-181">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-182">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-182">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-183">A ID do pool no qual a sessão foi capturada.</span><span class="sxs-lookup"><span data-stu-id="c6829-183">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="c6829-184">Consulte a <a href="lync-server-2013-pools-table.md">tabela pools no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-184">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-185"><strong>ContentTypeid</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-185"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-186">int</span><span class="sxs-lookup"><span data-stu-id="c6829-186">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-187">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-188">Tipo de conteúdo usado na sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-188">Content type used in the session.</span></span> <span data-ttu-id="c6829-189">Consulte a <a href="lync-server-2013-contenttypes-table.md">tabela ContentTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-189">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-190"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-190"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-191">int</span><span class="sxs-lookup"><span data-stu-id="c6829-191">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-192">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-193">A versão do cliente usada pelo Usuário1.</span><span class="sxs-lookup"><span data-stu-id="c6829-193">Client version used by User1.</span></span> <span data-ttu-id="c6829-194">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-194">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-195"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-195"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-196">int</span><span class="sxs-lookup"><span data-stu-id="c6829-196">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-197">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-198">A versão do cliente usada pelo Usuário2.</span><span class="sxs-lookup"><span data-stu-id="c6829-198">Client version used by User2.</span></span> <span data-ttu-id="c6829-199">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-199">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-200"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-200"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-201">int</span><span class="sxs-lookup"><span data-stu-id="c6829-201">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-202">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-203">O Servidor de Borda usado pelo Usuário1.</span><span class="sxs-lookup"><span data-stu-id="c6829-203">Edge Server used by User1.</span></span> <span data-ttu-id="c6829-204">Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-204">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-205"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-205"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-206">int</span><span class="sxs-lookup"><span data-stu-id="c6829-206">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-207">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-208">O Servidor de Borda usado pelo Usuário2.</span><span class="sxs-lookup"><span data-stu-id="c6829-208">Edge Server used by User2.</span></span> <span data-ttu-id="c6829-209">Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-209">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-210"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-210"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-211">bits</span><span class="sxs-lookup"><span data-stu-id="c6829-211">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-212">Se o Usuário1 está conectado internamente ou não.</span><span class="sxs-lookup"><span data-stu-id="c6829-212">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-213"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-213"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-214">bits</span><span class="sxs-lookup"><span data-stu-id="c6829-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-215">Se o Usuário2 está conectado internamente ou não.</span><span class="sxs-lookup"><span data-stu-id="c6829-215">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-216"><strong>Invitetime</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-216"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-217">datetime</span><span class="sxs-lookup"><span data-stu-id="c6829-217">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-218">A hora da primeira solicitação INVITE.</span><span class="sxs-lookup"><span data-stu-id="c6829-218">The time of the first INVITE request.</span></span> <span data-ttu-id="c6829-219">Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-219">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c6829-220">Caso não exista uma mensagem INVITE então o campo é preenchido com a data e horário da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE, ou INFO).</span><span class="sxs-lookup"><span data-stu-id="c6829-220">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="c6829-221">Este campo é normalmente preenchido pelos dados gerados a partir da mensagem INVITE inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-221">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c6829-222">Se não houver mensagem INVITE, então o campo será preenchido com a data e hora da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="c6829-222">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-223"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-223"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-224">datetime</span><span class="sxs-lookup"><span data-stu-id="c6829-224">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-225">O tempo de resposta da primeira mensagem INVITE.</span><span class="sxs-lookup"><span data-stu-id="c6829-225">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="c6829-226">Este campo é tipicamente preenchido pelos dados gerados pela mensagem INVITE inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-226">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c6829-227">Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="c6829-227">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-228"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-228"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-229">int</span><span class="sxs-lookup"><span data-stu-id="c6829-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-p121">Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="c6829-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-233"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-233"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-234">int</span><span class="sxs-lookup"><span data-stu-id="c6829-234">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-235">ID de diagnóstico capturada do cabeçalho SIP.</span><span class="sxs-lookup"><span data-stu-id="c6829-235">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-236"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-236"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-237">int</span><span class="sxs-lookup"><span data-stu-id="c6829-237">int</span></span></p></td>
<td><p><span data-ttu-id="c6829-238">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c6829-238">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6829-239">Prioridade de chamada.</span><span class="sxs-lookup"><span data-stu-id="c6829-239">Call priority.</span></span> <span data-ttu-id="c6829-240">Consulte a <a href="lync-server-2013-callpriorities-table.md">tabela CallPriorities no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c6829-240">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-241"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-241"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-242">int</span><span class="sxs-lookup"><span data-stu-id="c6829-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-243">O número de mensagens enviadas pelo Usuário1 durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-243">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-244"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-244"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-245">int</span><span class="sxs-lookup"><span data-stu-id="c6829-245">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-246">O número de mensagens enviadas pelo Usuário2 durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-246">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-247"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-247"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-248">datetime</span><span class="sxs-lookup"><span data-stu-id="c6829-248">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-249">Hora ao final da sessão.</span><span class="sxs-lookup"><span data-stu-id="c6829-249">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-250"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-250"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-251">int</span><span class="sxs-lookup"><span data-stu-id="c6829-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-p123">Um conjunto de bits que indica o tipo de mídia esta sessão. As definições dos tipos estão listadas:</span><span class="sxs-lookup"><span data-stu-id="c6829-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6829-254">Mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="c6829-254">IM</span></span></p></td>
<td><p><span data-ttu-id="c6829-255">1</span><span class="sxs-lookup"><span data-stu-id="c6829-255">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-256">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="c6829-256">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="c6829-257">duas</span><span class="sxs-lookup"><span data-stu-id="c6829-257">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-258">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="c6829-258">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="c6829-259">4 </span><span class="sxs-lookup"><span data-stu-id="c6829-259">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-260">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="c6829-260">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="c6829-261">8 </span><span class="sxs-lookup"><span data-stu-id="c6829-261">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-262">AÚDIO</span><span class="sxs-lookup"><span data-stu-id="c6829-262">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="c6829-263">16 </span><span class="sxs-lookup"><span data-stu-id="c6829-263">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-264">VÍDEOS</span><span class="sxs-lookup"><span data-stu-id="c6829-264">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="c6829-265">32</span><span class="sxs-lookup"><span data-stu-id="c6829-265">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-266">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="c6829-266">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="c6829-267">64</span><span class="sxs-lookup"><span data-stu-id="c6829-267">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-268"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-268"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-269">smallint</span><span class="sxs-lookup"><span data-stu-id="c6829-269">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-p124">Um conjunto de bits que indica os atributos do Usuário1. As seguintes definições de atributo são listadas:</span><span class="sxs-lookup"><span data-stu-id="c6829-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6829-272">0x01 - Integrado com telefone da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="c6829-272">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-273"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-273"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-274">smallint</span><span class="sxs-lookup"><span data-stu-id="c6829-274">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-p125">Um conjunto de bits que indica os atributos do Usuário2. As seguintes definições de atributo são listadas:</span><span class="sxs-lookup"><span data-stu-id="c6829-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6829-277">0x01 - Integrado com telefone da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="c6829-277">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6829-278"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-278"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-279">smallint</span><span class="sxs-lookup"><span data-stu-id="c6829-279">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-p126">Um conjunto de bits que indica os atributos da chamada. As seguintes definições de atributo são listadas:</span><span class="sxs-lookup"><span data-stu-id="c6829-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6829-282">0x01 - Sessão Repetida</span><span class="sxs-lookup"><span data-stu-id="c6829-282">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="c6829-283">0x02 - Uma chamada feita pelo operador em nome de um grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="c6829-283">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6829-284"><strong>Processa</strong></span><span class="sxs-lookup"><span data-stu-id="c6829-284"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="c6829-285">bits</span><span class="sxs-lookup"><span data-stu-id="c6829-285">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6829-286">Para uso interno pelo serviço de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="c6829-286">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="c6829-287">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c6829-287">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c6829-288">\* Para a maioria das sessões, SessionIdSeq terá o valor 1.</span><span class="sxs-lookup"><span data-stu-id="c6829-288">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="c6829-289">Se várias sessões iniciam exatamente ao mesmo tempo, o SessionIdSeq para uma delas será 1 e para a outra será 2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="c6829-289">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

