---
title: 'Lync Server 2013: tabela VoipDetails'
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
ms.openlocfilehash: d459262d5126dc6d55f930b20e54cbb1e69e04e9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="0c7db-102">Tabela VoipDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c7db-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c7db-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="0c7db-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0c7db-104">Cada registro representa uma chamada de dois participantes na qual pelo menos um usuário utiliza VoIP.</span><span class="sxs-lookup"><span data-stu-id="0c7db-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c7db-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="0c7db-105">Column</span></span></th>
<th><span data-ttu-id="0c7db-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="0c7db-106">Data Type</span></span></th>
<th><span data-ttu-id="0c7db-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="0c7db-107">Key/Index</span></span></th>
<th><span data-ttu-id="0c7db-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="0c7db-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c7db-109"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="0c7db-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0c7db-110">datetime</span><span class="sxs-lookup"><span data-stu-id="0c7db-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="0c7db-111">Primário</span><span class="sxs-lookup"><span data-stu-id="0c7db-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="0c7db-112">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="0c7db-112">Time of session request.</span></span> <span data-ttu-id="0c7db-113">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="0c7db-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0c7db-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0c7db-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c7db-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0c7db-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0c7db-116">int</span><span class="sxs-lookup"><span data-stu-id="0c7db-116">int</span></span></p></td>
<td><p><span data-ttu-id="0c7db-117">Primário</span><span class="sxs-lookup"><span data-stu-id="0c7db-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="0c7db-118">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="0c7db-118">ID number to identify the session.</span></span> <span data-ttu-id="0c7db-119">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="0c7db-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="0c7db-120">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0c7db-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c7db-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="0c7db-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="0c7db-122">int</span><span class="sxs-lookup"><span data-stu-id="0c7db-122">int</span></span></p></td>
<td><p><span data-ttu-id="0c7db-123">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="0c7db-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0c7db-124"><strong>PhoneId</strong> do chamador.</span><span class="sxs-lookup"><span data-stu-id="0c7db-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="0c7db-125">Consulte a <a href="lync-server-2013-phones-table.md">tabela telefones no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0c7db-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="0c7db-126">Se não é NULL e <strong>FromGatewayId </strong> não é nulo, o chamador era um usuário PSTN.</span><span class="sxs-lookup"><span data-stu-id="0c7db-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c7db-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="0c7db-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="0c7db-128">int</span><span class="sxs-lookup"><span data-stu-id="0c7db-128">int</span></span></p></td>
<td><p><span data-ttu-id="0c7db-129">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="0c7db-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0c7db-130"><strong>PhoneId</strong> do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="0c7db-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="0c7db-131">Consulte a <a href="lync-server-2013-phones-table.md">tabela telefones no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0c7db-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="0c7db-132">Se não é NULL e <strong>ToGatewayId</strong> não é nulo, o receptor de chamada era um usuário PSTN.</span><span class="sxs-lookup"><span data-stu-id="0c7db-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c7db-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="0c7db-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="0c7db-134">int</span><span class="sxs-lookup"><span data-stu-id="0c7db-134">int</span></span></p></td>
<td><p><span data-ttu-id="0c7db-135">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="0c7db-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0c7db-136">O Servidor de Mediação de onde a chamada está vindo.</span><span class="sxs-lookup"><span data-stu-id="0c7db-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="0c7db-137">Consulte a <a href="lync-server-2013-mediationservers-table.md">tabela MediationServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0c7db-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c7db-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="0c7db-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="0c7db-139">int</span><span class="sxs-lookup"><span data-stu-id="0c7db-139">int</span></span></p></td>
<td><p><span data-ttu-id="0c7db-140">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="0c7db-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0c7db-141">O Servidor de Mediação para onde vai a chamada.</span><span class="sxs-lookup"><span data-stu-id="0c7db-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="0c7db-142">Consulte a <a href="lync-server-2013-mediationservers-table.md">tabela MediationServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0c7db-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c7db-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="0c7db-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="0c7db-144">int</span><span class="sxs-lookup"><span data-stu-id="0c7db-144">int</span></span></p></td>
<td><p><span data-ttu-id="0c7db-145">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="0c7db-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0c7db-146">O Gateway de onde a chamada é feita.</span><span class="sxs-lookup"><span data-stu-id="0c7db-146">Gateway the call is coming from.</span></span> <span data-ttu-id="0c7db-147">Consulte a <a href="lync-server-2013-gateways-table.md">tabela gateways no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0c7db-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c7db-148"><strong>Togatewayid</strong></span><span class="sxs-lookup"><span data-stu-id="0c7db-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="0c7db-149">int</span><span class="sxs-lookup"><span data-stu-id="0c7db-149">int</span></span></p></td>
<td><p><span data-ttu-id="0c7db-150">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="0c7db-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0c7db-151">O Gateway para onde a chamada vai.</span><span class="sxs-lookup"><span data-stu-id="0c7db-151">Gateway the call is going to.</span></span> <span data-ttu-id="0c7db-152">Consulte a <a href="lync-server-2013-gateways-table.md">tabela gateways no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0c7db-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c7db-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="0c7db-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="0c7db-154">int</span><span class="sxs-lookup"><span data-stu-id="0c7db-154">int</span></span></p></td>
<td><p><span data-ttu-id="0c7db-155">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="0c7db-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0c7db-156">URI do usuário que desconectou a chamada, se o usuário tem um URI.</span><span class="sxs-lookup"><span data-stu-id="0c7db-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="0c7db-157">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0c7db-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c7db-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="0c7db-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="0c7db-159">int</span><span class="sxs-lookup"><span data-stu-id="0c7db-159">int</span></span></p></td>
<td><p><span data-ttu-id="0c7db-160">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="0c7db-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0c7db-161">A ID do telefone que desconectou a chamada foi desconectada de um telefone.</span><span class="sxs-lookup"><span data-stu-id="0c7db-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="0c7db-162">Consulte a <a href="lync-server-2013-phones-table.md">tabela telefones no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0c7db-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

