---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725d097e1e2e75b6430974a4f133cb5fa4130346
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="0a571-102">tblPrincipalType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a571-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a571-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="0a571-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="0a571-104">tblPrincipalType contém tipos principais para categorizar o que está na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="0a571-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="0a571-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="0a571-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a571-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="0a571-106">Column</span></span></th>
<th><span data-ttu-id="0a571-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="0a571-107">Type</span></span></th>
<th><span data-ttu-id="0a571-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="0a571-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a571-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="0a571-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="0a571-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="0a571-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="0a571-111">ID do tipo principal.</span><span class="sxs-lookup"><span data-stu-id="0a571-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a571-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="0a571-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="0a571-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="0a571-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="0a571-114">Descrição do tipo.</span><span class="sxs-lookup"><span data-stu-id="0a571-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a571-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="0a571-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="0a571-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="0a571-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="0a571-117">Verdadeiro se o tipo corresponder às entidades de segurança usadas para fins internos.</span><span class="sxs-lookup"><span data-stu-id="0a571-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a571-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="0a571-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="0a571-119">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="0a571-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="0a571-120">Verdadeiro se o tipo for um tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="0a571-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="0a571-121">Chave</span><span class="sxs-lookup"><span data-stu-id="0a571-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a571-122">Coluna</span><span class="sxs-lookup"><span data-stu-id="0a571-122">Column</span></span></th>
<th><span data-ttu-id="0a571-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="0a571-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a571-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="0a571-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="0a571-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="0a571-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="0a571-126">Valores principais</span><span class="sxs-lookup"><span data-stu-id="0a571-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a571-127">ID</span><span class="sxs-lookup"><span data-stu-id="0a571-127">ID</span></span></th>
<th><span data-ttu-id="0a571-128">Função</span><span class="sxs-lookup"><span data-stu-id="0a571-128">Role</span></span></th>
<th><span data-ttu-id="0a571-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="0a571-129">Description</span></span></th>
<th><span data-ttu-id="0a571-130">Usuário</span><span class="sxs-lookup"><span data-stu-id="0a571-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a571-131">1</span><span class="sxs-lookup"><span data-stu-id="0a571-131">1</span></span></p></td>
<td><p><span data-ttu-id="0a571-132">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="0a571-132">Any</span></span></p></td>
<td><p><span data-ttu-id="0a571-133">Entidade de segurança genérica sem tipo conhecido.</span><span class="sxs-lookup"><span data-stu-id="0a571-133">Generic principal with no known type.</span></span> <span data-ttu-id="0a571-134">Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="0a571-134">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a571-135">2</span><span class="sxs-lookup"><span data-stu-id="0a571-135">2</span></span></p></td>
<td><p><span data-ttu-id="0a571-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="0a571-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="0a571-137">Entidade de usuário genérica do tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="0a571-137">Generic principal of user type.</span></span> <span data-ttu-id="0a571-138">Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="0a571-138">Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="0a571-139">Sim</span><span class="sxs-lookup"><span data-stu-id="0a571-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a571-140">3</span><span class="sxs-lookup"><span data-stu-id="0a571-140">3</span></span></p></td>
<td><p><span data-ttu-id="0a571-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="0a571-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="0a571-142">Entidade de segurança genérica com semântica de grupo.</span><span class="sxs-lookup"><span data-stu-id="0a571-142">Generic principal with group semantic.</span></span> <span data-ttu-id="0a571-143">Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="0a571-143">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a571-144">4</span><span class="sxs-lookup"><span data-stu-id="0a571-144">4</span></span></p></td>
<td><p><span data-ttu-id="0a571-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="0a571-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="0a571-146">Principal usado internamente pelo servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0a571-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a571-147">5</span><span class="sxs-lookup"><span data-stu-id="0a571-147">5</span></span></p></td>
<td><p><span data-ttu-id="0a571-148">Usuário</span><span class="sxs-lookup"><span data-stu-id="0a571-148">User</span></span></p></td>
<td><p><span data-ttu-id="0a571-149">Usuário regular.</span><span class="sxs-lookup"><span data-stu-id="0a571-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="0a571-150">Sim</span><span class="sxs-lookup"><span data-stu-id="0a571-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a571-151">08</span><span class="sxs-lookup"><span data-stu-id="0a571-151">8</span></span></p></td>
<td><p><span data-ttu-id="0a571-152">CLONA</span><span class="sxs-lookup"><span data-stu-id="0a571-152">DC</span></span></p></td>
<td><p><span data-ttu-id="0a571-153">Controlador de domínio dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0a571-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a571-154">222</span><span class="sxs-lookup"><span data-stu-id="0a571-154">9</span></span></p></td>
<td><p><span data-ttu-id="0a571-155">Grupos</span><span class="sxs-lookup"><span data-stu-id="0a571-155">Group</span></span></p></td>
<td><p><span data-ttu-id="0a571-156">Grupo de segurança do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0a571-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a571-157">254</span><span class="sxs-lookup"><span data-stu-id="0a571-157">10</span></span></p></td>
<td><p><span data-ttu-id="0a571-158">La</span><span class="sxs-lookup"><span data-stu-id="0a571-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="0a571-159">Contêiner ou unidade organizacional do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0a571-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="0a571-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="0a571-160">See Also</span></span>


[<span data-ttu-id="0a571-161">tblPrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a571-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

