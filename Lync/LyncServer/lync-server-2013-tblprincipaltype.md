---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6731d0bcda6e4e66b1b498a5f1bf91023627b1f0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="78e0d-102">tblPrincipalType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78e0d-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78e0d-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="78e0d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="78e0d-104">tblPrincipalType contém tipos principais para categorizar o que está na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="78e0d-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="78e0d-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="78e0d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78e0d-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="78e0d-106">Column</span></span></th>
<th><span data-ttu-id="78e0d-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="78e0d-107">Type</span></span></th>
<th><span data-ttu-id="78e0d-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="78e0d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78e0d-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="78e0d-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="78e0d-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="78e0d-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="78e0d-111">ID do tipo principal.</span><span class="sxs-lookup"><span data-stu-id="78e0d-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78e0d-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="78e0d-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="78e0d-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="78e0d-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="78e0d-114">Descrição do tipo.</span><span class="sxs-lookup"><span data-stu-id="78e0d-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78e0d-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="78e0d-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="78e0d-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="78e0d-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="78e0d-117">Verdadeiro se o tipo corresponder às entidades de segurança usadas para fins internos.</span><span class="sxs-lookup"><span data-stu-id="78e0d-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78e0d-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="78e0d-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="78e0d-119">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="78e0d-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="78e0d-120">Verdadeiro se o tipo for um tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="78e0d-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="78e0d-121">Chave</span><span class="sxs-lookup"><span data-stu-id="78e0d-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78e0d-122">Coluna</span><span class="sxs-lookup"><span data-stu-id="78e0d-122">Column</span></span></th>
<th><span data-ttu-id="78e0d-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="78e0d-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78e0d-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="78e0d-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="78e0d-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="78e0d-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="78e0d-126">Valores principais</span><span class="sxs-lookup"><span data-stu-id="78e0d-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78e0d-127">ID</span><span class="sxs-lookup"><span data-stu-id="78e0d-127">ID</span></span></th>
<th><span data-ttu-id="78e0d-128">Função</span><span class="sxs-lookup"><span data-stu-id="78e0d-128">Role</span></span></th>
<th><span data-ttu-id="78e0d-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="78e0d-129">Description</span></span></th>
<th><span data-ttu-id="78e0d-130">Usuário</span><span class="sxs-lookup"><span data-stu-id="78e0d-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78e0d-131">1</span><span class="sxs-lookup"><span data-stu-id="78e0d-131">1</span></span></p></td>
<td><p><span data-ttu-id="78e0d-132">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="78e0d-132">Any</span></span></p></td>
<td><p><span data-ttu-id="78e0d-133">Entidade de segurança genérica sem tipo conhecido.</span><span class="sxs-lookup"><span data-stu-id="78e0d-133">Generic principal with no known type.</span></span> <span data-ttu-id="78e0d-134">Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="78e0d-134">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78e0d-135">2</span><span class="sxs-lookup"><span data-stu-id="78e0d-135">2</span></span></p></td>
<td><p><span data-ttu-id="78e0d-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="78e0d-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="78e0d-137">Entidade de usuário genérica do tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="78e0d-137">Generic principal of user type.</span></span> <span data-ttu-id="78e0d-138">Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="78e0d-138">Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="78e0d-139">Sim</span><span class="sxs-lookup"><span data-stu-id="78e0d-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78e0d-140">3</span><span class="sxs-lookup"><span data-stu-id="78e0d-140">3</span></span></p></td>
<td><p><span data-ttu-id="78e0d-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="78e0d-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="78e0d-142">Entidade de segurança genérica com semântica de grupo.</span><span class="sxs-lookup"><span data-stu-id="78e0d-142">Generic principal with group semantic.</span></span> <span data-ttu-id="78e0d-143">Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="78e0d-143">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78e0d-144">4</span><span class="sxs-lookup"><span data-stu-id="78e0d-144">4</span></span></p></td>
<td><p><span data-ttu-id="78e0d-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="78e0d-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="78e0d-146">Principal usado internamente pelo servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="78e0d-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78e0d-147">5</span><span class="sxs-lookup"><span data-stu-id="78e0d-147">5</span></span></p></td>
<td><p><span data-ttu-id="78e0d-148">Usuário</span><span class="sxs-lookup"><span data-stu-id="78e0d-148">User</span></span></p></td>
<td><p><span data-ttu-id="78e0d-149">Usuário regular.</span><span class="sxs-lookup"><span data-stu-id="78e0d-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="78e0d-150">Sim</span><span class="sxs-lookup"><span data-stu-id="78e0d-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78e0d-151">8</span><span class="sxs-lookup"><span data-stu-id="78e0d-151">8</span></span></p></td>
<td><p><span data-ttu-id="78e0d-152">CLONA</span><span class="sxs-lookup"><span data-stu-id="78e0d-152">DC</span></span></p></td>
<td><p><span data-ttu-id="78e0d-153">Controlador de domínio dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="78e0d-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78e0d-154">9</span><span class="sxs-lookup"><span data-stu-id="78e0d-154">9</span></span></p></td>
<td><p><span data-ttu-id="78e0d-155">Grupos</span><span class="sxs-lookup"><span data-stu-id="78e0d-155">Group</span></span></p></td>
<td><p><span data-ttu-id="78e0d-156">Grupo de segurança do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="78e0d-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78e0d-157">254</span><span class="sxs-lookup"><span data-stu-id="78e0d-157">10</span></span></p></td>
<td><p><span data-ttu-id="78e0d-158">La</span><span class="sxs-lookup"><span data-stu-id="78e0d-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="78e0d-159">Contêiner ou unidade organizacional do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="78e0d-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="78e0d-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="78e0d-160">See Also</span></span>


[<span data-ttu-id="78e0d-161">tblPrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78e0d-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

