---
title: 'Lync Server 2013: Tabela VoipDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f13087202b15cf9b25f0c32741c396c48f628908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="87d6c-102">Tabela VoipDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87d6c-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87d6c-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="87d6c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="87d6c-104">Cada registro representa uma chamada de 1 2 a terceiros na qual pelo menos um usuário é um usuário de VoIP.</span><span class="sxs-lookup"><span data-stu-id="87d6c-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87d6c-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="87d6c-105">Column</span></span></th>
<th><span data-ttu-id="87d6c-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="87d6c-106">Data Type</span></span></th>
<th><span data-ttu-id="87d6c-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="87d6c-107">Key/Index</span></span></th>
<th><span data-ttu-id="87d6c-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="87d6c-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87d6c-109"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="87d6c-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87d6c-110">datetime</span><span class="sxs-lookup"><span data-stu-id="87d6c-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="87d6c-111">Primária</span><span class="sxs-lookup"><span data-stu-id="87d6c-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="87d6c-112">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="87d6c-112">Time of session request.</span></span> <span data-ttu-id="87d6c-113">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="87d6c-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="87d6c-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="87d6c-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87d6c-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="87d6c-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="87d6c-116">int</span><span class="sxs-lookup"><span data-stu-id="87d6c-116">int</span></span></p></td>
<td><p><span data-ttu-id="87d6c-117">Primária</span><span class="sxs-lookup"><span data-stu-id="87d6c-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="87d6c-118">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="87d6c-118">ID number to identify the session.</span></span> <span data-ttu-id="87d6c-119">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="87d6c-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="87d6c-120">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="87d6c-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87d6c-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="87d6c-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="87d6c-122">int</span><span class="sxs-lookup"><span data-stu-id="87d6c-122">int</span></span></p></td>
<td><p><span data-ttu-id="87d6c-123">Exterior</span><span class="sxs-lookup"><span data-stu-id="87d6c-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87d6c-124">Identificação de <strong>telefone</strong> do chamador.</span><span class="sxs-lookup"><span data-stu-id="87d6c-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="87d6c-125">Consulte a <a href="lync-server-2013-phones-table.md">tabela de telefones no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="87d6c-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="87d6c-126">Se não for nulo e <strong>FromGatewayId</strong> não for nulo, o chamador será um usuário PSTN.</span><span class="sxs-lookup"><span data-stu-id="87d6c-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87d6c-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="87d6c-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="87d6c-128">int</span><span class="sxs-lookup"><span data-stu-id="87d6c-128">int</span></span></p></td>
<td><p><span data-ttu-id="87d6c-129">Exterior</span><span class="sxs-lookup"><span data-stu-id="87d6c-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87d6c-130"><strong>Número de telefoneid</strong> do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="87d6c-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="87d6c-131">Consulte a <a href="lync-server-2013-phones-table.md">tabela de telefones no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="87d6c-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="87d6c-132">Se não for nulo e <strong>Togatewayid</strong> não for nulo, o receptor da chamada será um usuário PSTN.</span><span class="sxs-lookup"><span data-stu-id="87d6c-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87d6c-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="87d6c-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="87d6c-134">int</span><span class="sxs-lookup"><span data-stu-id="87d6c-134">int</span></span></p></td>
<td><p><span data-ttu-id="87d6c-135">Exterior</span><span class="sxs-lookup"><span data-stu-id="87d6c-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87d6c-136">O servidor de mediação do qual a chamada está vindo.</span><span class="sxs-lookup"><span data-stu-id="87d6c-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="87d6c-137">Consulte a <a href="lync-server-2013-mediationservers-table.md">tabela MediationServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="87d6c-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87d6c-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="87d6c-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="87d6c-139">int</span><span class="sxs-lookup"><span data-stu-id="87d6c-139">int</span></span></p></td>
<td><p><span data-ttu-id="87d6c-140">Exterior</span><span class="sxs-lookup"><span data-stu-id="87d6c-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87d6c-141">O servidor de mediação chamado está indo para.</span><span class="sxs-lookup"><span data-stu-id="87d6c-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="87d6c-142">Consulte a <a href="lync-server-2013-mediationservers-table.md">tabela MediationServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="87d6c-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87d6c-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="87d6c-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="87d6c-144">int</span><span class="sxs-lookup"><span data-stu-id="87d6c-144">int</span></span></p></td>
<td><p><span data-ttu-id="87d6c-145">Exterior</span><span class="sxs-lookup"><span data-stu-id="87d6c-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87d6c-146">Gateway do qual a chamada está vindo.</span><span class="sxs-lookup"><span data-stu-id="87d6c-146">Gateway the call is coming from.</span></span> <span data-ttu-id="87d6c-147">Consulte a <a href="lync-server-2013-gateways-table.md">tabela gateways no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="87d6c-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87d6c-148"><strong>Togatewayid</strong></span><span class="sxs-lookup"><span data-stu-id="87d6c-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="87d6c-149">int</span><span class="sxs-lookup"><span data-stu-id="87d6c-149">int</span></span></p></td>
<td><p><span data-ttu-id="87d6c-150">Exterior</span><span class="sxs-lookup"><span data-stu-id="87d6c-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87d6c-151">Gateway em que a chamada vai.</span><span class="sxs-lookup"><span data-stu-id="87d6c-151">Gateway the call is going to.</span></span> <span data-ttu-id="87d6c-152">Consulte a <a href="lync-server-2013-gateways-table.md">tabela gateways no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="87d6c-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87d6c-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="87d6c-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="87d6c-154">int</span><span class="sxs-lookup"><span data-stu-id="87d6c-154">int</span></span></p></td>
<td><p><span data-ttu-id="87d6c-155">Exterior</span><span class="sxs-lookup"><span data-stu-id="87d6c-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87d6c-156">URI do usuário que desconectou a chamada, se o usuário tiver um URI.</span><span class="sxs-lookup"><span data-stu-id="87d6c-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="87d6c-157">Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="87d6c-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87d6c-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="87d6c-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="87d6c-159">int</span><span class="sxs-lookup"><span data-stu-id="87d6c-159">int</span></span></p></td>
<td><p><span data-ttu-id="87d6c-160">Exterior</span><span class="sxs-lookup"><span data-stu-id="87d6c-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87d6c-161">ID do telefone que desconectou a chamada foi desconectado de um telefone.</span><span class="sxs-lookup"><span data-stu-id="87d6c-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="87d6c-162">Consulte a <a href="lync-server-2013-phones-table.md">tabela de telefones no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="87d6c-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

