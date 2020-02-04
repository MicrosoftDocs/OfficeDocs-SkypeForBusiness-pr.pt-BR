---
title: 'Lync Server 2013: alterações feitas pela concessão-CsSetupPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d82b896f1d6d1da1184bfa61d7352c9b4803a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="d8fb7-102">Alterações feitas pelo Grant-CsSetupPermission no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8fb7-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8fb7-103">_**Tópico da última modificação:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="d8fb7-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="d8fb7-104">Para delegar a instalação, você pode conceder permissões ao grupo universal RTCUniversalServerAdmins para uma unidade organizacional (OU) específica do Active Directory, permitindo que os membros do grupo RTCUniversalServerAdmins dessa UO instalem o Lync Server 2013 no especificado domínio sem ser membro do grupo Domain admins.</span><span class="sxs-lookup"><span data-stu-id="d8fb7-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="d8fb7-105">O cmdlet **Grant-CsSetupPermission** concede as permissões do grupo RTCUniversalServerAdmins em uma UO, conforme especificado na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="d8fb7-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="d8fb7-106">Permissões concedidas a objetos na OU</span><span class="sxs-lookup"><span data-stu-id="d8fb7-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8fb7-107">As permissões se aplicam a:</span><span class="sxs-lookup"><span data-stu-id="d8fb7-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="d8fb7-108">Permissões concedidas são:</span><span class="sxs-lookup"><span data-stu-id="d8fb7-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8fb7-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d8fb7-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="d8fb7-110">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="d8fb7-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="d8fb7-111">Leia servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="d8fb7-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-112">Gravar servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="d8fb7-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-113">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="d8fb7-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-114">Replicando alterações de diretório</span><span class="sxs-lookup"><span data-stu-id="d8fb7-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8fb7-115">Objetos serviceConnectionPoint do descendant</span><span class="sxs-lookup"><span data-stu-id="d8fb7-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="d8fb7-116">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="d8fb7-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="d8fb7-117">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="d8fb7-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-118">Permissões de gravação</span><span class="sxs-lookup"><span data-stu-id="d8fb7-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-119">Criar filho</span><span class="sxs-lookup"><span data-stu-id="d8fb7-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-120">Excluir filho</span><span class="sxs-lookup"><span data-stu-id="d8fb7-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-121">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="d8fb7-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-122">Propriedade de gravação</span><span class="sxs-lookup"><span data-stu-id="d8fb7-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-123">Propriedade ler</span><span class="sxs-lookup"><span data-stu-id="d8fb7-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-124">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="d8fb7-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8fb7-125">Objetos msRTCSIP-Server descendentes</span><span class="sxs-lookup"><span data-stu-id="d8fb7-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="d8fb7-126">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="d8fb7-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="d8fb7-127">Propriedade de gravação</span><span class="sxs-lookup"><span data-stu-id="d8fb7-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-128">Propriedade ler</span><span class="sxs-lookup"><span data-stu-id="d8fb7-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-129">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="d8fb7-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8fb7-130">Objetos msRTCSIP descendentes-WebComponents</span><span class="sxs-lookup"><span data-stu-id="d8fb7-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="d8fb7-131">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="d8fb7-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="d8fb7-132">Propriedade de gravação</span><span class="sxs-lookup"><span data-stu-id="d8fb7-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-133">Propriedade ler</span><span class="sxs-lookup"><span data-stu-id="d8fb7-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-134">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="d8fb7-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8fb7-135">Objetos descendentes msRTCSIP-MCU</span><span class="sxs-lookup"><span data-stu-id="d8fb7-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="d8fb7-136">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="d8fb7-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="d8fb7-137">Propriedade de gravação</span><span class="sxs-lookup"><span data-stu-id="d8fb7-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-138">Propriedade ler</span><span class="sxs-lookup"><span data-stu-id="d8fb7-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-139">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="d8fb7-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8fb7-140">Objetos msRTCSIP-MediationServer descendentes</span><span class="sxs-lookup"><span data-stu-id="d8fb7-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="d8fb7-141">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="d8fb7-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="d8fb7-142">Propriedade de gravação</span><span class="sxs-lookup"><span data-stu-id="d8fb7-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-143">Propriedade ler</span><span class="sxs-lookup"><span data-stu-id="d8fb7-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-144">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="d8fb7-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8fb7-145">Objetos msRTCSIP-ApplicationServer descendentes</span><span class="sxs-lookup"><span data-stu-id="d8fb7-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="d8fb7-146">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="d8fb7-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="d8fb7-147">Propriedade de gravação</span><span class="sxs-lookup"><span data-stu-id="d8fb7-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-148">Propriedade ler</span><span class="sxs-lookup"><span data-stu-id="d8fb7-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-149">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="d8fb7-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8fb7-150">Objetos descendentes msRTCSIP-ConnectionPoint</span><span class="sxs-lookup"><span data-stu-id="d8fb7-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="d8fb7-151">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="d8fb7-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="d8fb7-152">Propriedade de gravação</span><span class="sxs-lookup"><span data-stu-id="d8fb7-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-153">Propriedade ler</span><span class="sxs-lookup"><span data-stu-id="d8fb7-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-154">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="d8fb7-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8fb7-155">Objetos de computador descendentes</span><span class="sxs-lookup"><span data-stu-id="d8fb7-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="d8fb7-156">Acesso especial para serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="d8fb7-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="d8fb7-157">Criar objetos filho</span><span class="sxs-lookup"><span data-stu-id="d8fb7-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-158">Excluir objetos filho</span><span class="sxs-lookup"><span data-stu-id="d8fb7-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="d8fb7-159">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="d8fb7-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="d8fb7-160">Acesso especial para informações públicas:</span><span class="sxs-lookup"><span data-stu-id="d8fb7-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="d8fb7-161">Propriedade ler</span><span class="sxs-lookup"><span data-stu-id="d8fb7-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="d8fb7-162">Acesso especial para o nome do host DNS:</span><span class="sxs-lookup"><span data-stu-id="d8fb7-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="d8fb7-163">Propriedade ler</span><span class="sxs-lookup"><span data-stu-id="d8fb7-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

