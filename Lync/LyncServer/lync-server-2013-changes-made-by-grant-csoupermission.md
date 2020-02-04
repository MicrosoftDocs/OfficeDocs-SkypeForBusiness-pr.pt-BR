---
title: 'Lync Server 2013: alterações feitas pela concessão-CsOUPermission'
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
ms.openlocfilehash: 9056753e57f57b131a05d13eb2862611ba34f966
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="9346a-102">Alterações feitas pelo Grant-CsOUPermission no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9346a-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9346a-103">_**Tópico da última modificação:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="9346a-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="9346a-104">Para delegar a administração do Lync Server 2013, você pode adicionar permissões a unidades organizacionais (UOs) especificadas para que os membros dos grupos universais do RTC criados pela preparação da floresta possam acessar as UOs sem serem membros do grupo Domain admins.</span><span class="sxs-lookup"><span data-stu-id="9346a-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="9346a-105">O cmdlet **Grant-CsOuPermission** concede permissões a objetos na unidade organizacional especificada, conforme especificado nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="9346a-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="9346a-106">Concedendo permissão para objetos de usuário</span><span class="sxs-lookup"><span data-stu-id="9346a-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="9346a-107">Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de usuário em uma ou, os grupos recebem permissões para os grupos, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9346a-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="9346a-108">Permissões concedidas para objetos de usuário</span><span class="sxs-lookup"><span data-stu-id="9346a-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9346a-109">Grupos</span><span class="sxs-lookup"><span data-stu-id="9346a-109">Group</span></span></th>
<th><span data-ttu-id="9346a-110">Permissão</span><span class="sxs-lookup"><span data-stu-id="9346a-110">Permission</span></span></th>
<th><span data-ttu-id="9346a-111">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="9346a-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9346a-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9346a-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9346a-113">Replicando alterações de diretório</span><span class="sxs-lookup"><span data-stu-id="9346a-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9346a-114">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9346a-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-116">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="9346a-116">List contents</span></span></p>
<p><span data-ttu-id="9346a-117">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="9346a-117">Read all properties</span></span></p>
<p><span data-ttu-id="9346a-118">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="9346a-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9346a-119">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9346a-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-121">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="9346a-121">List contents</span></span></p>
<p><span data-ttu-id="9346a-122">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="9346a-122">Read all properties</span></span></p>
<p><span data-ttu-id="9346a-123">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="9346a-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9346a-124">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9346a-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-126">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9346a-127">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9346a-128">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="9346a-129">Ler informações públicas</span><span class="sxs-lookup"><span data-stu-id="9346a-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="9346a-130">Leia informações gerais</span><span class="sxs-lookup"><span data-stu-id="9346a-130">Read General-Information</span></span></p>
<p><span data-ttu-id="9346a-131">Ler restrições de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="9346a-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="9346a-132">Objetos de usuário descendentes</span><span class="sxs-lookup"><span data-stu-id="9346a-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9346a-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9346a-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9346a-134">Escrever RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9346a-135">Escrever msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="9346a-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="9346a-136">Escrever RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9346a-137">Escrever RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="9346a-138">Escrever proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9346a-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="9346a-139">Objetos de usuário descendentes</span><span class="sxs-lookup"><span data-stu-id="9346a-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="9346a-140">Concedendo permissão para objetos de computador</span><span class="sxs-lookup"><span data-stu-id="9346a-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="9346a-141">Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de computador em uma ou, os grupos recebem permissões para os grupos, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9346a-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="9346a-142">Permissões concedidas para objetos de computador</span><span class="sxs-lookup"><span data-stu-id="9346a-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9346a-143">Grupos</span><span class="sxs-lookup"><span data-stu-id="9346a-143">Group</span></span></th>
<th><span data-ttu-id="9346a-144">Permissão</span><span class="sxs-lookup"><span data-stu-id="9346a-144">Permission</span></span></th>
<th><span data-ttu-id="9346a-145">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="9346a-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9346a-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9346a-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9346a-147">Replicando alterações de diretório</span><span class="sxs-lookup"><span data-stu-id="9346a-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9346a-148">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9346a-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-150">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="9346a-150">List contents</span></span></p>
<p><span data-ttu-id="9346a-151">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="9346a-151">Read all properties</span></span></p>
<p><span data-ttu-id="9346a-152">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="9346a-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9346a-153">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9346a-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-155">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="9346a-155">List contents</span></span></p>
<p><span data-ttu-id="9346a-156">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="9346a-156">Read all properties</span></span></p>
<p><span data-ttu-id="9346a-157">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="9346a-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9346a-158">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9346a-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-160">Ler informações públicas</span><span class="sxs-lookup"><span data-stu-id="9346a-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="9346a-161">Leitura validada-DNS-nome do host</span><span class="sxs-lookup"><span data-stu-id="9346a-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="9346a-162">Objetos de computador descendentes</span><span class="sxs-lookup"><span data-stu-id="9346a-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9346a-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9346a-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9346a-164">Ler informações públicas</span><span class="sxs-lookup"><span data-stu-id="9346a-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="9346a-165">Leitura validada-DNS-nome do host</span><span class="sxs-lookup"><span data-stu-id="9346a-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="9346a-166">Objetos de computador descendentes</span><span class="sxs-lookup"><span data-stu-id="9346a-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="9346a-167">Concedendo permissão para objetos de contato ou AppContact</span><span class="sxs-lookup"><span data-stu-id="9346a-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="9346a-168">Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de contato ou objetos AppContact em uma ou, os grupos recebem permissões como mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9346a-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="9346a-169">Permissões concedidas para objetos de contato ou AppContact</span><span class="sxs-lookup"><span data-stu-id="9346a-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9346a-170">Grupos</span><span class="sxs-lookup"><span data-stu-id="9346a-170">Group</span></span></th>
<th><span data-ttu-id="9346a-171">Permissão</span><span class="sxs-lookup"><span data-stu-id="9346a-171">Permission</span></span></th>
<th><span data-ttu-id="9346a-172">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="9346a-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9346a-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9346a-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9346a-174">Replicando alterações de diretório</span><span class="sxs-lookup"><span data-stu-id="9346a-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9346a-175">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9346a-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-177">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="9346a-177">List contents</span></span></p>
<p><span data-ttu-id="9346a-178">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="9346a-178">Read all properties</span></span></p>
<p><span data-ttu-id="9346a-179">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="9346a-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9346a-180">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9346a-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-182">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="9346a-182">List contents</span></span></p>
<p><span data-ttu-id="9346a-183">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="9346a-183">Read all properties</span></span></p>
<p><span data-ttu-id="9346a-184">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="9346a-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9346a-185">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9346a-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-187">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9346a-188">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9346a-189">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="9346a-190">Ler informações públicas</span><span class="sxs-lookup"><span data-stu-id="9346a-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="9346a-191">Leia informações gerais</span><span class="sxs-lookup"><span data-stu-id="9346a-191">Read General-Information</span></span></p>
<p><span data-ttu-id="9346a-192">Leia as informações pessoais</span><span class="sxs-lookup"><span data-stu-id="9346a-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="9346a-193">Ler restrições de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="9346a-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="9346a-194">Objetos de contato descendentes</span><span class="sxs-lookup"><span data-stu-id="9346a-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9346a-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9346a-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9346a-196">Escrever RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9346a-197">Escrever otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="9346a-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="9346a-198">Escrever displayName</span><span class="sxs-lookup"><span data-stu-id="9346a-198">Write displayName</span></span></p>
<p><span data-ttu-id="9346a-199">Descrição da gravação</span><span class="sxs-lookup"><span data-stu-id="9346a-199">Write description</span></span></p>
<p><span data-ttu-id="9346a-200">Escrever telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="9346a-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="9346a-201">Escrever msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="9346a-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="9346a-202">Escrever RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9346a-203">Escrever RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="9346a-204">Escrever proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9346a-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="9346a-205">Objetos de contato descendentes</span><span class="sxs-lookup"><span data-stu-id="9346a-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="9346a-206">Concedendo permissão para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="9346a-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="9346a-207">Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de dispositivo em uma ou, os grupos recebem permissões como mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9346a-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="9346a-208">Permissões concedidas para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="9346a-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9346a-209">Grupos</span><span class="sxs-lookup"><span data-stu-id="9346a-209">Group</span></span></th>
<th><span data-ttu-id="9346a-210">Permissão</span><span class="sxs-lookup"><span data-stu-id="9346a-210">Permission</span></span></th>
<th><span data-ttu-id="9346a-211">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="9346a-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9346a-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9346a-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9346a-213">Replicando alterações de diretório</span><span class="sxs-lookup"><span data-stu-id="9346a-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9346a-214">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9346a-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-216">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="9346a-216">List contents</span></span></p>
<p><span data-ttu-id="9346a-217">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="9346a-217">Read all properties</span></span></p>
<p><span data-ttu-id="9346a-218">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="9346a-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9346a-219">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9346a-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-221">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="9346a-221">List contents</span></span></p>
<p><span data-ttu-id="9346a-222">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="9346a-222">Read all properties</span></span></p>
<p><span data-ttu-id="9346a-223">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="9346a-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9346a-224">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9346a-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-226">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9346a-227">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9346a-228">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="9346a-229">Ler informações públicas</span><span class="sxs-lookup"><span data-stu-id="9346a-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="9346a-230">Leia as informações pessoais</span><span class="sxs-lookup"><span data-stu-id="9346a-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="9346a-231">Leia informações gerais</span><span class="sxs-lookup"><span data-stu-id="9346a-231">Read General-Information</span></span></p>
<p><span data-ttu-id="9346a-232">Ler restrições de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="9346a-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="9346a-233">Objetos de contato descendentes</span><span class="sxs-lookup"><span data-stu-id="9346a-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9346a-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9346a-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9346a-235">Criar filho</span><span class="sxs-lookup"><span data-stu-id="9346a-235">Create child</span></span></p>
<p><span data-ttu-id="9346a-236">Excluir filho</span><span class="sxs-lookup"><span data-stu-id="9346a-236">Delete child</span></span></p>
<p><span data-ttu-id="9346a-237">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="9346a-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="9346a-238">Entrando</span><span class="sxs-lookup"><span data-stu-id="9346a-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9346a-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9346a-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9346a-240">Escrever displayName</span><span class="sxs-lookup"><span data-stu-id="9346a-240">Write displayName</span></span></p>
<p><span data-ttu-id="9346a-241">Descrição da gravação</span><span class="sxs-lookup"><span data-stu-id="9346a-241">Write description</span></span></p>
<p><span data-ttu-id="9346a-242">Escrever telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="9346a-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="9346a-243">Objetos de usuário descendentes</span><span class="sxs-lookup"><span data-stu-id="9346a-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9346a-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9346a-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9346a-245">Escrever RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9346a-246">Escrever otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="9346a-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="9346a-247">Escrever displayName</span><span class="sxs-lookup"><span data-stu-id="9346a-247">Write displayName</span></span></p>
<p><span data-ttu-id="9346a-248">Descrição da gravação</span><span class="sxs-lookup"><span data-stu-id="9346a-248">Write description</span></span></p>
<p><span data-ttu-id="9346a-249">Escrever telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="9346a-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="9346a-250">Escrever msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="9346a-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="9346a-251">Escrever RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9346a-252">Escrever RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="9346a-253">Escrever proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9346a-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="9346a-254">Objetos de contato descendentes</span><span class="sxs-lookup"><span data-stu-id="9346a-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="9346a-255">Concedendo permissão para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="9346a-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="9346a-256">Quando você executa o cmdlet **Grant-CsOuPermission** para objetos inetOrgPerson em uma ou, os grupos recebem permissões como mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9346a-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="9346a-257">Permissões concedidas para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="9346a-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9346a-258">Grupos</span><span class="sxs-lookup"><span data-stu-id="9346a-258">Group</span></span></th>
<th><span data-ttu-id="9346a-259">Permissão</span><span class="sxs-lookup"><span data-stu-id="9346a-259">Permission</span></span></th>
<th><span data-ttu-id="9346a-260">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="9346a-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9346a-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="9346a-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="9346a-262">Replicando alterações de diretório</span><span class="sxs-lookup"><span data-stu-id="9346a-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="9346a-263">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9346a-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-265">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="9346a-265">List contents</span></span></p>
<p><span data-ttu-id="9346a-266">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="9346a-266">Read all properties</span></span></p>
<p><span data-ttu-id="9346a-267">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="9346a-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9346a-268">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9346a-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-270">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="9346a-270">List contents</span></span></p>
<p><span data-ttu-id="9346a-271">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="9346a-271">Read all properties</span></span></p>
<p><span data-ttu-id="9346a-272">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="9346a-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="9346a-273">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="9346a-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9346a-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="9346a-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="9346a-275">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9346a-276">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9346a-277">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="9346a-278">Leia as informações pessoais</span><span class="sxs-lookup"><span data-stu-id="9346a-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="9346a-279">Ler informações públicas</span><span class="sxs-lookup"><span data-stu-id="9346a-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="9346a-280">Leia informações gerais</span><span class="sxs-lookup"><span data-stu-id="9346a-280">Read General-Information</span></span></p>
<p><span data-ttu-id="9346a-281">Ler restrições de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="9346a-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="9346a-282">Objetos inetOrgPerson descendentes</span><span class="sxs-lookup"><span data-stu-id="9346a-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9346a-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="9346a-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="9346a-284">Escrever RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="9346a-285">Escrever RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="9346a-286">Escrever RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9346a-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="9346a-287">Escrever proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="9346a-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="9346a-288">Objetos inetOrgPerson descendentes</span><span class="sxs-lookup"><span data-stu-id="9346a-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

