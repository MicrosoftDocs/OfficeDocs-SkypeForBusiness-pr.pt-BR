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
ms.openlocfilehash: 12c9431e413428080f72d34510cdb3879e26e7cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="6d58d-102">Alterações feitas pelo Grant-CsSetupPermission no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d58d-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d58d-103">_**Última modificação do tópico:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="6d58d-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="6d58d-104">Para delegar a instalação, você pode conceder permissões ao grupo universal RTCUniversalServerAdmins para uma OU (unidade organizacional) do Active Directory específica, permitindo que os membros do grupo RTCUniversalServerAdmins nesse OU instalem o Lync Server 2013 no domínio sem ser membro do grupo de administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="6d58d-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="6d58d-105">O cmdlet **Grant-CsSetupPermission** concede permissões do grupo RTCUniversalServerAdmins em um OU, conforme especificado na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="6d58d-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="6d58d-106">Permissões concedidas para Objetos no OU</span><span class="sxs-lookup"><span data-stu-id="6d58d-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d58d-107">As permissões aplicam-se:</span><span class="sxs-lookup"><span data-stu-id="6d58d-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="6d58d-108">As permissões concedidas são:</span><span class="sxs-lookup"><span data-stu-id="6d58d-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d58d-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6d58d-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="6d58d-110">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="6d58d-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d58d-111">Ler servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="6d58d-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="6d58d-112">Gravar servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="6d58d-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="6d58d-113">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="6d58d-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="6d58d-114">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="6d58d-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d58d-115">Objetos do serviceConnectionPoint descendente</span><span class="sxs-lookup"><span data-stu-id="6d58d-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="6d58d-116">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="6d58d-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d58d-117">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="6d58d-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="6d58d-118">Permissões de gravação</span><span class="sxs-lookup"><span data-stu-id="6d58d-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="6d58d-119">Criar filho</span><span class="sxs-lookup"><span data-stu-id="6d58d-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="6d58d-120">Excluir filho</span><span class="sxs-lookup"><span data-stu-id="6d58d-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="6d58d-121">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="6d58d-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="6d58d-122">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="6d58d-123">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="6d58d-124">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="6d58d-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d58d-125">Objetos msRTCSIP-Server descendentes</span><span class="sxs-lookup"><span data-stu-id="6d58d-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="6d58d-126">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="6d58d-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d58d-127">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="6d58d-128">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="6d58d-129">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="6d58d-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d58d-130">Objetos msRTCSIP-WebComponents descendentes</span><span class="sxs-lookup"><span data-stu-id="6d58d-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="6d58d-131">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="6d58d-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d58d-132">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="6d58d-133">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="6d58d-134">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="6d58d-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d58d-135">Objetos msRTCSIP-MCU descendentes</span><span class="sxs-lookup"><span data-stu-id="6d58d-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="6d58d-136">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="6d58d-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d58d-137">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="6d58d-138">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="6d58d-139">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="6d58d-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d58d-140">Objetos msRTCSIP-MediationServer descendentes</span><span class="sxs-lookup"><span data-stu-id="6d58d-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="6d58d-141">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="6d58d-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d58d-142">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="6d58d-143">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="6d58d-144">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="6d58d-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d58d-145">Objetos msRTCSIP-ApplicationServer descendentes</span><span class="sxs-lookup"><span data-stu-id="6d58d-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="6d58d-146">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="6d58d-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d58d-147">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="6d58d-148">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="6d58d-149">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="6d58d-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d58d-150">Objetos msRTCSIP-ConnectionPoint descendentes</span><span class="sxs-lookup"><span data-stu-id="6d58d-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="6d58d-151">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="6d58d-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d58d-152">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="6d58d-153">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="6d58d-154">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="6d58d-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d58d-155">Objetos do computador descendentes</span><span class="sxs-lookup"><span data-stu-id="6d58d-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="6d58d-156">Acesso especial para serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="6d58d-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d58d-157">Criar objetos filhos</span><span class="sxs-lookup"><span data-stu-id="6d58d-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="6d58d-158">Excluir objetos filhos</span><span class="sxs-lookup"><span data-stu-id="6d58d-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="6d58d-159">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="6d58d-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="6d58d-160">Acesso especial para informação pública:</span><span class="sxs-lookup"><span data-stu-id="6d58d-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d58d-161">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="6d58d-162">Acesso especial para nome de host DNS:</span><span class="sxs-lookup"><span data-stu-id="6d58d-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d58d-163">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="6d58d-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

