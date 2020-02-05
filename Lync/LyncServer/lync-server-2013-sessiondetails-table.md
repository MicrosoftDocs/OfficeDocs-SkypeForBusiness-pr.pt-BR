---
title: 'Lync Server 2013: Tabela SessionDetails'
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
ms.openlocfilehash: b68c50fc17199c68a69c5a7c6dd6abc8a5bd1dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="0e4c3-102">Tabela SessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e4c3-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e4c3-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="0e4c3-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0e4c3-104">Cada registro representa uma sessão ponto a ponto, que pode ser uma chamada telefônica VoIP-VoIP, uma sessão de IM de duas partes ou outro tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="0e4c3-105">Você pode executar uma junção de tabela com a [tabela de mídia no Lync Server 2013](lync-server-2013-media-table.md) para encontrar os detalhes de cada mídia envolvida nesta sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="0e4c3-106">Observe que os campos IsUser1IntegratedWithDeskPhone e IsUser2IntegratedWithDeskPhone foram descartados da tabela SessionDetails usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e4c3-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="0e4c3-107">Column</span></span></th>
<th><span data-ttu-id="0e4c3-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="0e4c3-108">Data Type</span></span></th>
<th><span data-ttu-id="0e4c3-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="0e4c3-109">Key/Index</span></span></th>
<th><span data-ttu-id="0e4c3-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="0e4c3-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-111"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0e4c3-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-113">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="0e4c3-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-114">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-114">Time of session request.</span></span> <span data-ttu-id="0e4c3-115">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0e4c3-116">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-118">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-118">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-119">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="0e4c3-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-120">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-120">ID number to identify the session.</span></span> <span data-ttu-id="0e4c3-121">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma sessão. \* consulte a <a href="lync-server-2013-dialogs-table.md">tabela de caixas de diálogo no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-123">identificador</span><span class="sxs-lookup"><span data-stu-id="0e4c3-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-124">Um GUID para correlacionar várias sessões.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-126">datetime</span><span class="sxs-lookup"><span data-stu-id="0e4c3-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-127">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-128">Número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="0e4c3-129">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-131">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-131">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-132">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-133">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-133">ID number to identify the session.</span></span> <span data-ttu-id="0e4c3-134">Usado em conjunto com <strong>ReplacesDialogIdTime</strong> para identificar exclusivamente uma sessão substituída por esta sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="0e4c3-135">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-136"><strong>Usuário1id</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-137">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-137">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-138">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-139">ID de um usuário na sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-139">ID of one user in the session.</span></span> <span data-ttu-id="0e4c3-140">Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-142">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-142">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-143">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-144">ID do outro usuário na sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-144">ID of the other user in the session.</span></span> <span data-ttu-id="0e4c3-145">Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-147">Identificador</span><span class="sxs-lookup"><span data-stu-id="0e4c3-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-148">GUID que identifica o ponto de extremidade usado pelo primeiro usuário na sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="0e4c3-149">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-151">Identificador</span><span class="sxs-lookup"><span data-stu-id="0e4c3-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-152">GUID que identifica o ponto de extremidade usado pelo segundo usuário na sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="0e4c3-153">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-155">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-155">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-156">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-157">O URI do usuário original na solicitação SIP.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="0e4c3-158">consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-160">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-160">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-161">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-162">ID do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-162">ID of the user who started the session.</span></span> <span data-ttu-id="0e4c3-163">Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-165">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-165">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-166">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-167">Indica a ID do usuário de quem o chamador está em nome.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="0e4c3-168">Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-170">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-170">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-171">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-172">ID do usuário por quem a chamada é referida.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="0e4c3-173">Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-174"><strong>ServerID</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-175">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-175">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-176">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-177">ID do servidor front-end usado para esta sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="0e4c3-178">Consulte a <a href="lync-server-2013-servers-table.md">tabela servidores no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-179"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-180">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-180">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-181">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-182">ID do pool no qual a sessão foi capturada.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="0e4c3-183">Consulte a <a href="lync-server-2013-pools-table.md">tabela de grupos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-184"><strong>ContentTypeid</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-185">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-185">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-186">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-187">Tipo de conteúdo usado na sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-187">Content type used in the session.</span></span> <span data-ttu-id="0e4c3-188">Consulte a <a href="lync-server-2013-contenttypes-table.md">tabela ContentTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-190">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-190">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-191">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-192">Versão do cliente usada pelo Usuário1.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-192">Client version used by User1.</span></span> <span data-ttu-id="0e4c3-193">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-195">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-195">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-196">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-197">Versão do cliente usada pelo user2.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-197">Client version used by User2.</span></span> <span data-ttu-id="0e4c3-198">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-200">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-200">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-201">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-202">Servidor de borda usado pelo Usuário1.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-202">Edge Server used by User1.</span></span> <span data-ttu-id="0e4c3-203">Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-205">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-205">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-206">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-207">Servidor de borda usado pelo user2.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-207">Edge Server used by User2.</span></span> <span data-ttu-id="0e4c3-208">Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-210">bit</span><span class="sxs-lookup"><span data-stu-id="0e4c3-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-211">Se user1 está conectado de Internal ou not.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-213">bit</span><span class="sxs-lookup"><span data-stu-id="0e4c3-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-214">Se o User2 está conectado do Internal ou não.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-215"><strong>Invitetime</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-216">datetime</span><span class="sxs-lookup"><span data-stu-id="0e4c3-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-217">A hora da primeira solicitação INVITE.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-217">The time of the first INVITE request.</span></span> <span data-ttu-id="0e4c3-218">Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="0e4c3-219">Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</span><span class="sxs-lookup"><span data-stu-id="0e4c3-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="0e4c3-220">Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="0e4c3-221">Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</span><span class="sxs-lookup"><span data-stu-id="0e4c3-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-223">datetime</span><span class="sxs-lookup"><span data-stu-id="0e4c3-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-224">A hora da resposta para a primeira mensagem de convite.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="0e4c3-225">Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="0e4c3-226">Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</span><span class="sxs-lookup"><span data-stu-id="0e4c3-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-228">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-229">Código de resposta SIP para o convite da sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-229">SIP response code to the session invitation.</span></span> <span data-ttu-id="0e4c3-230">Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-230">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="0e4c3-231">Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</span><span class="sxs-lookup"><span data-stu-id="0e4c3-231">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-232"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-233">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-234">ID de diagnóstico capturada do cabeçalho SIP.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-236">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-236">int</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-237">Exterior</span><span class="sxs-lookup"><span data-stu-id="0e4c3-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-238">Prioridade da chamada.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-238">Call priority.</span></span> <span data-ttu-id="0e4c3-239">Consulte a <a href="lync-server-2013-callpriorities-table.md">tabela CallPriorities no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-241">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-242">Número de mensagens enviadas pelo Usuário1 durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-244">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-245">Número de mensagens enviadas pelo user2 durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-247">datetime</span><span class="sxs-lookup"><span data-stu-id="0e4c3-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-248">Hora no final da sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-250">int</span><span class="sxs-lookup"><span data-stu-id="0e4c3-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-251">Um conjunto de bits que indica o tipo de mídia desta sessão.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-251">A bit set that indicates the media type of this session.</span></span> <span data-ttu-id="0e4c3-252">Listadas são as definições dos tipos:</span><span class="sxs-lookup"><span data-stu-id="0e4c3-252">Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-253">Mensagem instantânea</span><span class="sxs-lookup"><span data-stu-id="0e4c3-253">IM</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-254">1</span><span class="sxs-lookup"><span data-stu-id="0e4c3-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="0e4c3-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-256">2</span><span class="sxs-lookup"><span data-stu-id="0e4c3-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="0e4c3-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-258">4</span><span class="sxs-lookup"><span data-stu-id="0e4c3-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="0e4c3-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-260">8</span><span class="sxs-lookup"><span data-stu-id="0e4c3-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-261">ÁUDIO</span><span class="sxs-lookup"><span data-stu-id="0e4c3-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-262">16</span><span class="sxs-lookup"><span data-stu-id="0e4c3-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-263">VIDEO</span><span class="sxs-lookup"><span data-stu-id="0e4c3-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-264">32</span><span class="sxs-lookup"><span data-stu-id="0e4c3-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="0e4c3-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="0e4c3-266">64</span><span class="sxs-lookup"><span data-stu-id="0e4c3-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-268">smallint</span><span class="sxs-lookup"><span data-stu-id="0e4c3-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-269">Um conjunto de bits que indica os atributos Usuário1.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-269">A bit set that indicates the User1 attributes.</span></span> <span data-ttu-id="0e4c3-270">As definições de atributo a seguir estão listadas:</span><span class="sxs-lookup"><span data-stu-id="0e4c3-270">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="0e4c3-271">0x01-integrado ao telefone desktop</span><span class="sxs-lookup"><span data-stu-id="0e4c3-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-273">smallint</span><span class="sxs-lookup"><span data-stu-id="0e4c3-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-274">Um conjunto de bits que indica os atributos do user2.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-274">A bit set that indicates the User2 attributes.</span></span> <span data-ttu-id="0e4c3-275">As definições de atributo a seguir estão listadas:</span><span class="sxs-lookup"><span data-stu-id="0e4c3-275">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="0e4c3-276">0x01-integrado ao telefone desktop</span><span class="sxs-lookup"><span data-stu-id="0e4c3-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4c3-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-278">smallint</span><span class="sxs-lookup"><span data-stu-id="0e4c3-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-279">Um conjunto de bits que indica os atributos da chamada.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-279">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="0e4c3-280">As definições de atributo a seguir estão listadas:</span><span class="sxs-lookup"><span data-stu-id="0e4c3-280">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="0e4c3-281">0x01-sessão repetida</span><span class="sxs-lookup"><span data-stu-id="0e4c3-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="0e4c3-282">0x02-uma chamada feita pelo agente em nome de um grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="0e4c3-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e4c3-283"><strong>Processe</strong></span><span class="sxs-lookup"><span data-stu-id="0e4c3-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="0e4c3-284">bit</span><span class="sxs-lookup"><span data-stu-id="0e4c3-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e4c3-285">Para uso interno pelo serviço de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="0e4c3-286">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0e4c3-287">\*Para a maioria das sessões, o SessionIdSeq terá o valor de 1.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="0e4c3-288">Se várias sessões começarem exatamente ao mesmo tempo, o SessionIdSeq de uma será 1, por outro será 2, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

