---
title: 'Lync Server 2013: tblPrincipal'
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
ms.openlocfilehash: b9d5122b375b4906320f254179ce101652ad6db2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="5bb79-102">tblPrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bb79-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bb79-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5bb79-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5bb79-104">tblPrincipal contém todas as entidades, incluindo usuários, pastas e grupos.</span><span class="sxs-lookup"><span data-stu-id="5bb79-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="5bb79-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="5bb79-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5bb79-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="5bb79-106">Column</span></span></th>
<th><span data-ttu-id="5bb79-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="5bb79-107">Type</span></span></th>
<th><span data-ttu-id="5bb79-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="5bb79-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bb79-109">prinID</span><span class="sxs-lookup"><span data-stu-id="5bb79-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="5bb79-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="5bb79-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5bb79-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="5bb79-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb79-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="5bb79-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="5bb79-113">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="5bb79-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="5bb79-114">GUID da entidade.</span><span class="sxs-lookup"><span data-stu-id="5bb79-114">Principal GUID.</span></span> <span data-ttu-id="5bb79-115">Isso é amplamente usado como uma chave primária alternativa, pois o significado é cruzado no espaço dos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5bb79-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="5bb79-116">(O GUID de uma entidade em cache é igual ao GUID de objeto correspondente no Active Directory).</span><span class="sxs-lookup"><span data-stu-id="5bb79-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb79-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="5bb79-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="5bb79-118">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="5bb79-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="5bb79-p102">URI de entidade. O esquema do SIP é usado para usuários e o ma-grp é usado para quase tudo.</span><span class="sxs-lookup"><span data-stu-id="5bb79-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb79-121">imprimir</span><span class="sxs-lookup"><span data-stu-id="5bb79-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="5bb79-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5bb79-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="5bb79-p103">Nome comum. Usado apenas por tipos de usuário.</span><span class="sxs-lookup"><span data-stu-id="5bb79-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb79-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="5bb79-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="5bb79-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5bb79-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="5bb79-p104">Nome de exibição. Usado somente pelos tipos de usuário.</span><span class="sxs-lookup"><span data-stu-id="5bb79-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb79-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="5bb79-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="5bb79-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5bb79-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="5bb79-p105">Nome da empresa. Usado somente pelos tipos de usuário.</span><span class="sxs-lookup"><span data-stu-id="5bb79-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb79-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="5bb79-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="5bb79-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5bb79-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="5bb79-p106">Email. Usado apenas pelos tipos de usuários.</span><span class="sxs-lookup"><span data-stu-id="5bb79-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb79-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="5bb79-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="5bb79-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="5bb79-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="5bb79-p107">Nome de domínio do objeto do Active Directory do qual a entidade é uma versão em cache. Pode ser nulo para tipos que não são objetos do Active Directory (como os usuários do sistema).</span><span class="sxs-lookup"><span data-stu-id="5bb79-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb79-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="5bb79-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="5bb79-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5bb79-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="5bb79-p108">Nome UPN do usuário. Usado somente pelos tipos de usuário regular.</span><span class="sxs-lookup"><span data-stu-id="5bb79-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb79-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="5bb79-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="5bb79-146">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="5bb79-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5bb79-147">0: a entidade está ativa.</span><span class="sxs-lookup"><span data-stu-id="5bb79-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="5bb79-148">1: a entidade é desabilitada porque os recursos SIP do usuário estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="5bb79-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="5bb79-149">2: a entidade é excluída porque o objeto associado do AD foi excluído.</span><span class="sxs-lookup"><span data-stu-id="5bb79-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb79-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="5bb79-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="5bb79-151">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="5bb79-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="5bb79-152">Tipo de entidade (da tabela tblPrincipalType).</span><span class="sxs-lookup"><span data-stu-id="5bb79-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb79-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="5bb79-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="5bb79-154">Int</span><span class="sxs-lookup"><span data-stu-id="5bb79-154">Int</span></span></p></td>
<td><p><span data-ttu-id="5bb79-155">Atribuição do pool do Lync para a entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="5bb79-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb79-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="5bb79-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="5bb79-157">Int</span><span class="sxs-lookup"><span data-stu-id="5bb79-157">Int</span></span></p></td>
<td><p><span data-ttu-id="5bb79-158">Valor da política do servidor de chat persistente para o usuário, se a política de tipo de marca estiver presente.</span><span class="sxs-lookup"><span data-stu-id="5bb79-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb79-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="5bb79-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="5bb79-160">int</span><span class="sxs-lookup"><span data-stu-id="5bb79-160">int</span></span></p></td>
<td><p><span data-ttu-id="5bb79-161">ID da entidade do criador.</span><span class="sxs-lookup"><span data-stu-id="5bb79-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb79-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="5bb79-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="5bb79-163">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="5bb79-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="5bb79-164">Carimbo de data/hora para a hora da criação.</span><span class="sxs-lookup"><span data-stu-id="5bb79-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb79-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="5bb79-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="5bb79-166">int</span><span class="sxs-lookup"><span data-stu-id="5bb79-166">int</span></span></p></td>
<td><p><span data-ttu-id="5bb79-167">ID da entidade que atualizou esta entrada pela última vez.</span><span class="sxs-lookup"><span data-stu-id="5bb79-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bb79-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="5bb79-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="5bb79-169">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="5bb79-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="5bb79-170">Carimbo de data/hora da última atualização.</span><span class="sxs-lookup"><span data-stu-id="5bb79-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb79-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="5bb79-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="5bb79-172">datetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="5bb79-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="5bb79-173">Data e hora da última atualização de Sincronização do Active Directory para a entidade.</span><span class="sxs-lookup"><span data-stu-id="5bb79-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5bb79-174">Chaves</span><span class="sxs-lookup"><span data-stu-id="5bb79-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5bb79-175">Coluna</span><span class="sxs-lookup"><span data-stu-id="5bb79-175">Column</span></span></th>
<th><span data-ttu-id="5bb79-176">Descrição</span><span class="sxs-lookup"><span data-stu-id="5bb79-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bb79-177">prinID</span><span class="sxs-lookup"><span data-stu-id="5bb79-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="5bb79-178">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="5bb79-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bb79-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="5bb79-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="5bb79-180">Chave estrangeira com pesquisa na tabela tblPrincipalType.ptypeID.</span><span class="sxs-lookup"><span data-stu-id="5bb79-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

