---
title: 'Lync Server 2013: tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c24f963b34ef6184675e724496d7d45ca1d40d27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="b6c40-102">tblPrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6c40-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6c40-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b6c40-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b6c40-104">tblPrincipal contém todas as entidades, incluindo usuários, pastas e grupos.</span><span class="sxs-lookup"><span data-stu-id="b6c40-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="b6c40-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="b6c40-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6c40-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="b6c40-106">Column</span></span></th>
<th><span data-ttu-id="b6c40-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="b6c40-107">Type</span></span></th>
<th><span data-ttu-id="b6c40-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="b6c40-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6c40-109">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="b6c40-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="b6c40-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="b6c40-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b6c40-111">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="b6c40-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6c40-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="b6c40-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="b6c40-113">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="b6c40-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="b6c40-114">GUID principal.</span><span class="sxs-lookup"><span data-stu-id="b6c40-114">Principal GUID.</span></span> <span data-ttu-id="b6c40-115">Isso é amplamente usado como uma chave primária alternativa porque o significado é cruzado para o espaço dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b6c40-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="b6c40-116">(O GUID de uma entidade do cache é igual à GUID do objeto do Active Directory correspondente.)</span><span class="sxs-lookup"><span data-stu-id="b6c40-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6c40-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="b6c40-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="b6c40-118">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="b6c40-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="b6c40-119">URI principal.</span><span class="sxs-lookup"><span data-stu-id="b6c40-119">Principal URI.</span></span> <span data-ttu-id="b6c40-120">O esquema SIP é usado para os usuários, e o ma-GRP é usado para praticamente tudo o mais.</span><span class="sxs-lookup"><span data-stu-id="b6c40-120">The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6c40-121">imprimir</span><span class="sxs-lookup"><span data-stu-id="b6c40-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="b6c40-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b6c40-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="b6c40-123">Nome comum.</span><span class="sxs-lookup"><span data-stu-id="b6c40-123">Common name.</span></span> <span data-ttu-id="b6c40-124">Usado apenas por tipos de usuário.</span><span class="sxs-lookup"><span data-stu-id="b6c40-124">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6c40-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="b6c40-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="b6c40-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b6c40-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="b6c40-127">Nome para exibição.</span><span class="sxs-lookup"><span data-stu-id="b6c40-127">Display name.</span></span> <span data-ttu-id="b6c40-128">Usado apenas por tipos de usuário.</span><span class="sxs-lookup"><span data-stu-id="b6c40-128">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6c40-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="b6c40-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="b6c40-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b6c40-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="b6c40-131">Nome da empresa.</span><span class="sxs-lookup"><span data-stu-id="b6c40-131">Company name.</span></span> <span data-ttu-id="b6c40-132">Usado apenas por tipos de usuário.</span><span class="sxs-lookup"><span data-stu-id="b6c40-132">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6c40-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="b6c40-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="b6c40-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b6c40-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="b6c40-135">Email.</span><span class="sxs-lookup"><span data-stu-id="b6c40-135">Email.</span></span> <span data-ttu-id="b6c40-136">Usado apenas por tipos de usuário.</span><span class="sxs-lookup"><span data-stu-id="b6c40-136">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6c40-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="b6c40-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="b6c40-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="b6c40-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="b6c40-139">Nome do domínio do objeto do Active Directory que a entidade de segurança é uma versão em cache de.</span><span class="sxs-lookup"><span data-stu-id="b6c40-139">Domain name of the Active Directory object that the principal is a cached version of.</span></span> <span data-ttu-id="b6c40-140">Pode ser NULL para tipos que não sejam objetos do Active Directory (como usuários do sistema).</span><span class="sxs-lookup"><span data-stu-id="b6c40-140">Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6c40-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="b6c40-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="b6c40-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b6c40-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="b6c40-143">Nome UPN do usuário.</span><span class="sxs-lookup"><span data-stu-id="b6c40-143">User’s user principal name (UPN).</span></span> <span data-ttu-id="b6c40-144">Usado apenas por tipos de usuário regulares.</span><span class="sxs-lookup"><span data-stu-id="b6c40-144">Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6c40-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="b6c40-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="b6c40-146">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="b6c40-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b6c40-147">0: a entidade de segurança está ativa.</span><span class="sxs-lookup"><span data-stu-id="b6c40-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="b6c40-148">1: o principal está desabilitado porque as funcionalidades SIP do usuário estão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="b6c40-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="b6c40-149">2: o principal é excluído porque o objeto do anúncio associado foi excluído.</span><span class="sxs-lookup"><span data-stu-id="b6c40-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6c40-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="b6c40-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="b6c40-151">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="b6c40-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="b6c40-152">Tipo de entidade de segurança (da tabela tblPrincipalType).</span><span class="sxs-lookup"><span data-stu-id="b6c40-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6c40-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="b6c40-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="b6c40-154">Núm</span><span class="sxs-lookup"><span data-stu-id="b6c40-154">Int</span></span></p></td>
<td><p><span data-ttu-id="b6c40-155">Atribuição de pool do Lync para a entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="b6c40-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6c40-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="b6c40-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="b6c40-157">Núm</span><span class="sxs-lookup"><span data-stu-id="b6c40-157">Int</span></span></p></td>
<td><p><span data-ttu-id="b6c40-158">Valor da política do servidor de chat persistente para o usuário, se a política de tipo de marca estiver presente.</span><span class="sxs-lookup"><span data-stu-id="b6c40-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6c40-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="b6c40-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="b6c40-160">int</span><span class="sxs-lookup"><span data-stu-id="b6c40-160">int</span></span></p></td>
<td><p><span data-ttu-id="b6c40-161">ID da entidade de segurança do criador.</span><span class="sxs-lookup"><span data-stu-id="b6c40-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6c40-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="b6c40-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="b6c40-163">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="b6c40-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="b6c40-164">Carimbo de data/hora para a hora da criação.</span><span class="sxs-lookup"><span data-stu-id="b6c40-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6c40-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="b6c40-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="b6c40-166">int</span><span class="sxs-lookup"><span data-stu-id="b6c40-166">int</span></span></p></td>
<td><p><span data-ttu-id="b6c40-167">ID da entidade de segurança que atualizou pela última vez.</span><span class="sxs-lookup"><span data-stu-id="b6c40-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6c40-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="b6c40-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="b6c40-169">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="b6c40-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="b6c40-170">Carimbo de data/hora para a última atualização.</span><span class="sxs-lookup"><span data-stu-id="b6c40-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6c40-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="b6c40-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="b6c40-172">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="b6c40-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="b6c40-173">Data e hora da última atualização de sincronização do Active Directory para a entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="b6c40-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b6c40-174">As</span><span class="sxs-lookup"><span data-stu-id="b6c40-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6c40-175">Coluna</span><span class="sxs-lookup"><span data-stu-id="b6c40-175">Column</span></span></th>
<th><span data-ttu-id="b6c40-176">Descrição</span><span class="sxs-lookup"><span data-stu-id="b6c40-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6c40-177">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="b6c40-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="b6c40-178">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="b6c40-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6c40-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="b6c40-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="b6c40-180">Chave estrangeira com Lookup na tabela tblPrincipalType. ptypeID.</span><span class="sxs-lookup"><span data-stu-id="b6c40-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

