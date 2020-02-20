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
ms.openlocfilehash: c64c11ba999763a44105a68502e53fc4889af305
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="058ad-102">Alterações feitas pelo Grant-CsOUPermission no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="058ad-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="058ad-103">_**Última modificação do tópico:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="058ad-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="058ad-104">Para delegar a administração do Lync Server 2013, você pode adicionar permissões a unidades organizacionais (UOs) especificadas para que os membros dos grupos universais RTC criados pela preparação da floresta possam acessar as UOs sem ser membros do grupo Administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="058ad-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="058ad-105">O cmdlet **Grant-CsOuPermission** concede permissões para objetos no OU especificado conforme mostrado nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="058ad-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="058ad-106">Concedendo permissões para objetos do usuário</span><span class="sxs-lookup"><span data-stu-id="058ad-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="058ad-107">Ao executar o cmdlet **Grant-CsOuPermission** para objetos do Usuário em um OU, os grupos são concedidos com permissões exibidas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="058ad-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="058ad-108">Permissões concedidas para objetos do usuário</span><span class="sxs-lookup"><span data-stu-id="058ad-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="058ad-109">Grupo</span><span class="sxs-lookup"><span data-stu-id="058ad-109">Group</span></span></th>
<th><span data-ttu-id="058ad-110">Permissão</span><span class="sxs-lookup"><span data-stu-id="058ad-110">Permission</span></span></th>
<th><span data-ttu-id="058ad-111">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="058ad-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="058ad-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="058ad-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="058ad-113">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="058ad-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="058ad-114">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="058ad-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-116">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="058ad-116">List contents</span></span></p>
<p><span data-ttu-id="058ad-117">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="058ad-117">Read all properties</span></span></p>
<p><span data-ttu-id="058ad-118">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="058ad-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="058ad-119">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="058ad-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-121">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="058ad-121">List contents</span></span></p>
<p><span data-ttu-id="058ad-122">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="058ad-122">Read all properties</span></span></p>
<p><span data-ttu-id="058ad-123">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="058ad-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="058ad-124">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="058ad-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-126">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="058ad-127">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="058ad-128">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="058ad-129">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="058ad-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="058ad-130">Ler General-Information</span><span class="sxs-lookup"><span data-stu-id="058ad-130">Read General-Information</span></span></p>
<p><span data-ttu-id="058ad-131">Ler User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="058ad-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="058ad-132">Objetos do usuário descendente</span><span class="sxs-lookup"><span data-stu-id="058ad-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="058ad-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="058ad-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="058ad-134">Gravara RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="058ad-135">Gravar msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="058ad-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="058ad-136">Gravar RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="058ad-137">Gravar RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="058ad-138">Gravar proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="058ad-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="058ad-139">Objetos do usuário descendente</span><span class="sxs-lookup"><span data-stu-id="058ad-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="058ad-140">Conceder permissões para objetos do computador</span><span class="sxs-lookup"><span data-stu-id="058ad-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="058ad-141">Ao executar o cmdlet **Grant-CsOuPermission** para objetos de computador em um OU, os grupos são concedidos com as permissões mostradas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="058ad-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="058ad-142">Permissões concedidas para objetos do computador</span><span class="sxs-lookup"><span data-stu-id="058ad-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="058ad-143">Grupo</span><span class="sxs-lookup"><span data-stu-id="058ad-143">Group</span></span></th>
<th><span data-ttu-id="058ad-144">Permissão</span><span class="sxs-lookup"><span data-stu-id="058ad-144">Permission</span></span></th>
<th><span data-ttu-id="058ad-145">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="058ad-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="058ad-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="058ad-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="058ad-147">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="058ad-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="058ad-148">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="058ad-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-150">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="058ad-150">List contents</span></span></p>
<p><span data-ttu-id="058ad-151">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="058ad-151">Read all properties</span></span></p>
<p><span data-ttu-id="058ad-152">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="058ad-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="058ad-153">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="058ad-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-155">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="058ad-155">List contents</span></span></p>
<p><span data-ttu-id="058ad-156">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="058ad-156">Read all properties</span></span></p>
<p><span data-ttu-id="058ad-157">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="058ad-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="058ad-158">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="058ad-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-160">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="058ad-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="058ad-161">Ler Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="058ad-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="058ad-162">Objetos do computador descendente</span><span class="sxs-lookup"><span data-stu-id="058ad-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="058ad-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="058ad-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="058ad-164">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="058ad-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="058ad-165">Ler Validated-DNS-Host-Name</span><span class="sxs-lookup"><span data-stu-id="058ad-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="058ad-166">Objetos do computador descendente</span><span class="sxs-lookup"><span data-stu-id="058ad-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="058ad-167">Concedendo permissões para contato ou objetos AppContact</span><span class="sxs-lookup"><span data-stu-id="058ad-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="058ad-168">Ao executar o cmdlet **Grant-CsOuPermission** para objetos de Contato ou AppContact em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="058ad-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="058ad-169">Permissões concedidas para os objetos Contato ou AppContact</span><span class="sxs-lookup"><span data-stu-id="058ad-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="058ad-170">Grupo</span><span class="sxs-lookup"><span data-stu-id="058ad-170">Group</span></span></th>
<th><span data-ttu-id="058ad-171">Permissão</span><span class="sxs-lookup"><span data-stu-id="058ad-171">Permission</span></span></th>
<th><span data-ttu-id="058ad-172">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="058ad-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="058ad-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="058ad-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="058ad-174">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="058ad-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="058ad-175">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="058ad-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-177">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="058ad-177">List contents</span></span></p>
<p><span data-ttu-id="058ad-178">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="058ad-178">Read all properties</span></span></p>
<p><span data-ttu-id="058ad-179">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="058ad-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="058ad-180">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="058ad-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-182">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="058ad-182">List contents</span></span></p>
<p><span data-ttu-id="058ad-183">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="058ad-183">Read all properties</span></span></p>
<p><span data-ttu-id="058ad-184">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="058ad-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="058ad-185">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="058ad-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-187">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="058ad-188">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="058ad-189">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="058ad-190">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="058ad-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="058ad-191">Ler General-Information</span><span class="sxs-lookup"><span data-stu-id="058ad-191">Read General-Information</span></span></p>
<p><span data-ttu-id="058ad-192">Ler Personal-Information</span><span class="sxs-lookup"><span data-stu-id="058ad-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="058ad-193">Ler User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="058ad-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="058ad-194">Objetos de contato descendente</span><span class="sxs-lookup"><span data-stu-id="058ad-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="058ad-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="058ad-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="058ad-196">Gravar RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="058ad-197">Gravar otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="058ad-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="058ad-198">Gravar displayName</span><span class="sxs-lookup"><span data-stu-id="058ad-198">Write displayName</span></span></p>
<p><span data-ttu-id="058ad-199">Descrição de gravação</span><span class="sxs-lookup"><span data-stu-id="058ad-199">Write description</span></span></p>
<p><span data-ttu-id="058ad-200">Gravar telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="058ad-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="058ad-201">Gravar msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="058ad-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="058ad-202">Gravar RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="058ad-203">Gravar RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="058ad-204">Gravar proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="058ad-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="058ad-205">Objetos de contato descendente</span><span class="sxs-lookup"><span data-stu-id="058ad-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="058ad-206">Concedendo permissões para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="058ad-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="058ad-207">Ao executar o cmdlet **Grant-CsOuPermission** para objetos de Dispositivo em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="058ad-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="058ad-208">Permissões concedidos para objetos de Dispositivo</span><span class="sxs-lookup"><span data-stu-id="058ad-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="058ad-209">Grupo</span><span class="sxs-lookup"><span data-stu-id="058ad-209">Group</span></span></th>
<th><span data-ttu-id="058ad-210">Permissão</span><span class="sxs-lookup"><span data-stu-id="058ad-210">Permission</span></span></th>
<th><span data-ttu-id="058ad-211">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="058ad-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="058ad-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="058ad-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="058ad-213">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="058ad-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="058ad-214">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="058ad-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-216">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="058ad-216">List contents</span></span></p>
<p><span data-ttu-id="058ad-217">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="058ad-217">Read all properties</span></span></p>
<p><span data-ttu-id="058ad-218">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="058ad-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="058ad-219">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="058ad-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-221">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="058ad-221">List contents</span></span></p>
<p><span data-ttu-id="058ad-222">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="058ad-222">Read all properties</span></span></p>
<p><span data-ttu-id="058ad-223">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="058ad-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="058ad-224">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="058ad-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-226">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="058ad-227">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="058ad-228">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="058ad-229">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="058ad-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="058ad-230">Ler Personal-Information</span><span class="sxs-lookup"><span data-stu-id="058ad-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="058ad-231">Ler General-Information</span><span class="sxs-lookup"><span data-stu-id="058ad-231">Read General-Information</span></span></p>
<p><span data-ttu-id="058ad-232">Ler User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="058ad-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="058ad-233">Objetos de contato descendente</span><span class="sxs-lookup"><span data-stu-id="058ad-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="058ad-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="058ad-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="058ad-235">Criar filho</span><span class="sxs-lookup"><span data-stu-id="058ad-235">Create child</span></span></p>
<p><span data-ttu-id="058ad-236">Excluir filho</span><span class="sxs-lookup"><span data-stu-id="058ad-236">Delete child</span></span></p>
<p><span data-ttu-id="058ad-237">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="058ad-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="058ad-238">Contato</span><span class="sxs-lookup"><span data-stu-id="058ad-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="058ad-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="058ad-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="058ad-240">Gravar displayName</span><span class="sxs-lookup"><span data-stu-id="058ad-240">Write displayName</span></span></p>
<p><span data-ttu-id="058ad-241">Descrição de gravação</span><span class="sxs-lookup"><span data-stu-id="058ad-241">Write description</span></span></p>
<p><span data-ttu-id="058ad-242">Gravar telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="058ad-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="058ad-243">Objetos do usuário descendente</span><span class="sxs-lookup"><span data-stu-id="058ad-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="058ad-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="058ad-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="058ad-245">Gravar RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="058ad-246">Gravar otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="058ad-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="058ad-247">Gravar displayName</span><span class="sxs-lookup"><span data-stu-id="058ad-247">Write displayName</span></span></p>
<p><span data-ttu-id="058ad-248">Descrição de gravação</span><span class="sxs-lookup"><span data-stu-id="058ad-248">Write description</span></span></p>
<p><span data-ttu-id="058ad-249">Gravar telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="058ad-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="058ad-250">Gravar msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="058ad-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="058ad-251">Gravar RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="058ad-252">Gravar RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="058ad-253">Gravar proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="058ad-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="058ad-254">Objetos de contato descendente</span><span class="sxs-lookup"><span data-stu-id="058ad-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="058ad-255">Concedendo permissões para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="058ad-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="058ad-256">Ao executar o cmdlet **Grant-CsOuPermission** para objetos InetOrgPerson em um OU, os grupos são concedidos com permissões conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="058ad-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="058ad-257">Permissões concedidas para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="058ad-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="058ad-258">Grupo</span><span class="sxs-lookup"><span data-stu-id="058ad-258">Group</span></span></th>
<th><span data-ttu-id="058ad-259">Permissão</span><span class="sxs-lookup"><span data-stu-id="058ad-259">Permission</span></span></th>
<th><span data-ttu-id="058ad-260">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="058ad-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="058ad-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="058ad-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="058ad-262">Replicando mudanças de diretório</span><span class="sxs-lookup"><span data-stu-id="058ad-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="058ad-263">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="058ad-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-265">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="058ad-265">List contents</span></span></p>
<p><span data-ttu-id="058ad-266">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="058ad-266">Read all properties</span></span></p>
<p><span data-ttu-id="058ad-267">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="058ad-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="058ad-268">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="058ad-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-270">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="058ad-270">List contents</span></span></p>
<p><span data-ttu-id="058ad-271">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="058ad-271">Read all properties</span></span></p>
<p><span data-ttu-id="058ad-272">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="058ad-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="058ad-273">Apenas este objeto</span><span class="sxs-lookup"><span data-stu-id="058ad-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="058ad-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="058ad-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="058ad-275">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="058ad-276">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="058ad-277">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="058ad-278">Ler Personal-Information</span><span class="sxs-lookup"><span data-stu-id="058ad-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="058ad-279">Ler Public-Information</span><span class="sxs-lookup"><span data-stu-id="058ad-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="058ad-280">Ler General-Information</span><span class="sxs-lookup"><span data-stu-id="058ad-280">Read General-Information</span></span></p>
<p><span data-ttu-id="058ad-281">Ler User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="058ad-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="058ad-282">Objetos inetOrgPerson descendentes</span><span class="sxs-lookup"><span data-stu-id="058ad-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="058ad-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="058ad-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="058ad-284">Gravar RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="058ad-285">Gravar RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="058ad-286">Gravar RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="058ad-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="058ad-287">Gravar proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="058ad-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="058ad-288">Objetos inetOrgPerson descendentes</span><span class="sxs-lookup"><span data-stu-id="058ad-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

