---
title: 'Lync Server 2013: alterações feitas por Grant-CsSetupPermission'
description: 'Lync Server 2013: alterações feitas por Grant-CsSetupPermission.'
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
ms.openlocfilehash: d2a9156c977c993dd32e38fc6816bd08d3f65c1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543597"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="dbc11-103">Alterações feitas por Grant-CsSetupPermission no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc11-103">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbc11-104">_**Última modificação do tópico:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="dbc11-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="dbc11-105">Para delegar a instalação, você pode conceder permissões ao grupo universal RTCUniversalServerAdmins para uma OU (unidade organizacional) do Active Directory específica, permitindo que os membros do grupo RTCUniversalServerAdmins nesse OU instalem o Lync Server 2013 no domínio especificado sem ser membros do grupo de administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="dbc11-105">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="dbc11-106">O cmdlet **Grant-CsSetupPermission** concede permissões do grupo RTCUniversalServerAdmins em um OU, conforme especificado na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="dbc11-106">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="dbc11-107">Permissões concedidas para Objetos no OU</span><span class="sxs-lookup"><span data-stu-id="dbc11-107">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbc11-108">As permissões aplicam-se:</span><span class="sxs-lookup"><span data-stu-id="dbc11-108">Permissions apply to:</span></span></th>
<th><span data-ttu-id="dbc11-109">As permissões concedidas são:</span><span class="sxs-lookup"><span data-stu-id="dbc11-109">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbc11-110">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="dbc11-110">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="dbc11-111">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="dbc11-111">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbc11-112">Ler servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="dbc11-112">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="dbc11-113">Gravar servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="dbc11-113">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="dbc11-114">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="dbc11-114">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="dbc11-115">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="dbc11-115">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbc11-116">Objetos do serviceConnectionPoint descendente</span><span class="sxs-lookup"><span data-stu-id="dbc11-116">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="dbc11-117">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="dbc11-117">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbc11-118">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="dbc11-118">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="dbc11-119">Permissões de gravação</span><span class="sxs-lookup"><span data-stu-id="dbc11-119">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="dbc11-120">Criar filho</span><span class="sxs-lookup"><span data-stu-id="dbc11-120">Create child</span></span></p></li>
<li><p><span data-ttu-id="dbc11-121">Excluir filho</span><span class="sxs-lookup"><span data-stu-id="dbc11-121">Delete child</span></span></p></li>
<li><p><span data-ttu-id="dbc11-122">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="dbc11-122">List contents</span></span></p></li>
<li><p><span data-ttu-id="dbc11-123">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-123">Write property</span></span></p></li>
<li><p><span data-ttu-id="dbc11-124">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-124">Read property</span></span></p></li>
<li><p><span data-ttu-id="dbc11-125">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="dbc11-125">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbc11-126">Objetos msRTCSIP-Server descendentes</span><span class="sxs-lookup"><span data-stu-id="dbc11-126">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="dbc11-127">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="dbc11-127">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbc11-128">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-128">Write property</span></span></p></li>
<li><p><span data-ttu-id="dbc11-129">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-129">Read property</span></span></p></li>
<li><p><span data-ttu-id="dbc11-130">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="dbc11-130">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbc11-131">Objetos msRTCSIP-WebComponents descendentes</span><span class="sxs-lookup"><span data-stu-id="dbc11-131">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="dbc11-132">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="dbc11-132">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbc11-133">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-133">Write property</span></span></p></li>
<li><p><span data-ttu-id="dbc11-134">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-134">Read property</span></span></p></li>
<li><p><span data-ttu-id="dbc11-135">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="dbc11-135">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbc11-136">Objetos msRTCSIP-MCU descendentes</span><span class="sxs-lookup"><span data-stu-id="dbc11-136">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="dbc11-137">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="dbc11-137">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbc11-138">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-138">Write property</span></span></p></li>
<li><p><span data-ttu-id="dbc11-139">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-139">Read property</span></span></p></li>
<li><p><span data-ttu-id="dbc11-140">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="dbc11-140">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbc11-141">Objetos msRTCSIP-MediationServer descendentes</span><span class="sxs-lookup"><span data-stu-id="dbc11-141">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="dbc11-142">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="dbc11-142">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbc11-143">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-143">Write property</span></span></p></li>
<li><p><span data-ttu-id="dbc11-144">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-144">Read property</span></span></p></li>
<li><p><span data-ttu-id="dbc11-145">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="dbc11-145">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbc11-146">Objetos msRTCSIP-ApplicationServer descendentes</span><span class="sxs-lookup"><span data-stu-id="dbc11-146">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="dbc11-147">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="dbc11-147">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbc11-148">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-148">Write property</span></span></p></li>
<li><p><span data-ttu-id="dbc11-149">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-149">Read property</span></span></p></li>
<li><p><span data-ttu-id="dbc11-150">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="dbc11-150">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbc11-151">Objetos msRTCSIP-ConnectionPoint descendentes</span><span class="sxs-lookup"><span data-stu-id="dbc11-151">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="dbc11-152">Acesso especial:</span><span class="sxs-lookup"><span data-stu-id="dbc11-152">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbc11-153">Gravar propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-153">Write property</span></span></p></li>
<li><p><span data-ttu-id="dbc11-154">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-154">Read property</span></span></p></li>
<li><p><span data-ttu-id="dbc11-155">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="dbc11-155">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbc11-156">Objetos do computador descendentes</span><span class="sxs-lookup"><span data-stu-id="dbc11-156">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="dbc11-157">Acesso especial para serviceConnectionPoint:</span><span class="sxs-lookup"><span data-stu-id="dbc11-157">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbc11-158">Criar objetos filhos</span><span class="sxs-lookup"><span data-stu-id="dbc11-158">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="dbc11-159">Excluir objetos filhos</span><span class="sxs-lookup"><span data-stu-id="dbc11-159">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="dbc11-160">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="dbc11-160">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="dbc11-161">Acesso especial para informação pública:</span><span class="sxs-lookup"><span data-stu-id="dbc11-161">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbc11-162">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-162">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="dbc11-163">Acesso especial para nome de host DNS:</span><span class="sxs-lookup"><span data-stu-id="dbc11-163">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbc11-164">Ler propriedade</span><span class="sxs-lookup"><span data-stu-id="dbc11-164">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

