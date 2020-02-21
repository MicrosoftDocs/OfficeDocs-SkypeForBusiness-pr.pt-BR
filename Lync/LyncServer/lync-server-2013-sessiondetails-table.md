---
title: 'Lync Server 2013: tabela SessionDetails'
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
ms.openlocfilehash: bfdf5552f150b23c50e8ad6867e90f96a6b586fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="eef97-102">Tabela SessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eef97-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eef97-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="eef97-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="eef97-104">Cada registro representa uma sessão ponto a ponto, que poderia ser uma chamada telefônica VoIP-VoIP, uma sessão de IM de duas partes ou outro tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="eef97-105">Você pode executar uma junção de tabela com a [tabela de mídia no Lync Server 2013](lync-server-2013-media-table.md) para encontrar os detalhes de cada mídia envolvida nesta sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="eef97-106">Observe que os campos IsUser1IntegratedWithDeskPhone e IsUser2IntegratedWithDeskPhone foram descartados da tabela SessionDetails usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eef97-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eef97-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="eef97-107">Column</span></span></th>
<th><span data-ttu-id="eef97-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="eef97-108">Data Type</span></span></th>
<th><span data-ttu-id="eef97-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="eef97-109">Key/Index</span></span></th>
<th><span data-ttu-id="eef97-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="eef97-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eef97-111"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-112">datetime</span><span class="sxs-lookup"><span data-stu-id="eef97-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="eef97-113">Primária, Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-114">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-114">Time of session request.</span></span> <span data-ttu-id="eef97-115">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="eef97-116">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-118">int</span><span class="sxs-lookup"><span data-stu-id="eef97-118">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-119">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="eef97-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-120">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-120">ID number to identify the session.</span></span> <span data-ttu-id="eef97-121">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma sessão. \* consulte a <a href="lync-server-2013-dialogs-table.md">tabela Dialogs no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-123">identificador</span><span class="sxs-lookup"><span data-stu-id="eef97-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-124">Um GUID para correlacionar várias sessões.</span><span class="sxs-lookup"><span data-stu-id="eef97-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-126">datetime</span><span class="sxs-lookup"><span data-stu-id="eef97-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="eef97-127">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-128">O número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual.</span><span class="sxs-lookup"><span data-stu-id="eef97-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="eef97-129">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-131">int</span><span class="sxs-lookup"><span data-stu-id="eef97-131">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-132">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-133">O número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-133">ID number to identify the session.</span></span> <span data-ttu-id="eef97-134">Usado em conjunto com <strong>ReplacesDialogIdTime </strong> para identificar exclusivamente uma sessão que é substituída por esta sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="eef97-135">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-136"><strong>Usuário1id</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-137">int</span><span class="sxs-lookup"><span data-stu-id="eef97-137">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-138">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-139">A ID de um usuário na sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-139">ID of one user in the session.</span></span> <span data-ttu-id="eef97-140">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-142">int</span><span class="sxs-lookup"><span data-stu-id="eef97-142">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-143">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-144">A ID de outro usuário na sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-144">ID of the other user in the session.</span></span> <span data-ttu-id="eef97-145">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-147">Identificador</span><span class="sxs-lookup"><span data-stu-id="eef97-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-148">GUID que identifica o ponto de extremidade usado pelo primeiro usuário na sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="eef97-149">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eef97-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-151">Identificador</span><span class="sxs-lookup"><span data-stu-id="eef97-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-152">GUID que identifica o ponto de extremidade usado pelo segundo usuário na sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="eef97-153">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eef97-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-155">int</span><span class="sxs-lookup"><span data-stu-id="eef97-155">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-156">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-157">A solicitação original Para o URI do usuário no SIP.</span><span class="sxs-lookup"><span data-stu-id="eef97-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="eef97-158">consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-160">int</span><span class="sxs-lookup"><span data-stu-id="eef97-160">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-161">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-162">A ID do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-162">ID of the user who started the session.</span></span> <span data-ttu-id="eef97-163">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-165">int</span><span class="sxs-lookup"><span data-stu-id="eef97-165">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-166">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-167">Indica a ID do usuário que está em nome do chamador.</span><span class="sxs-lookup"><span data-stu-id="eef97-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="eef97-168">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-170">int</span><span class="sxs-lookup"><span data-stu-id="eef97-170">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-171">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-172">A ID do usuário a quem se refere a chamada.</span><span class="sxs-lookup"><span data-stu-id="eef97-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="eef97-173">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-175">int</span><span class="sxs-lookup"><span data-stu-id="eef97-175">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-176">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-177">A ID do servidor Front-End usado para esta sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="eef97-178">Consulte a <a href="lync-server-2013-servers-table.md">tabela de servidores no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-179"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-180">int</span><span class="sxs-lookup"><span data-stu-id="eef97-180">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-181">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-182">A ID do pool no qual a sessão foi capturada.</span><span class="sxs-lookup"><span data-stu-id="eef97-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="eef97-183">Consulte a <a href="lync-server-2013-pools-table.md">tabela pools no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-184"><strong>ContentTypeid</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-185">int</span><span class="sxs-lookup"><span data-stu-id="eef97-185">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-186">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-187">Tipo de conteúdo usado na sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-187">Content type used in the session.</span></span> <span data-ttu-id="eef97-188">Consulte a <a href="lync-server-2013-contenttypes-table.md">tabela ContentTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-190">int</span><span class="sxs-lookup"><span data-stu-id="eef97-190">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-191">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-192">A versão do cliente usada pelo Usuário1.</span><span class="sxs-lookup"><span data-stu-id="eef97-192">Client version used by User1.</span></span> <span data-ttu-id="eef97-193">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-195">int</span><span class="sxs-lookup"><span data-stu-id="eef97-195">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-196">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-197">A versão do cliente usada pelo Usuário2.</span><span class="sxs-lookup"><span data-stu-id="eef97-197">Client version used by User2.</span></span> <span data-ttu-id="eef97-198">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-200">int</span><span class="sxs-lookup"><span data-stu-id="eef97-200">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-201">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-202">O Servidor de Borda usado pelo Usuário1.</span><span class="sxs-lookup"><span data-stu-id="eef97-202">Edge Server used by User1.</span></span> <span data-ttu-id="eef97-203">Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-205">int</span><span class="sxs-lookup"><span data-stu-id="eef97-205">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-206">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-207">O Servidor de Borda usado pelo Usuário2.</span><span class="sxs-lookup"><span data-stu-id="eef97-207">Edge Server used by User2.</span></span> <span data-ttu-id="eef97-208">Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-210">bits</span><span class="sxs-lookup"><span data-stu-id="eef97-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-211">Se o Usuário1 está conectado internamente ou não.</span><span class="sxs-lookup"><span data-stu-id="eef97-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-213">bits</span><span class="sxs-lookup"><span data-stu-id="eef97-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-214">Se o Usuário2 está conectado internamente ou não.</span><span class="sxs-lookup"><span data-stu-id="eef97-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-215"><strong>Invitetime</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-216">datetime</span><span class="sxs-lookup"><span data-stu-id="eef97-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-217">A hora da primeira solicitação INVITE.</span><span class="sxs-lookup"><span data-stu-id="eef97-217">The time of the first INVITE request.</span></span> <span data-ttu-id="eef97-218">Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="eef97-219">Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="eef97-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="eef97-220">Este campo é normalmente preenchido pelos dados gerados a partir da mensagem INVITE inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="eef97-221">Se não houver mensagem INVITE, então o campo será preenchido com a data e hora da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="eef97-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-223">datetime</span><span class="sxs-lookup"><span data-stu-id="eef97-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-224">O tempo de resposta da primeira mensagem INVITE.</span><span class="sxs-lookup"><span data-stu-id="eef97-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="eef97-225">Este campo é tipicamente preenchido pelos dados gerados pela mensagem INVITE inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="eef97-226">Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="eef97-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-228">int</span><span class="sxs-lookup"><span data-stu-id="eef97-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-p121">Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="eef97-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-232"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-233">int</span><span class="sxs-lookup"><span data-stu-id="eef97-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-234">ID de diagnóstico capturada do cabeçalho SIP.</span><span class="sxs-lookup"><span data-stu-id="eef97-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-236">int</span><span class="sxs-lookup"><span data-stu-id="eef97-236">int</span></span></p></td>
<td><p><span data-ttu-id="eef97-237">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="eef97-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eef97-238">Prioridade de chamada.</span><span class="sxs-lookup"><span data-stu-id="eef97-238">Call priority.</span></span> <span data-ttu-id="eef97-239">Consulte a <a href="lync-server-2013-callpriorities-table.md">tabela CallPriorities no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="eef97-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-241">int</span><span class="sxs-lookup"><span data-stu-id="eef97-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-242">O número de mensagens enviadas pelo Usuário1 durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-244">int</span><span class="sxs-lookup"><span data-stu-id="eef97-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-245">O número de mensagens enviadas pelo Usuário2 durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-247">datetime</span><span class="sxs-lookup"><span data-stu-id="eef97-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-248">Hora ao final da sessão.</span><span class="sxs-lookup"><span data-stu-id="eef97-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-250">int</span><span class="sxs-lookup"><span data-stu-id="eef97-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-p123">Um conjunto de bits que indica o tipo de mídia esta sessão. As definições dos tipos estão listadas:</span><span class="sxs-lookup"><span data-stu-id="eef97-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eef97-253">Mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="eef97-253">IM</span></span></p></td>
<td><p><span data-ttu-id="eef97-254">1</span><span class="sxs-lookup"><span data-stu-id="eef97-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="eef97-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="eef97-256">duas</span><span class="sxs-lookup"><span data-stu-id="eef97-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="eef97-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="eef97-258">quatro</span><span class="sxs-lookup"><span data-stu-id="eef97-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="eef97-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="eef97-260">8 </span><span class="sxs-lookup"><span data-stu-id="eef97-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-261">AÚDIO</span><span class="sxs-lookup"><span data-stu-id="eef97-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="eef97-262">16 </span><span class="sxs-lookup"><span data-stu-id="eef97-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-263">VÍDEOS</span><span class="sxs-lookup"><span data-stu-id="eef97-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="eef97-264">32</span><span class="sxs-lookup"><span data-stu-id="eef97-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="eef97-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="eef97-266">64</span><span class="sxs-lookup"><span data-stu-id="eef97-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-268">smallint</span><span class="sxs-lookup"><span data-stu-id="eef97-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-p124">Um conjunto de bits que indica os atributos do Usuário1. As seguintes definições de atributo são listadas:</span><span class="sxs-lookup"><span data-stu-id="eef97-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="eef97-271">0x01 - Integrado com telefone de mesa</span><span class="sxs-lookup"><span data-stu-id="eef97-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-273">smallint</span><span class="sxs-lookup"><span data-stu-id="eef97-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-p125">Um conjunto de bits que indica os atributos do Usuário2. As seguintes definições de atributo são listadas:</span><span class="sxs-lookup"><span data-stu-id="eef97-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="eef97-276">0x01 - Integrado com telefone da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="eef97-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eef97-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-278">smallint</span><span class="sxs-lookup"><span data-stu-id="eef97-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-p126">Um conjunto de bits que indica os atributos da chamada. As seguintes definições de atributo são listadas:</span><span class="sxs-lookup"><span data-stu-id="eef97-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="eef97-281">0x01 - Sessão Repetida</span><span class="sxs-lookup"><span data-stu-id="eef97-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="eef97-282">0x02 - Uma chamada feita pelo operador em nome de um grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="eef97-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eef97-283"><strong>Processa</strong></span><span class="sxs-lookup"><span data-stu-id="eef97-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="eef97-284">bits</span><span class="sxs-lookup"><span data-stu-id="eef97-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eef97-285">Para uso interno pelo serviço de Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="eef97-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="eef97-286">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eef97-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eef97-287">\*Para a maioria das sessões, SessionIdSeq terá o valor 1.</span><span class="sxs-lookup"><span data-stu-id="eef97-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="eef97-288">Se várias sessões iniciam exatamente ao mesmo tempo, o SessionIdSeq para uma delas será 1 e para a outra será 2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="eef97-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

