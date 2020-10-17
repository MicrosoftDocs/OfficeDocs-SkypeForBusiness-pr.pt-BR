---
title: 'Lync Server 2013: tabela VoipDetails'
description: 'Lync Server 2013: tabela VoipDetails.'
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
ms.openlocfilehash: f23d991c1d577a15717de2572d744e1b65ba6bab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566277"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="5020e-103">Tabela VoipDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5020e-103">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5020e-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5020e-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5020e-105">Cada registro representa uma chamada de dois participantes na qual pelo menos um usuário utiliza VoIP.</span><span class="sxs-lookup"><span data-stu-id="5020e-105">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5020e-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="5020e-106">Column</span></span></th>
<th><span data-ttu-id="5020e-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="5020e-107">Data Type</span></span></th>
<th><span data-ttu-id="5020e-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="5020e-108">Key/Index</span></span></th>
<th><span data-ttu-id="5020e-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5020e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5020e-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="5020e-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5020e-111">datetime</span><span class="sxs-lookup"><span data-stu-id="5020e-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5020e-112">Primário</span><span class="sxs-lookup"><span data-stu-id="5020e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5020e-113">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="5020e-113">Time of session request.</span></span> <span data-ttu-id="5020e-114">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="5020e-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="5020e-115">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5020e-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5020e-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5020e-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5020e-117">int</span><span class="sxs-lookup"><span data-stu-id="5020e-117">int</span></span></p></td>
<td><p><span data-ttu-id="5020e-118">Primário</span><span class="sxs-lookup"><span data-stu-id="5020e-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="5020e-119">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="5020e-119">ID number to identify the session.</span></span> <span data-ttu-id="5020e-120">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="5020e-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="5020e-121">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5020e-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5020e-122"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="5020e-122"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="5020e-123">int</span><span class="sxs-lookup"><span data-stu-id="5020e-123">int</span></span></p></td>
<td><p><span data-ttu-id="5020e-124">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="5020e-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5020e-125"><strong>PhoneId</strong> do chamador.</span><span class="sxs-lookup"><span data-stu-id="5020e-125"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="5020e-126">Consulte a <a href="lync-server-2013-phones-table.md">tabela telefones no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5020e-126">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="5020e-127">Se não é NULL e <strong>FromGatewayId </strong> não é nulo, o chamador era um usuário PSTN.</span><span class="sxs-lookup"><span data-stu-id="5020e-127">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5020e-128"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="5020e-128"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="5020e-129">int</span><span class="sxs-lookup"><span data-stu-id="5020e-129">int</span></span></p></td>
<td><p><span data-ttu-id="5020e-130">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="5020e-130">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5020e-131"><strong>PhoneId</strong> do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="5020e-131"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="5020e-132">Consulte a <a href="lync-server-2013-phones-table.md">tabela telefones no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5020e-132">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="5020e-133">Se não é NULL e <strong>ToGatewayId</strong> não é nulo, o receptor de chamada era um usuário PSTN.</span><span class="sxs-lookup"><span data-stu-id="5020e-133">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5020e-134"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="5020e-134"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5020e-135">int</span><span class="sxs-lookup"><span data-stu-id="5020e-135">int</span></span></p></td>
<td><p><span data-ttu-id="5020e-136">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="5020e-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5020e-137">O Servidor de Mediação de onde a chamada está vindo.</span><span class="sxs-lookup"><span data-stu-id="5020e-137">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="5020e-138">Consulte a <a href="lync-server-2013-mediationservers-table.md">tabela MediationServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5020e-138">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5020e-139"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="5020e-139"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5020e-140">int</span><span class="sxs-lookup"><span data-stu-id="5020e-140">int</span></span></p></td>
<td><p><span data-ttu-id="5020e-141">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="5020e-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5020e-142">O Servidor de Mediação para onde vai a chamada.</span><span class="sxs-lookup"><span data-stu-id="5020e-142">The Mediation Server called is going to.</span></span> <span data-ttu-id="5020e-143">Consulte a <a href="lync-server-2013-mediationservers-table.md">tabela MediationServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5020e-143">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5020e-144"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="5020e-144"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="5020e-145">int</span><span class="sxs-lookup"><span data-stu-id="5020e-145">int</span></span></p></td>
<td><p><span data-ttu-id="5020e-146">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="5020e-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5020e-147">O Gateway de onde a chamada é feita.</span><span class="sxs-lookup"><span data-stu-id="5020e-147">Gateway the call is coming from.</span></span> <span data-ttu-id="5020e-148">Consulte a <a href="lync-server-2013-gateways-table.md">tabela gateways no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5020e-148">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5020e-149"><strong>Togatewayid</strong></span><span class="sxs-lookup"><span data-stu-id="5020e-149"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="5020e-150">int</span><span class="sxs-lookup"><span data-stu-id="5020e-150">int</span></span></p></td>
<td><p><span data-ttu-id="5020e-151">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="5020e-151">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5020e-152">O Gateway para onde a chamada vai.</span><span class="sxs-lookup"><span data-stu-id="5020e-152">Gateway the call is going to.</span></span> <span data-ttu-id="5020e-153">Consulte a <a href="lync-server-2013-gateways-table.md">tabela gateways no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5020e-153">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5020e-154"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="5020e-154"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="5020e-155">int</span><span class="sxs-lookup"><span data-stu-id="5020e-155">int</span></span></p></td>
<td><p><span data-ttu-id="5020e-156">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="5020e-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5020e-157">URI do usuário que desconectou a chamada, se o usuário tem um URI.</span><span class="sxs-lookup"><span data-stu-id="5020e-157">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="5020e-158">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5020e-158">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5020e-159"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="5020e-159"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="5020e-160">int</span><span class="sxs-lookup"><span data-stu-id="5020e-160">int</span></span></p></td>
<td><p><span data-ttu-id="5020e-161">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="5020e-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5020e-162">A ID do telefone que desconectou a chamada foi desconectada de um telefone.</span><span class="sxs-lookup"><span data-stu-id="5020e-162">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="5020e-163">Consulte a <a href="lync-server-2013-phones-table.md">tabela telefones no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5020e-163">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

