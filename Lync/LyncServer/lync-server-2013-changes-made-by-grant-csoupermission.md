---
title: 'Lync Server 2013: alterações feitas pela concessão-CsOUPermission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ce6b16dff48afeeec848024d763655695905008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="209b7-102">Alterações feitas pelo Grant-CsOUPermission no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="209b7-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="209b7-103">_**Tópico da última modificação:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="209b7-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="209b7-104">Para delegar a administração do Lync Server 2013, você pode adicionar permissões a unidades organizacionais (UOs) especificadas para que os membros dos grupos universais do RTC criados pela preparação da floresta possam acessar as UOs sem serem membros do grupo Domain admins.</span><span class="sxs-lookup"><span data-stu-id="209b7-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="209b7-105">O cmdlet **Grant-CsOuPermission** concede permissões a objetos na unidade organizacional especificada, conforme especificado nas tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="209b7-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="209b7-106">Concedendo permissão para objetos de usuário</span><span class="sxs-lookup"><span data-stu-id="209b7-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="209b7-107">Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de usuário em uma ou, os grupos recebem permissões para os grupos, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="209b7-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="209b7-108">Permissões concedidas para objetos de usuário</span><span class="sxs-lookup"><span data-stu-id="209b7-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="209b7-109">Grupos</span><span class="sxs-lookup"><span data-stu-id="209b7-109">Group</span></span></th>
<th><span data-ttu-id="209b7-110">Permissão</span><span class="sxs-lookup"><span data-stu-id="209b7-110">Permission</span></span></th>
<th><span data-ttu-id="209b7-111">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="209b7-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="209b7-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="209b7-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="209b7-113">Replicando alterações de diretório</span><span class="sxs-lookup"><span data-stu-id="209b7-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="209b7-114">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209b7-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-116">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="209b7-116">List contents</span></span></p>
<p><span data-ttu-id="209b7-117">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="209b7-117">Read all properties</span></span></p>
<p><span data-ttu-id="209b7-118">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="209b7-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="209b7-119">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209b7-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-121">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="209b7-121">List contents</span></span></p>
<p><span data-ttu-id="209b7-122">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="209b7-122">Read all properties</span></span></p>
<p><span data-ttu-id="209b7-123">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="209b7-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="209b7-124">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209b7-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-126">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="209b7-127">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="209b7-128">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="209b7-129">Ler informações públicas</span><span class="sxs-lookup"><span data-stu-id="209b7-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="209b7-130">Leia informações gerais</span><span class="sxs-lookup"><span data-stu-id="209b7-130">Read General-Information</span></span></p>
<p><span data-ttu-id="209b7-131">Ler restrições de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="209b7-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="209b7-132">Objetos de usuário descendentes</span><span class="sxs-lookup"><span data-stu-id="209b7-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209b7-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="209b7-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="209b7-134">Escrever RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="209b7-135">Escrever msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="209b7-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="209b7-136">Escrever RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="209b7-137">Escrever RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="209b7-138">Escrever proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="209b7-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="209b7-139">Objetos de usuário descendentes</span><span class="sxs-lookup"><span data-stu-id="209b7-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="209b7-140">Concedendo permissão para objetos de computador</span><span class="sxs-lookup"><span data-stu-id="209b7-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="209b7-141">Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de computador em uma ou, os grupos recebem permissões para os grupos, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="209b7-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="209b7-142">Permissões concedidas para objetos de computador</span><span class="sxs-lookup"><span data-stu-id="209b7-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="209b7-143">Grupos</span><span class="sxs-lookup"><span data-stu-id="209b7-143">Group</span></span></th>
<th><span data-ttu-id="209b7-144">Permissão</span><span class="sxs-lookup"><span data-stu-id="209b7-144">Permission</span></span></th>
<th><span data-ttu-id="209b7-145">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="209b7-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="209b7-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="209b7-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="209b7-147">Replicando alterações de diretório</span><span class="sxs-lookup"><span data-stu-id="209b7-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="209b7-148">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209b7-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-150">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="209b7-150">List contents</span></span></p>
<p><span data-ttu-id="209b7-151">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="209b7-151">Read all properties</span></span></p>
<p><span data-ttu-id="209b7-152">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="209b7-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="209b7-153">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209b7-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-155">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="209b7-155">List contents</span></span></p>
<p><span data-ttu-id="209b7-156">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="209b7-156">Read all properties</span></span></p>
<p><span data-ttu-id="209b7-157">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="209b7-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="209b7-158">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209b7-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-160">Ler informações públicas</span><span class="sxs-lookup"><span data-stu-id="209b7-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="209b7-161">Leitura validada-DNS-nome do host</span><span class="sxs-lookup"><span data-stu-id="209b7-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="209b7-162">Objetos de computador descendentes</span><span class="sxs-lookup"><span data-stu-id="209b7-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209b7-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="209b7-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="209b7-164">Ler informações públicas</span><span class="sxs-lookup"><span data-stu-id="209b7-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="209b7-165">Leitura validada-DNS-nome do host</span><span class="sxs-lookup"><span data-stu-id="209b7-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="209b7-166">Objetos de computador descendentes</span><span class="sxs-lookup"><span data-stu-id="209b7-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="209b7-167">Concedendo permissão para objetos de contato ou AppContact</span><span class="sxs-lookup"><span data-stu-id="209b7-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="209b7-168">Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de contato ou objetos AppContact em uma ou, os grupos recebem permissões como mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="209b7-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="209b7-169">Permissões concedidas para objetos de contato ou AppContact</span><span class="sxs-lookup"><span data-stu-id="209b7-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="209b7-170">Grupos</span><span class="sxs-lookup"><span data-stu-id="209b7-170">Group</span></span></th>
<th><span data-ttu-id="209b7-171">Permissão</span><span class="sxs-lookup"><span data-stu-id="209b7-171">Permission</span></span></th>
<th><span data-ttu-id="209b7-172">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="209b7-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="209b7-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="209b7-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="209b7-174">Replicando alterações de diretório</span><span class="sxs-lookup"><span data-stu-id="209b7-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="209b7-175">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209b7-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-177">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="209b7-177">List contents</span></span></p>
<p><span data-ttu-id="209b7-178">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="209b7-178">Read all properties</span></span></p>
<p><span data-ttu-id="209b7-179">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="209b7-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="209b7-180">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209b7-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-182">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="209b7-182">List contents</span></span></p>
<p><span data-ttu-id="209b7-183">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="209b7-183">Read all properties</span></span></p>
<p><span data-ttu-id="209b7-184">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="209b7-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="209b7-185">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209b7-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-187">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="209b7-188">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="209b7-189">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="209b7-190">Ler informações públicas</span><span class="sxs-lookup"><span data-stu-id="209b7-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="209b7-191">Leia informações gerais</span><span class="sxs-lookup"><span data-stu-id="209b7-191">Read General-Information</span></span></p>
<p><span data-ttu-id="209b7-192">Leia as informações pessoais</span><span class="sxs-lookup"><span data-stu-id="209b7-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="209b7-193">Ler restrições de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="209b7-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="209b7-194">Objetos de contato descendentes</span><span class="sxs-lookup"><span data-stu-id="209b7-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209b7-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="209b7-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="209b7-196">Escrever RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="209b7-197">Escrever otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="209b7-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="209b7-198">Escrever displayName</span><span class="sxs-lookup"><span data-stu-id="209b7-198">Write displayName</span></span></p>
<p><span data-ttu-id="209b7-199">Descrição da gravação</span><span class="sxs-lookup"><span data-stu-id="209b7-199">Write description</span></span></p>
<p><span data-ttu-id="209b7-200">Escrever telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="209b7-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="209b7-201">Escrever msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="209b7-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="209b7-202">Escrever RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="209b7-203">Escrever RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="209b7-204">Escrever proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="209b7-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="209b7-205">Objetos de contato descendentes</span><span class="sxs-lookup"><span data-stu-id="209b7-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="209b7-206">Concedendo permissão para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="209b7-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="209b7-207">Quando você executa o cmdlet **Grant-CsOuPermission** para objetos de dispositivo em uma ou, os grupos recebem permissões como mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="209b7-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="209b7-208">Permissões concedidas para objetos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="209b7-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="209b7-209">Grupos</span><span class="sxs-lookup"><span data-stu-id="209b7-209">Group</span></span></th>
<th><span data-ttu-id="209b7-210">Permissão</span><span class="sxs-lookup"><span data-stu-id="209b7-210">Permission</span></span></th>
<th><span data-ttu-id="209b7-211">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="209b7-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="209b7-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="209b7-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="209b7-213">Replicando alterações de diretório</span><span class="sxs-lookup"><span data-stu-id="209b7-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="209b7-214">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209b7-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-216">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="209b7-216">List contents</span></span></p>
<p><span data-ttu-id="209b7-217">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="209b7-217">Read all properties</span></span></p>
<p><span data-ttu-id="209b7-218">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="209b7-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="209b7-219">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209b7-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-221">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="209b7-221">List contents</span></span></p>
<p><span data-ttu-id="209b7-222">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="209b7-222">Read all properties</span></span></p>
<p><span data-ttu-id="209b7-223">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="209b7-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="209b7-224">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209b7-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-226">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="209b7-227">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="209b7-228">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="209b7-229">Ler informações públicas</span><span class="sxs-lookup"><span data-stu-id="209b7-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="209b7-230">Leia as informações pessoais</span><span class="sxs-lookup"><span data-stu-id="209b7-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="209b7-231">Leia informações gerais</span><span class="sxs-lookup"><span data-stu-id="209b7-231">Read General-Information</span></span></p>
<p><span data-ttu-id="209b7-232">Ler restrições de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="209b7-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="209b7-233">Objetos de contato descendentes</span><span class="sxs-lookup"><span data-stu-id="209b7-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209b7-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="209b7-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="209b7-235">Criar filho</span><span class="sxs-lookup"><span data-stu-id="209b7-235">Create child</span></span></p>
<p><span data-ttu-id="209b7-236">Excluir filho</span><span class="sxs-lookup"><span data-stu-id="209b7-236">Delete child</span></span></p>
<p><span data-ttu-id="209b7-237">Excluir árvore</span><span class="sxs-lookup"><span data-stu-id="209b7-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="209b7-238">Entrando</span><span class="sxs-lookup"><span data-stu-id="209b7-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209b7-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="209b7-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="209b7-240">Escrever displayName</span><span class="sxs-lookup"><span data-stu-id="209b7-240">Write displayName</span></span></p>
<p><span data-ttu-id="209b7-241">Descrição da gravação</span><span class="sxs-lookup"><span data-stu-id="209b7-241">Write description</span></span></p>
<p><span data-ttu-id="209b7-242">Escrever telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="209b7-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="209b7-243">Objetos de usuário descendentes</span><span class="sxs-lookup"><span data-stu-id="209b7-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209b7-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="209b7-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="209b7-245">Escrever RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="209b7-246">Escrever otherIpPhone</span><span class="sxs-lookup"><span data-stu-id="209b7-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="209b7-247">Escrever displayName</span><span class="sxs-lookup"><span data-stu-id="209b7-247">Write displayName</span></span></p>
<p><span data-ttu-id="209b7-248">Descrição da gravação</span><span class="sxs-lookup"><span data-stu-id="209b7-248">Write description</span></span></p>
<p><span data-ttu-id="209b7-249">Escrever telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="209b7-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="209b7-250">Escrever msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="209b7-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="209b7-251">Escrever RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="209b7-252">Escrever RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="209b7-253">Escrever proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="209b7-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="209b7-254">Objetos de contato descendentes</span><span class="sxs-lookup"><span data-stu-id="209b7-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="209b7-255">Concedendo permissão para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="209b7-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="209b7-256">Quando você executa o cmdlet **Grant-CsOuPermission** para objetos inetOrgPerson em uma ou, os grupos recebem permissões como mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="209b7-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="209b7-257">Permissões concedidas para objetos InetOrgPerson</span><span class="sxs-lookup"><span data-stu-id="209b7-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="209b7-258">Grupos</span><span class="sxs-lookup"><span data-stu-id="209b7-258">Group</span></span></th>
<th><span data-ttu-id="209b7-259">Permissão</span><span class="sxs-lookup"><span data-stu-id="209b7-259">Permission</span></span></th>
<th><span data-ttu-id="209b7-260">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="209b7-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="209b7-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="209b7-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="209b7-262">Replicando alterações de diretório</span><span class="sxs-lookup"><span data-stu-id="209b7-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="209b7-263">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209b7-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-265">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="209b7-265">List contents</span></span></p>
<p><span data-ttu-id="209b7-266">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="209b7-266">Read all properties</span></span></p>
<p><span data-ttu-id="209b7-267">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="209b7-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="209b7-268">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209b7-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-270">Conteúdo da lista</span><span class="sxs-lookup"><span data-stu-id="209b7-270">List contents</span></span></p>
<p><span data-ttu-id="209b7-271">Ler todas as propriedades</span><span class="sxs-lookup"><span data-stu-id="209b7-271">Read all properties</span></span></p>
<p><span data-ttu-id="209b7-272">Permissões de leitura</span><span class="sxs-lookup"><span data-stu-id="209b7-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="209b7-273">Somente este objeto</span><span class="sxs-lookup"><span data-stu-id="209b7-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="209b7-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="209b7-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="209b7-275">Ler RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="209b7-276">Ler RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="209b7-277">Ler RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="209b7-278">Leia as informações pessoais</span><span class="sxs-lookup"><span data-stu-id="209b7-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="209b7-279">Ler informações públicas</span><span class="sxs-lookup"><span data-stu-id="209b7-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="209b7-280">Leia informações gerais</span><span class="sxs-lookup"><span data-stu-id="209b7-280">Read General-Information</span></span></p>
<p><span data-ttu-id="209b7-281">Ler restrições de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="209b7-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="209b7-282">Objetos inetOrgPerson descendentes</span><span class="sxs-lookup"><span data-stu-id="209b7-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="209b7-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="209b7-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="209b7-284">Escrever RTCUserSearchPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="209b7-285">Escrever RTCUserProvisioningPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="209b7-286">Escrever RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="209b7-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="209b7-287">Escrever proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="209b7-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="209b7-288">Objetos inetOrgPerson descendentes</span><span class="sxs-lookup"><span data-stu-id="209b7-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

