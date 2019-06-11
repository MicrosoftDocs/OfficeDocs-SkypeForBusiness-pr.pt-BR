---
title: 'Lync Server 2013: Tabela VoipDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7879f5dc7d5b884dfc2d3777ed4fa800978a3cff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="cabdd-102">Tabela VoipDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cabdd-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cabdd-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cabdd-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cabdd-104">Cada registro representa uma chamada de 1 2 a terceiros na qual pelo menos um usuário é um usuário de VoIP.</span><span class="sxs-lookup"><span data-stu-id="cabdd-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cabdd-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="cabdd-105">Column</span></span></th>
<th><span data-ttu-id="cabdd-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="cabdd-106">Data Type</span></span></th>
<th><span data-ttu-id="cabdd-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="cabdd-107">Key/Index</span></span></th>
<th><span data-ttu-id="cabdd-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="cabdd-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cabdd-109"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="cabdd-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cabdd-110">datetime</span><span class="sxs-lookup"><span data-stu-id="cabdd-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="cabdd-111">Primária</span><span class="sxs-lookup"><span data-stu-id="cabdd-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="cabdd-112">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="cabdd-112">Time of session request.</span></span> <span data-ttu-id="cabdd-113">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="cabdd-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="cabdd-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cabdd-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cabdd-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cabdd-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cabdd-116">int</span><span class="sxs-lookup"><span data-stu-id="cabdd-116">int</span></span></p></td>
<td><p><span data-ttu-id="cabdd-117">Primária</span><span class="sxs-lookup"><span data-stu-id="cabdd-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="cabdd-118">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="cabdd-118">ID number to identify the session.</span></span> <span data-ttu-id="cabdd-119">Usado em conjunto com <strong></strong> a identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="cabdd-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="cabdd-120">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cabdd-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cabdd-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="cabdd-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="cabdd-122">int</span><span class="sxs-lookup"><span data-stu-id="cabdd-122">int</span></span></p></td>
<td><p><span data-ttu-id="cabdd-123">Exterior</span><span class="sxs-lookup"><span data-stu-id="cabdd-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cabdd-124">Identificação de <strong>telefone</strong> do chamador.</span><span class="sxs-lookup"><span data-stu-id="cabdd-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="cabdd-125">Consulte a <a href="lync-server-2013-phones-table.md">tabela de telefones no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cabdd-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="cabdd-126">Se não for nulo e <strong>FromGatewayId</strong> não for nulo, o chamador será um usuário PSTN.</span><span class="sxs-lookup"><span data-stu-id="cabdd-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cabdd-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="cabdd-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="cabdd-128">int</span><span class="sxs-lookup"><span data-stu-id="cabdd-128">int</span></span></p></td>
<td><p><span data-ttu-id="cabdd-129">Exterior</span><span class="sxs-lookup"><span data-stu-id="cabdd-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cabdd-130"><strong>Número</strong> de telefoneid do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="cabdd-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="cabdd-131">Consulte a <a href="lync-server-2013-phones-table.md">tabela de telefones no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cabdd-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="cabdd-132">Se não for nulo <strong></strong> e togatewayid não for nulo, o receptor da chamada será um usuário PSTN.</span><span class="sxs-lookup"><span data-stu-id="cabdd-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cabdd-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="cabdd-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="cabdd-134">int</span><span class="sxs-lookup"><span data-stu-id="cabdd-134">int</span></span></p></td>
<td><p><span data-ttu-id="cabdd-135">Exterior</span><span class="sxs-lookup"><span data-stu-id="cabdd-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cabdd-136">O servidor de mediação do qual a chamada está vindo.</span><span class="sxs-lookup"><span data-stu-id="cabdd-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="cabdd-137">Consulte a <a href="lync-server-2013-mediationservers-table.md">tabela MediationServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cabdd-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cabdd-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="cabdd-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="cabdd-139">int</span><span class="sxs-lookup"><span data-stu-id="cabdd-139">int</span></span></p></td>
<td><p><span data-ttu-id="cabdd-140">Exterior</span><span class="sxs-lookup"><span data-stu-id="cabdd-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cabdd-141">O servidor de mediação chamado está indo para.</span><span class="sxs-lookup"><span data-stu-id="cabdd-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="cabdd-142">Consulte a <a href="lync-server-2013-mediationservers-table.md">tabela MediationServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cabdd-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cabdd-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="cabdd-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="cabdd-144">int</span><span class="sxs-lookup"><span data-stu-id="cabdd-144">int</span></span></p></td>
<td><p><span data-ttu-id="cabdd-145">Exterior</span><span class="sxs-lookup"><span data-stu-id="cabdd-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cabdd-146">Gateway do qual a chamada está vindo.</span><span class="sxs-lookup"><span data-stu-id="cabdd-146">Gateway the call is coming from.</span></span> <span data-ttu-id="cabdd-147">Consulte a <a href="lync-server-2013-gateways-table.md">tabela gateways no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cabdd-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cabdd-148"><strong>Togatewayid</strong></span><span class="sxs-lookup"><span data-stu-id="cabdd-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="cabdd-149">int</span><span class="sxs-lookup"><span data-stu-id="cabdd-149">int</span></span></p></td>
<td><p><span data-ttu-id="cabdd-150">Exterior</span><span class="sxs-lookup"><span data-stu-id="cabdd-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cabdd-151">Gateway em que a chamada vai.</span><span class="sxs-lookup"><span data-stu-id="cabdd-151">Gateway the call is going to.</span></span> <span data-ttu-id="cabdd-152">Consulte a <a href="lync-server-2013-gateways-table.md">tabela gateways no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cabdd-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cabdd-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="cabdd-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="cabdd-154">int</span><span class="sxs-lookup"><span data-stu-id="cabdd-154">int</span></span></p></td>
<td><p><span data-ttu-id="cabdd-155">Exterior</span><span class="sxs-lookup"><span data-stu-id="cabdd-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cabdd-156">URI do usuário que desconectou a chamada, se o usuário tiver um URI.</span><span class="sxs-lookup"><span data-stu-id="cabdd-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="cabdd-157">Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cabdd-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cabdd-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="cabdd-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="cabdd-159">int</span><span class="sxs-lookup"><span data-stu-id="cabdd-159">int</span></span></p></td>
<td><p><span data-ttu-id="cabdd-160">Exterior</span><span class="sxs-lookup"><span data-stu-id="cabdd-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cabdd-161">ID do telefone que desconectou a chamada foi desconectado de um telefone.</span><span class="sxs-lookup"><span data-stu-id="cabdd-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="cabdd-162">Consulte a <a href="lync-server-2013-phones-table.md">tabela de telefones no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cabdd-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

