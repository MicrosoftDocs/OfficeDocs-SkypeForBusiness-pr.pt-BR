---
title: 'Lync Server 2013: alterações feitas por Grant-CsOUPermission'
description: 'Lync Server 2013: alterações feitas por Grant-CsOUPermission.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d3db0e9dde380628690bc016e2b4bd2ec85b54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543607"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="f441e-103">Alterações feitas por Grant-CsOUPermission no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f441e-103">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f441e-104">_**Última modificação do tópico:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="f441e-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="f441e-105">Para delegar a administração do Lync Server 2013, você pode adicionar permissões a unidades organizacionais (UOs) especificadas para que os membros dos grupos universais RTC criados pela preparação da floresta possam acessar as UOs sem ser membros do grupo Administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="f441e-105">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="f441e-106">O cmdlet **Grant-CsOuPermission** concede permissões para objetos no OU especificado conforme mostrado nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="f441e-106">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="f441e-107">Concedendo permissões para objetos do usuário</span><span class="sxs-lookup"><span data-stu-id="f441e-107">Granting Permission for User Objects</span></span>

<span data-ttu-id="f441e-108">Ao executar o cmdlet **Grant-CsOuPermission** para objetos do Usuário em um OU, os grupos são concedidos com permissões exibidas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f441e-108">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="f441e-109">Permissões concedidas para objetos do usuário</span><span class="sxs-lookup"><span data-stu-id="f441e-109">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f441e-110">Grupo</span><span class="sxs-lookup"><span data-stu-id="f441e-110">Group</span></span></th>
<th><span data-ttu-id="f441e-111">Permissão</span><span class="sxs-lookup"><span data-stu-id="f441e-111">Permission</span></span></th>
<th><span data-ttu-id="f441e-112">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="f441e-112">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f441e-113">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f441e-113">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="f441e-114">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="f441e-114">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="f441e-115">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-115">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f441e-116">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-116">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-117">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="f441e-117">List contents</span></span></p>
<p><span data-ttu-id="f441e-118">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="f441e-118">Read all properties</span></span></p>
<p><span data-ttu-id="f441e-119">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="f441e-119">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f441e-120">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-120">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f441e-121">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-121">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-122">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="f441e-122">List contents</span></span></p>
<p><span data-ttu-id="f441e-123">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="f441e-123">Read all properties</span></span></p>
<p><span data-ttu-id="f441e-124">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="f441e-124">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f441e-125">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-125">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f441e-126">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-126">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-127">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-127">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f441e-128">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-128">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f441e-129">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-129">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="f441e-130">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="f441e-130">Read Public-Information</span></span></p>
<p><span data-ttu-id="f441e-131">Ler General-Information</span><span class="sxs-lookup"><span data-stu-id="f441e-131">Read General-Information</span></span></p>
<p><span data-ttu-id="f441e-132">Ler User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="f441e-132">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="f441e-133">Objetos do usuário descendente</span><span class="sxs-lookup"><span data-stu-id="f441e-133">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f441e-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f441e-134">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="f441e-135">Gravara RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-135">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f441e-136">Gravar msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="f441e-136">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="f441e-137">Gravar RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-137">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f441e-138">Gravar RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-138">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="f441e-139">Gravar proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f441e-139">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="f441e-140">Objetos do usuário descendente</span><span class="sxs-lookup"><span data-stu-id="f441e-140">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="f441e-141">Conceder permissões para objetos do computador</span><span class="sxs-lookup"><span data-stu-id="f441e-141">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="f441e-142">Ao executar o cmdlet **Grant-CsOuPermission** para objetos de computador em um OU, os grupos são concedidos com as permissões mostradas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f441e-142">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="f441e-143">Permissões concedidas para objetos do computador</span><span class="sxs-lookup"><span data-stu-id="f441e-143">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f441e-144">Grupo</span><span class="sxs-lookup"><span data-stu-id="f441e-144">Group</span></span></th>
<th><span data-ttu-id="f441e-145">Permissão</span><span class="sxs-lookup"><span data-stu-id="f441e-145">Permission</span></span></th>
<th><span data-ttu-id="f441e-146">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="f441e-146">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f441e-147">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f441e-147">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="f441e-148">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="f441e-148">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="f441e-149">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-149">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f441e-150">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-150">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-151">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="f441e-151">List contents</span></span></p>
<p><span data-ttu-id="f441e-152">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="f441e-152">Read all properties</span></span></p>
<p><span data-ttu-id="f441e-153">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="f441e-153">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f441e-154">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-154">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f441e-155">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-155">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-156">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="f441e-156">List contents</span></span></p>
<p><span data-ttu-id="f441e-157">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="f441e-157">Read all properties</span></span></p>
<p><span data-ttu-id="f441e-158">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="f441e-158">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f441e-159">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-159">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f441e-160">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-160">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-161">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="f441e-161">Read Public-Information</span></span></p>
<p><span data-ttu-id="f441e-162">Ler Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="f441e-162">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="f441e-163">Objetos do computador descendente</span><span class="sxs-lookup"><span data-stu-id="f441e-163">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f441e-164">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f441e-164">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="f441e-165">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="f441e-165">Read Public-Information</span></span></p>
<p><span data-ttu-id="f441e-166">Ler Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="f441e-166">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="f441e-167">Objetos do computador descendente</span><span class="sxs-lookup"><span data-stu-id="f441e-167">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="f441e-168">Concedendo permissões para contato ou objetos AppContact</span><span class="sxs-lookup"><span data-stu-id="f441e-168">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="f441e-169">Ao executar o cmdlet **Grant-CsOuPermission** para objetos de Contato ou AppContact em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f441e-169">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="f441e-170">Permissões concedidas para os objetos Contato ou AppContact</span><span class="sxs-lookup"><span data-stu-id="f441e-170">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f441e-171">Grupo</span><span class="sxs-lookup"><span data-stu-id="f441e-171">Group</span></span></th>
<th><span data-ttu-id="f441e-172">Permissão</span><span class="sxs-lookup"><span data-stu-id="f441e-172">Permission</span></span></th>
<th><span data-ttu-id="f441e-173">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="f441e-173">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f441e-174">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f441e-174">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="f441e-175">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="f441e-175">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="f441e-176">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-176">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f441e-177">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-177">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-178">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="f441e-178">List contents</span></span></p>
<p><span data-ttu-id="f441e-179">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="f441e-179">Read all properties</span></span></p>
<p><span data-ttu-id="f441e-180">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="f441e-180">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f441e-181">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-181">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f441e-182">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-182">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-183">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="f441e-183">List contents</span></span></p>
<p><span data-ttu-id="f441e-184">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="f441e-184">Read all properties</span></span></p>
<p><span data-ttu-id="f441e-185">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="f441e-185">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f441e-186">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-186">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f441e-187">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-187">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-188">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-188">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f441e-189">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-189">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f441e-190">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-190">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="f441e-191">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="f441e-191">Read Public-Information</span></span></p>
<p><span data-ttu-id="f441e-192">Ler General-Information</span><span class="sxs-lookup"><span data-stu-id="f441e-192">Read General-Information</span></span></p>
<p><span data-ttu-id="f441e-193">Ler Personal-Information</span><span class="sxs-lookup"><span data-stu-id="f441e-193">Read Personal-Information</span></span></p>
<p><span data-ttu-id="f441e-194">Ler User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="f441e-194">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="f441e-195">Objetos de contato descendente</span><span class="sxs-lookup"><span data-stu-id="f441e-195">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f441e-196">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f441e-196">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="f441e-197">Gravar RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-197">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f441e-198">Gravar otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="f441e-198">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="f441e-199">Gravar displayName</span><span class="sxs-lookup"><span data-stu-id="f441e-199">Write displayName</span></span></p>
<p><span data-ttu-id="f441e-200">Descrição de gravação</span><span class="sxs-lookup"><span data-stu-id="f441e-200">Write description</span></span></p>
<p><span data-ttu-id="f441e-201">Gravar telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="f441e-201">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="f441e-202">Gravar msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="f441e-202">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="f441e-203">Gravar RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-203">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f441e-204">Gravar RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-204">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="f441e-205">Gravar proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f441e-205">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="f441e-206">Objetos de contato descendente</span><span class="sxs-lookup"><span data-stu-id="f441e-206">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="f441e-207">Concedendo permissões para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="f441e-207">Granting Permission for Device Objects</span></span>

<span data-ttu-id="f441e-208">Ao executar o cmdlet **Grant-CsOuPermission** para objetos de Dispositivo em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f441e-208">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="f441e-209">Permissões concedidos para objetos de Dispositivo</span><span class="sxs-lookup"><span data-stu-id="f441e-209">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f441e-210">Grupo</span><span class="sxs-lookup"><span data-stu-id="f441e-210">Group</span></span></th>
<th><span data-ttu-id="f441e-211">Permissão</span><span class="sxs-lookup"><span data-stu-id="f441e-211">Permission</span></span></th>
<th><span data-ttu-id="f441e-212">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="f441e-212">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f441e-213">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f441e-213">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="f441e-214">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="f441e-214">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="f441e-215">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-215">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f441e-216">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-216">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-217">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="f441e-217">List contents</span></span></p>
<p><span data-ttu-id="f441e-218">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="f441e-218">Read all properties</span></span></p>
<p><span data-ttu-id="f441e-219">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="f441e-219">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f441e-220">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-220">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f441e-221">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-221">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-222">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="f441e-222">List contents</span></span></p>
<p><span data-ttu-id="f441e-223">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="f441e-223">Read all properties</span></span></p>
<p><span data-ttu-id="f441e-224">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="f441e-224">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f441e-225">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-225">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f441e-226">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-226">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-227">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-227">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f441e-228">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-228">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f441e-229">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-229">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="f441e-230">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="f441e-230">Read Public-Information</span></span></p>
<p><span data-ttu-id="f441e-231">Ler Personal-Information</span><span class="sxs-lookup"><span data-stu-id="f441e-231">Read Personal-Information</span></span></p>
<p><span data-ttu-id="f441e-232">Ler General-Information</span><span class="sxs-lookup"><span data-stu-id="f441e-232">Read General-Information</span></span></p>
<p><span data-ttu-id="f441e-233">Ler User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="f441e-233">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="f441e-234">Objetos de contato descendente</span><span class="sxs-lookup"><span data-stu-id="f441e-234">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f441e-235">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f441e-235">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="f441e-236">Criar filho</span><span class="sxs-lookup"><span data-stu-id="f441e-236">Create child</span></span></p>
<p><span data-ttu-id="f441e-237">Excluir filho</span><span class="sxs-lookup"><span data-stu-id="f441e-237">Delete child</span></span></p>
<p><span data-ttu-id="f441e-238">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="f441e-238">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="f441e-239">Contato</span><span class="sxs-lookup"><span data-stu-id="f441e-239">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f441e-240">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f441e-240">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="f441e-241">Gravar displayName</span><span class="sxs-lookup"><span data-stu-id="f441e-241">Write displayName</span></span></p>
<p><span data-ttu-id="f441e-242">Descrição de gravação</span><span class="sxs-lookup"><span data-stu-id="f441e-242">Write description</span></span></p>
<p><span data-ttu-id="f441e-243">Gravar telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="f441e-243">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="f441e-244">Objetos do usuário descendente</span><span class="sxs-lookup"><span data-stu-id="f441e-244">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f441e-245">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f441e-245">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="f441e-246">Gravar RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-246">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f441e-247">Gravar otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="f441e-247">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="f441e-248">Gravar displayName</span><span class="sxs-lookup"><span data-stu-id="f441e-248">Write displayName</span></span></p>
<p><span data-ttu-id="f441e-249">Descrição de gravação</span><span class="sxs-lookup"><span data-stu-id="f441e-249">Write description</span></span></p>
<p><span data-ttu-id="f441e-250">Gravar telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="f441e-250">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="f441e-251">Gravar msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="f441e-251">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="f441e-252">Gravar RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-252">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f441e-253">Gravar RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-253">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="f441e-254">Gravar proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f441e-254">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="f441e-255">Objetos de contato descendente</span><span class="sxs-lookup"><span data-stu-id="f441e-255">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="f441e-256">Concedendo permissões para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="f441e-256">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="f441e-257">Ao executar o cmdlet **Grant-CsOuPermission** para objetos InetOrgPerson em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f441e-257">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="f441e-258">Permissões concedidas para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="f441e-258">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f441e-259">Grupo</span><span class="sxs-lookup"><span data-stu-id="f441e-259">Group</span></span></th>
<th><span data-ttu-id="f441e-260">Permissão</span><span class="sxs-lookup"><span data-stu-id="f441e-260">Permission</span></span></th>
<th><span data-ttu-id="f441e-261">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="f441e-261">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f441e-262">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="f441e-262">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="f441e-263">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="f441e-263">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="f441e-264">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-264">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f441e-265">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-265">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-266">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="f441e-266">List contents</span></span></p>
<p><span data-ttu-id="f441e-267">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="f441e-267">Read all properties</span></span></p>
<p><span data-ttu-id="f441e-268">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="f441e-268">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f441e-269">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-269">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f441e-270">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-270">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-271">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="f441e-271">List contents</span></span></p>
<p><span data-ttu-id="f441e-272">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="f441e-272">Read all properties</span></span></p>
<p><span data-ttu-id="f441e-273">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="f441e-273">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="f441e-274">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="f441e-274">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f441e-275">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="f441e-275">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="f441e-276">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-276">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f441e-277">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-277">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f441e-278">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-278">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="f441e-279">Ler Personal-Information</span><span class="sxs-lookup"><span data-stu-id="f441e-279">Read Personal-Information</span></span></p>
<p><span data-ttu-id="f441e-280">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="f441e-280">Read Public-Information</span></span></p>
<p><span data-ttu-id="f441e-281">Ler General-Information</span><span class="sxs-lookup"><span data-stu-id="f441e-281">Read General-Information</span></span></p>
<p><span data-ttu-id="f441e-282">Ler User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="f441e-282">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="f441e-283">Objetos inetOrgPerson descendentes</span><span class="sxs-lookup"><span data-stu-id="f441e-283">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f441e-284">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="f441e-284">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="f441e-285">Gravar RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-285">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="f441e-286">Gravar RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-286">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="f441e-287">Gravar RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="f441e-287">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="f441e-288">Gravar proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f441e-288">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="f441e-289">Objetos inetOrgPerson descendentes</span><span class="sxs-lookup"><span data-stu-id="f441e-289">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

