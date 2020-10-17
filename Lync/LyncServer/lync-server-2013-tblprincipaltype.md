---
title: 'Lync Server 2013: tblPrincipalType'
description: 'Lync Server 2013: tblPrincipalType.'
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
ms.openlocfilehash: ba0f607d4499b54b16d7ecf8a4e7de603e874788
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549857"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="8e905-103">tblPrincipalType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e905-103">tblPrincipalType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e905-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="8e905-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="8e905-105">PrincipalType contém os tipos principais para categorizar o que está na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="8e905-105">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="8e905-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="8e905-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e905-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="8e905-107">Column</span></span></th>
<th><span data-ttu-id="8e905-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="8e905-108">Type</span></span></th>
<th><span data-ttu-id="8e905-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="8e905-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e905-110">ptypeID</span><span class="sxs-lookup"><span data-stu-id="8e905-110">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="8e905-111">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="8e905-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="8e905-112">ID do tipo principal.</span><span class="sxs-lookup"><span data-stu-id="8e905-112">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e905-113">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="8e905-113">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="8e905-114">não nulo nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8e905-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="8e905-115">Descrição do tipo.</span><span class="sxs-lookup"><span data-stu-id="8e905-115">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e905-116">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="8e905-116">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="8e905-117">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="8e905-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="8e905-118">True se o tipo corresponder às entidades que são usadas para fins internos.</span><span class="sxs-lookup"><span data-stu-id="8e905-118">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e905-119">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="8e905-119">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="8e905-120">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="8e905-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="8e905-121">True se o tipo for um tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="8e905-121">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="8e905-122">Chave</span><span class="sxs-lookup"><span data-stu-id="8e905-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e905-123">Coluna</span><span class="sxs-lookup"><span data-stu-id="8e905-123">Column</span></span></th>
<th><span data-ttu-id="8e905-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="8e905-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e905-125">ptypeID</span><span class="sxs-lookup"><span data-stu-id="8e905-125">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="8e905-126">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="8e905-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="8e905-127">Valores principais</span><span class="sxs-lookup"><span data-stu-id="8e905-127">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e905-128">ID</span><span class="sxs-lookup"><span data-stu-id="8e905-128">ID</span></span></th>
<th><span data-ttu-id="8e905-129">Role</span><span class="sxs-lookup"><span data-stu-id="8e905-129">Role</span></span></th>
<th><span data-ttu-id="8e905-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="8e905-130">Description</span></span></th>
<th><span data-ttu-id="8e905-131">Usuário</span><span class="sxs-lookup"><span data-stu-id="8e905-131">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e905-132">1</span><span class="sxs-lookup"><span data-stu-id="8e905-132">1</span></span></p></td>
<td><p><span data-ttu-id="8e905-133">Qualquer</span><span class="sxs-lookup"><span data-stu-id="8e905-133">Any</span></span></p></td>
<td><p><span data-ttu-id="8e905-p101">Entidade genérica sem um tipo conhecido. Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="8e905-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e905-136">duas</span><span class="sxs-lookup"><span data-stu-id="8e905-136">2</span></span></p></td>
<td><p><span data-ttu-id="8e905-137">AnyUser</span><span class="sxs-lookup"><span data-stu-id="8e905-137">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="8e905-p102">Entidade de segurança genérica do tipo de usuário. Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="8e905-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="8e905-140">Sim</span><span class="sxs-lookup"><span data-stu-id="8e905-140">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e905-141">3D</span><span class="sxs-lookup"><span data-stu-id="8e905-141">3</span></span></p></td>
<td><p><span data-ttu-id="8e905-142">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="8e905-142">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="8e905-p103">Entidade de segurança genérica com semântica de grupo. Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="8e905-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e905-145">4 </span><span class="sxs-lookup"><span data-stu-id="8e905-145">4</span></span></p></td>
<td><p><span data-ttu-id="8e905-146">SystemUser</span><span class="sxs-lookup"><span data-stu-id="8e905-146">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="8e905-147">Principal usada internamente pelo servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8e905-147">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e905-148">5 </span><span class="sxs-lookup"><span data-stu-id="8e905-148">5</span></span></p></td>
<td><p><span data-ttu-id="8e905-149">Usuário</span><span class="sxs-lookup"><span data-stu-id="8e905-149">User</span></span></p></td>
<td><p><span data-ttu-id="8e905-150">Usuário regular.</span><span class="sxs-lookup"><span data-stu-id="8e905-150">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="8e905-151">Sim</span><span class="sxs-lookup"><span data-stu-id="8e905-151">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e905-152">8 </span><span class="sxs-lookup"><span data-stu-id="8e905-152">8</span></span></p></td>
<td><p><span data-ttu-id="8e905-153">CC</span><span class="sxs-lookup"><span data-stu-id="8e905-153">DC</span></span></p></td>
<td><p><span data-ttu-id="8e905-154">Controlador de domínio dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8e905-154">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e905-155">9 </span><span class="sxs-lookup"><span data-stu-id="8e905-155">9</span></span></p></td>
<td><p><span data-ttu-id="8e905-156">Grupo</span><span class="sxs-lookup"><span data-stu-id="8e905-156">Group</span></span></p></td>
<td><p><span data-ttu-id="8e905-157">Grupo de segurança do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8e905-157">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e905-158">10 </span><span class="sxs-lookup"><span data-stu-id="8e905-158">10</span></span></p></td>
<td><p><span data-ttu-id="8e905-159">Folder</span><span class="sxs-lookup"><span data-stu-id="8e905-159">Folder</span></span></p></td>
<td><p><span data-ttu-id="8e905-160">Unidade organizacional ou recipiente do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8e905-160">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="8e905-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="8e905-161">See Also</span></span>


[<span data-ttu-id="8e905-162">tblPrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e905-162">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

