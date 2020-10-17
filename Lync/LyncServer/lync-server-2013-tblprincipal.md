---
title: 'Lync Server 2013: tblPrincipal'
description: 'Lync Server 2013: tblPrincipal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f07b37ac4c8ceed5c044b5c263eeee6370adfdc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547487"
---
# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="11c20-103">tblPrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11c20-103">tblPrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11c20-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="11c20-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="11c20-105">tblPrincipal contém todas as entidades, incluindo usuários, pastas e grupos.</span><span class="sxs-lookup"><span data-stu-id="11c20-105">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="11c20-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="11c20-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11c20-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="11c20-107">Column</span></span></th>
<th><span data-ttu-id="11c20-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="11c20-108">Type</span></span></th>
<th><span data-ttu-id="11c20-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="11c20-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11c20-110">prinID</span><span class="sxs-lookup"><span data-stu-id="11c20-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="11c20-111">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="11c20-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="11c20-112">ID principal.</span><span class="sxs-lookup"><span data-stu-id="11c20-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11c20-113">prinGuid</span><span class="sxs-lookup"><span data-stu-id="11c20-113">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="11c20-114">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="11c20-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="11c20-115">GUID da entidade.</span><span class="sxs-lookup"><span data-stu-id="11c20-115">Principal GUID.</span></span> <span data-ttu-id="11c20-116">Isso é amplamente usado como uma chave primária alternativa, pois o significado é cruzado no espaço dos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="11c20-116">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="11c20-117">(O GUID de uma entidade em cache é igual ao GUID de objeto correspondente no Active Directory).</span><span class="sxs-lookup"><span data-stu-id="11c20-117">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11c20-118">prinUri</span><span class="sxs-lookup"><span data-stu-id="11c20-118">prinUri</span></span></p></td>
<td><p><span data-ttu-id="11c20-119">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="11c20-119">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="11c20-p102">URI de entidade. O esquema do SIP é usado para usuários e o ma-grp é usado para quase tudo.</span><span class="sxs-lookup"><span data-stu-id="11c20-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11c20-122">imprimir</span><span class="sxs-lookup"><span data-stu-id="11c20-122">prinName</span></span></p></td>
<td><p><span data-ttu-id="11c20-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11c20-123">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="11c20-p103">Nome comum. Usado apenas por tipos de usuário.</span><span class="sxs-lookup"><span data-stu-id="11c20-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11c20-126">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="11c20-126">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="11c20-127">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11c20-127">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="11c20-p104">Nome de exibição. Usado somente pelos tipos de usuário.</span><span class="sxs-lookup"><span data-stu-id="11c20-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11c20-130">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="11c20-130">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="11c20-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11c20-131">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="11c20-p105">Nome da empresa. Usado somente pelos tipos de usuário.</span><span class="sxs-lookup"><span data-stu-id="11c20-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11c20-134">prinEmail</span><span class="sxs-lookup"><span data-stu-id="11c20-134">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="11c20-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11c20-135">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="11c20-p106">Email. Usado apenas pelos tipos de usuários.</span><span class="sxs-lookup"><span data-stu-id="11c20-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11c20-138">prinADPath</span><span class="sxs-lookup"><span data-stu-id="11c20-138">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="11c20-139">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="11c20-139">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="11c20-p107">Nome de domínio do objeto do Active Directory do qual a entidade é uma versão em cache. Pode ser nulo para tipos que não são objetos do Active Directory (como os usuários do sistema).</span><span class="sxs-lookup"><span data-stu-id="11c20-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11c20-142">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="11c20-142">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="11c20-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11c20-143">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="11c20-p108">Nome UPN do usuário. Usado somente pelos tipos de usuário regular.</span><span class="sxs-lookup"><span data-stu-id="11c20-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11c20-146">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="11c20-146">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="11c20-147">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="11c20-147">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="11c20-148">0: a entidade está ativa.</span><span class="sxs-lookup"><span data-stu-id="11c20-148">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="11c20-149">1: a entidade é desabilitada porque os recursos SIP do usuário estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="11c20-149">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="11c20-150">2: a entidade é excluída porque o objeto associado do AD foi excluído.</span><span class="sxs-lookup"><span data-stu-id="11c20-150">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11c20-151">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="11c20-151">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="11c20-152">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="11c20-152">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="11c20-153">Tipo de entidade (da tabela tblPrincipalType).</span><span class="sxs-lookup"><span data-stu-id="11c20-153">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11c20-154">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="11c20-154">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="11c20-155">Int</span><span class="sxs-lookup"><span data-stu-id="11c20-155">Int</span></span></p></td>
<td><p><span data-ttu-id="11c20-156">Atribuição do pool do Lync para a entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="11c20-156">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11c20-157">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="11c20-157">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="11c20-158">Int</span><span class="sxs-lookup"><span data-stu-id="11c20-158">Int</span></span></p></td>
<td><p><span data-ttu-id="11c20-159">Valor da política do servidor de chat persistente para o usuário, se a política de tipo de marca estiver presente.</span><span class="sxs-lookup"><span data-stu-id="11c20-159">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11c20-160">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="11c20-160">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="11c20-161">int</span><span class="sxs-lookup"><span data-stu-id="11c20-161">int</span></span></p></td>
<td><p><span data-ttu-id="11c20-162">ID da entidade do criador.</span><span class="sxs-lookup"><span data-stu-id="11c20-162">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11c20-163">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="11c20-163">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="11c20-164">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="11c20-164">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="11c20-165">Carimbo de data/hora para a hora da criação.</span><span class="sxs-lookup"><span data-stu-id="11c20-165">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11c20-166">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="11c20-166">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="11c20-167">int</span><span class="sxs-lookup"><span data-stu-id="11c20-167">int</span></span></p></td>
<td><p><span data-ttu-id="11c20-168">ID da entidade que atualizou esta entrada pela última vez.</span><span class="sxs-lookup"><span data-stu-id="11c20-168">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11c20-169">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="11c20-169">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="11c20-170">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="11c20-170">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="11c20-171">Carimbo de data/hora da última atualização.</span><span class="sxs-lookup"><span data-stu-id="11c20-171">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11c20-172">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="11c20-172">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="11c20-173">datetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="11c20-173">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="11c20-174">Data e hora da última atualização de Sincronização do Active Directory para a entidade.</span><span class="sxs-lookup"><span data-stu-id="11c20-174">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="11c20-175">Chaves</span><span class="sxs-lookup"><span data-stu-id="11c20-175">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11c20-176">Coluna</span><span class="sxs-lookup"><span data-stu-id="11c20-176">Column</span></span></th>
<th><span data-ttu-id="11c20-177">Descrição</span><span class="sxs-lookup"><span data-stu-id="11c20-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11c20-178">prinID</span><span class="sxs-lookup"><span data-stu-id="11c20-178">prinID</span></span></p></td>
<td><p><span data-ttu-id="11c20-179">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="11c20-179">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11c20-180">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="11c20-180">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="11c20-181">Chave estrangeira com pesquisa na tabela tblPrincipalType.ptypeID.</span><span class="sxs-lookup"><span data-stu-id="11c20-181">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

