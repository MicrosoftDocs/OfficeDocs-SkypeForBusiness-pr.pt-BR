---
title: 'Lync Server 2013: alterações feitas por Grant-CsOUPermission'
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
ms.openlocfilehash: 0ff916c0b4e284f9c6ce4d5dbaf9c2e196ed4bc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529428"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="e95e9-102">Alterações feitas por Grant-CsOUPermission no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e95e9-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e95e9-103">_**Última modificação do tópico:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="e95e9-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="e95e9-104">Para delegar a administração do Lync Server 2013, você pode adicionar permissões a unidades organizacionais (UOs) especificadas para que os membros dos grupos universais RTC criados pela preparação da floresta possam acessar as UOs sem ser membros do grupo Administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="e95e9-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="e95e9-105">O cmdlet **Grant-CsOuPermission** concede permissões para objetos no OU especificado conforme mostrado nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="e95e9-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="e95e9-106">Concedendo permissões para objetos do usuário</span><span class="sxs-lookup"><span data-stu-id="e95e9-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="e95e9-107">Ao executar o cmdlet **Grant-CsOuPermission** para objetos do Usuário em um OU, os grupos são concedidos com permissões exibidas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e95e9-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="e95e9-108">Permissões concedidas para objetos do usuário</span><span class="sxs-lookup"><span data-stu-id="e95e9-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e95e9-109">Grupo</span><span class="sxs-lookup"><span data-stu-id="e95e9-109">Group</span></span></th>
<th><span data-ttu-id="e95e9-110">Permissão</span><span class="sxs-lookup"><span data-stu-id="e95e9-110">Permission</span></span></th>
<th><span data-ttu-id="e95e9-111">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="e95e9-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e95e9-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e95e9-113">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="e95e9-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e95e9-114">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e95e9-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-116">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="e95e9-116">List contents</span></span></p>
<p><span data-ttu-id="e95e9-117">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="e95e9-117">Read all properties</span></span></p>
<p><span data-ttu-id="e95e9-118">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="e95e9-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e95e9-119">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-121">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="e95e9-121">List contents</span></span></p>
<p><span data-ttu-id="e95e9-122">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="e95e9-122">Read all properties</span></span></p>
<p><span data-ttu-id="e95e9-123">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="e95e9-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e95e9-124">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e95e9-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-126">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-127">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-128">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-129">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="e95e9-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="e95e9-130">Ler General-Information</span><span class="sxs-lookup"><span data-stu-id="e95e9-130">Read General-Information</span></span></p>
<p><span data-ttu-id="e95e9-131">Ler User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="e95e9-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="e95e9-132">Objetos do usuário descendente</span><span class="sxs-lookup"><span data-stu-id="e95e9-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e95e9-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e95e9-134">Gravara RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-135">Gravar msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="e95e9-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="e95e9-136">Gravar RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-137">Gravar RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-138">Gravar proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="e95e9-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e95e9-139">Objetos do usuário descendente</span><span class="sxs-lookup"><span data-stu-id="e95e9-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="e95e9-140">Conceder permissões para objetos do computador</span><span class="sxs-lookup"><span data-stu-id="e95e9-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="e95e9-141">Ao executar o cmdlet **Grant-CsOuPermission** para objetos de computador em um OU, os grupos são concedidos com as permissões mostradas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e95e9-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="e95e9-142">Permissões concedidas para objetos do computador</span><span class="sxs-lookup"><span data-stu-id="e95e9-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e95e9-143">Grupo</span><span class="sxs-lookup"><span data-stu-id="e95e9-143">Group</span></span></th>
<th><span data-ttu-id="e95e9-144">Permissão</span><span class="sxs-lookup"><span data-stu-id="e95e9-144">Permission</span></span></th>
<th><span data-ttu-id="e95e9-145">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="e95e9-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e95e9-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e95e9-147">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="e95e9-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e95e9-148">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e95e9-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-150">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="e95e9-150">List contents</span></span></p>
<p><span data-ttu-id="e95e9-151">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="e95e9-151">Read all properties</span></span></p>
<p><span data-ttu-id="e95e9-152">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="e95e9-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e95e9-153">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-155">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="e95e9-155">List contents</span></span></p>
<p><span data-ttu-id="e95e9-156">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="e95e9-156">Read all properties</span></span></p>
<p><span data-ttu-id="e95e9-157">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="e95e9-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e95e9-158">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e95e9-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-160">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="e95e9-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="e95e9-161">Ler Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="e95e9-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="e95e9-162">Objetos do computador descendente</span><span class="sxs-lookup"><span data-stu-id="e95e9-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e95e9-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e95e9-164">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="e95e9-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="e95e9-165">Ler Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="e95e9-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="e95e9-166">Objetos do computador descendente</span><span class="sxs-lookup"><span data-stu-id="e95e9-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="e95e9-167">Concedendo permissões para contato ou objetos AppContact</span><span class="sxs-lookup"><span data-stu-id="e95e9-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="e95e9-168">Ao executar o cmdlet **Grant-CsOuPermission** para objetos de Contato ou AppContact em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e95e9-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="e95e9-169">Permissões concedidas para os objetos Contato ou AppContact</span><span class="sxs-lookup"><span data-stu-id="e95e9-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e95e9-170">Grupo</span><span class="sxs-lookup"><span data-stu-id="e95e9-170">Group</span></span></th>
<th><span data-ttu-id="e95e9-171">Permissão</span><span class="sxs-lookup"><span data-stu-id="e95e9-171">Permission</span></span></th>
<th><span data-ttu-id="e95e9-172">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="e95e9-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e95e9-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e95e9-174">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="e95e9-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e95e9-175">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e95e9-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-177">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="e95e9-177">List contents</span></span></p>
<p><span data-ttu-id="e95e9-178">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="e95e9-178">Read all properties</span></span></p>
<p><span data-ttu-id="e95e9-179">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="e95e9-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e95e9-180">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-182">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="e95e9-182">List contents</span></span></p>
<p><span data-ttu-id="e95e9-183">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="e95e9-183">Read all properties</span></span></p>
<p><span data-ttu-id="e95e9-184">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="e95e9-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e95e9-185">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e95e9-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-187">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-188">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-189">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-190">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="e95e9-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="e95e9-191">Ler General-Information</span><span class="sxs-lookup"><span data-stu-id="e95e9-191">Read General-Information</span></span></p>
<p><span data-ttu-id="e95e9-192">Ler Personal-Information</span><span class="sxs-lookup"><span data-stu-id="e95e9-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="e95e9-193">Ler User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="e95e9-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="e95e9-194">Objetos de contato descendente</span><span class="sxs-lookup"><span data-stu-id="e95e9-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e95e9-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e95e9-196">Gravar RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-197">Gravar otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="e95e9-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="e95e9-198">Gravar displayName</span><span class="sxs-lookup"><span data-stu-id="e95e9-198">Write displayName</span></span></p>
<p><span data-ttu-id="e95e9-199">Descrição de gravação</span><span class="sxs-lookup"><span data-stu-id="e95e9-199">Write description</span></span></p>
<p><span data-ttu-id="e95e9-200">Gravar telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="e95e9-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="e95e9-201">Gravar msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="e95e9-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="e95e9-202">Gravar RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-203">Gravar RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-204">Gravar proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="e95e9-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e95e9-205">Objetos de contato descendente</span><span class="sxs-lookup"><span data-stu-id="e95e9-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="e95e9-206">Concedendo permissões para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="e95e9-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="e95e9-207">Ao executar o cmdlet **Grant-CsOuPermission** para objetos de Dispositivo em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e95e9-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="e95e9-208">Permissões concedidos para objetos de Dispositivo</span><span class="sxs-lookup"><span data-stu-id="e95e9-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e95e9-209">Grupo</span><span class="sxs-lookup"><span data-stu-id="e95e9-209">Group</span></span></th>
<th><span data-ttu-id="e95e9-210">Permissão</span><span class="sxs-lookup"><span data-stu-id="e95e9-210">Permission</span></span></th>
<th><span data-ttu-id="e95e9-211">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="e95e9-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e95e9-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e95e9-213">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="e95e9-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e95e9-214">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e95e9-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-216">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="e95e9-216">List contents</span></span></p>
<p><span data-ttu-id="e95e9-217">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="e95e9-217">Read all properties</span></span></p>
<p><span data-ttu-id="e95e9-218">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="e95e9-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e95e9-219">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-221">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="e95e9-221">List contents</span></span></p>
<p><span data-ttu-id="e95e9-222">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="e95e9-222">Read all properties</span></span></p>
<p><span data-ttu-id="e95e9-223">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="e95e9-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e95e9-224">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e95e9-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-226">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-227">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-228">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-229">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="e95e9-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="e95e9-230">Ler Personal-Information</span><span class="sxs-lookup"><span data-stu-id="e95e9-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="e95e9-231">Ler General-Information</span><span class="sxs-lookup"><span data-stu-id="e95e9-231">Read General-Information</span></span></p>
<p><span data-ttu-id="e95e9-232">Ler User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="e95e9-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="e95e9-233">Objetos de contato descendente</span><span class="sxs-lookup"><span data-stu-id="e95e9-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e95e9-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e95e9-235">Criar filho</span><span class="sxs-lookup"><span data-stu-id="e95e9-235">Create child</span></span></p>
<p><span data-ttu-id="e95e9-236">Excluir filho</span><span class="sxs-lookup"><span data-stu-id="e95e9-236">Delete child</span></span></p>
<p><span data-ttu-id="e95e9-237">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="e95e9-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="e95e9-238">Contato</span><span class="sxs-lookup"><span data-stu-id="e95e9-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e95e9-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e95e9-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e95e9-240">Gravar displayName</span><span class="sxs-lookup"><span data-stu-id="e95e9-240">Write displayName</span></span></p>
<p><span data-ttu-id="e95e9-241">Descrição de gravação</span><span class="sxs-lookup"><span data-stu-id="e95e9-241">Write description</span></span></p>
<p><span data-ttu-id="e95e9-242">Gravar telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="e95e9-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="e95e9-243">Objetos do usuário descendente</span><span class="sxs-lookup"><span data-stu-id="e95e9-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e95e9-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e95e9-245">Gravar RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-246">Gravar otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="e95e9-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="e95e9-247">Gravar displayName</span><span class="sxs-lookup"><span data-stu-id="e95e9-247">Write displayName</span></span></p>
<p><span data-ttu-id="e95e9-248">Descrição de gravação</span><span class="sxs-lookup"><span data-stu-id="e95e9-248">Write description</span></span></p>
<p><span data-ttu-id="e95e9-249">Gravar telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="e95e9-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="e95e9-250">Gravar msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="e95e9-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="e95e9-251">Gravar RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-252">Gravar RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-253">Gravar proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="e95e9-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e95e9-254">Objetos de contato descendente</span><span class="sxs-lookup"><span data-stu-id="e95e9-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="e95e9-255">Concedendo permissões para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="e95e9-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="e95e9-256">Ao executar o cmdlet **Grant-CsOuPermission** para objetos InetOrgPerson em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="e95e9-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="e95e9-257">Permissões concedidas para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="e95e9-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e95e9-258">Grupo</span><span class="sxs-lookup"><span data-stu-id="e95e9-258">Group</span></span></th>
<th><span data-ttu-id="e95e9-259">Permissão</span><span class="sxs-lookup"><span data-stu-id="e95e9-259">Permission</span></span></th>
<th><span data-ttu-id="e95e9-260">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="e95e9-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="e95e9-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="e95e9-262">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="e95e9-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="e95e9-263">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e95e9-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-265">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="e95e9-265">List contents</span></span></p>
<p><span data-ttu-id="e95e9-266">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="e95e9-266">Read all properties</span></span></p>
<p><span data-ttu-id="e95e9-267">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="e95e9-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e95e9-268">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-270">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="e95e9-270">List contents</span></span></p>
<p><span data-ttu-id="e95e9-271">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="e95e9-271">Read all properties</span></span></p>
<p><span data-ttu-id="e95e9-272">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="e95e9-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="e95e9-273">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="e95e9-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e95e9-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="e95e9-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="e95e9-275">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-276">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-277">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-278">Ler Personal-Information</span><span class="sxs-lookup"><span data-stu-id="e95e9-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="e95e9-279">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="e95e9-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="e95e9-280">Ler General-Information</span><span class="sxs-lookup"><span data-stu-id="e95e9-280">Read General-Information</span></span></p>
<p><span data-ttu-id="e95e9-281">Ler User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="e95e9-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="e95e9-282">Objetos inetOrgPerson descendentes</span><span class="sxs-lookup"><span data-stu-id="e95e9-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e95e9-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="e95e9-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="e95e9-284">Gravar RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-285">Gravar RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-286">Gravar RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="e95e9-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="e95e9-287">Gravar proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="e95e9-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="e95e9-288">Objetos inetOrgPerson descendentes</span><span class="sxs-lookup"><span data-stu-id="e95e9-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

