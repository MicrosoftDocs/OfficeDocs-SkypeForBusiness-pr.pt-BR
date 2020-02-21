---
title: 'Lync Server 2013: alterações feitas por Grant-CsSetupPermission'
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
ms.openlocfilehash: 98ac8f4f84280fb8980d38170fc964157b8037ee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="2b8ab-102">Alterações feitas pelo Grant-CsSetupPermission no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b8ab-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b8ab-103">_**Última modificação do tópico:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="2b8ab-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="2b8ab-104">Para delegar a instalação, você pode conceder permissões ao grupo universal RTCUniversalServerAdmins para uma OU (unidade organizacional) do Active Directory específica, permitindo que os membros do grupo RTCUniversalServerAdmins nesse OU instalem o Lync Server 2013 no domínio sem ser membro do grupo de administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="2b8ab-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="2b8ab-105">O cmdlet **Grant-CsSetupPermission** concede permissões do grupo RTCUniversalServerAdmins em um OU, conforme especificado na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="2b8ab-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="2b8ab-106">Permissões concedidas para Objetos no OU</span><span class="sxs-lookup"><span data-stu-id="2b8ab-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b8ab-107">As permissões aplicam-se:</span><span class="sxs-lookup"><span data-stu-id="2b8ab-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="2b8ab-108">As permissões concedidas são:</span><span class="sxs-lookup"><span data-stu-id="2b8ab-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b8ab-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b8ab-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="2b8ab-110">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="2b8ab-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b8ab-111">Ler servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="2b8ab-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-112">Gravar servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="2b8ab-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-113">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="2b8ab-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-114">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="2b8ab-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b8ab-115">Objetos do serviceConnectionPoint descendente</span><span class="sxs-lookup"><span data-stu-id="2b8ab-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="2b8ab-116">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="2b8ab-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b8ab-117">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="2b8ab-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-118">Permissões de gravação</span><span class="sxs-lookup"><span data-stu-id="2b8ab-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-119">Criar filho</span><span class="sxs-lookup"><span data-stu-id="2b8ab-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-120">Excluir filho</span><span class="sxs-lookup"><span data-stu-id="2b8ab-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-121">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="2b8ab-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-122">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-123">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-124">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="2b8ab-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b8ab-125">Objetos msRTCSIP-Server descendentes</span><span class="sxs-lookup"><span data-stu-id="2b8ab-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="2b8ab-126">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="2b8ab-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b8ab-127">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-128">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-129">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="2b8ab-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b8ab-130">Objetos msRTCSIP-WebComponents descendentes</span><span class="sxs-lookup"><span data-stu-id="2b8ab-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="2b8ab-131">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="2b8ab-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b8ab-132">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-133">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-134">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="2b8ab-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b8ab-135">Objetos msRTCSIP-MCU descendentes</span><span class="sxs-lookup"><span data-stu-id="2b8ab-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="2b8ab-136">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="2b8ab-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b8ab-137">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-138">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-139">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="2b8ab-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b8ab-140">Objetos msRTCSIP-MediationServer descendentes</span><span class="sxs-lookup"><span data-stu-id="2b8ab-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="2b8ab-141">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="2b8ab-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b8ab-142">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-143">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-144">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="2b8ab-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b8ab-145">Objetos msRTCSIP-ApplicationServer descendentes</span><span class="sxs-lookup"><span data-stu-id="2b8ab-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="2b8ab-146">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="2b8ab-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b8ab-147">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-148">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-149">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="2b8ab-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b8ab-150">Objetos msRTCSIP-ConnectionPoint descendentes</span><span class="sxs-lookup"><span data-stu-id="2b8ab-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="2b8ab-151">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="2b8ab-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b8ab-152">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-153">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-154">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="2b8ab-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b8ab-155">Objetos do computador descendentes</span><span class="sxs-lookup"><span data-stu-id="2b8ab-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="2b8ab-156">Acesso especial para serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="2b8ab-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b8ab-157">Criar objetos filhos</span><span class="sxs-lookup"><span data-stu-id="2b8ab-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-158">Excluir objetos filhos</span><span class="sxs-lookup"><span data-stu-id="2b8ab-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="2b8ab-159">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="2b8ab-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="2b8ab-160">Acesso especial para informação pública:</span><span class="sxs-lookup"><span data-stu-id="2b8ab-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b8ab-161">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="2b8ab-162">Acesso especial para nome de host DNS:</span><span class="sxs-lookup"><span data-stu-id="2b8ab-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b8ab-163">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="2b8ab-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

