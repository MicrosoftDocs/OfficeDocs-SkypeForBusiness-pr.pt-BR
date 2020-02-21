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
ms.openlocfilehash: 0de18da521bd4dadc63d5be592009bd60b643e7b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="5b960-102">tblPrincipalType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b960-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b960-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5b960-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5b960-104">PrincipalType contém os tipos principais para categorizar o que está na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="5b960-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="5b960-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="5b960-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b960-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="5b960-106">Column</span></span></th>
<th><span data-ttu-id="5b960-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="5b960-107">Type</span></span></th>
<th><span data-ttu-id="5b960-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="5b960-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b960-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="5b960-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="5b960-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="5b960-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="5b960-111">ID do tipo principal.</span><span class="sxs-lookup"><span data-stu-id="5b960-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b960-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="5b960-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="5b960-113">não nulo nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5b960-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="5b960-114">Descrição do tipo.</span><span class="sxs-lookup"><span data-stu-id="5b960-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b960-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="5b960-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="5b960-116">bit, não vazio</span><span class="sxs-lookup"><span data-stu-id="5b960-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="5b960-117">True se o tipo corresponder às entidades que são usadas para fins internos.</span><span class="sxs-lookup"><span data-stu-id="5b960-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b960-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="5b960-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="5b960-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="5b960-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="5b960-120">True se o tipo for um tipo de usuário.</span><span class="sxs-lookup"><span data-stu-id="5b960-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5b960-121">Chave</span><span class="sxs-lookup"><span data-stu-id="5b960-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b960-122">Coluna</span><span class="sxs-lookup"><span data-stu-id="5b960-122">Column</span></span></th>
<th><span data-ttu-id="5b960-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="5b960-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b960-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="5b960-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="5b960-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="5b960-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="5b960-126">Valores principais</span><span class="sxs-lookup"><span data-stu-id="5b960-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b960-127">ID</span><span class="sxs-lookup"><span data-stu-id="5b960-127">ID</span></span></th>
<th><span data-ttu-id="5b960-128">Role</span><span class="sxs-lookup"><span data-stu-id="5b960-128">Role</span></span></th>
<th><span data-ttu-id="5b960-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="5b960-129">Description</span></span></th>
<th><span data-ttu-id="5b960-130">Usuário</span><span class="sxs-lookup"><span data-stu-id="5b960-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b960-131">1</span><span class="sxs-lookup"><span data-stu-id="5b960-131">1</span></span></p></td>
<td><p><span data-ttu-id="5b960-132">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="5b960-132">Any</span></span></p></td>
<td><p><span data-ttu-id="5b960-p101">Entidade genérica sem um tipo conhecido. Não usado na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="5b960-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b960-135">duas</span><span class="sxs-lookup"><span data-stu-id="5b960-135">2</span></span></p></td>
<td><p><span data-ttu-id="5b960-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="5b960-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="5b960-p102">Entidade de segurança genérica do tipo de usuário. Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="5b960-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="5b960-139">Sim</span><span class="sxs-lookup"><span data-stu-id="5b960-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b960-140">3D</span><span class="sxs-lookup"><span data-stu-id="5b960-140">3</span></span></p></td>
<td><p><span data-ttu-id="5b960-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="5b960-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="5b960-p103">Entidade de segurança genérica com semântica de grupo. Não é usada na tabela tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="5b960-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b960-144">quatro</span><span class="sxs-lookup"><span data-stu-id="5b960-144">4</span></span></p></td>
<td><p><span data-ttu-id="5b960-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="5b960-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="5b960-146">Principal usada internamente pelo servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5b960-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b960-147">0,5</span><span class="sxs-lookup"><span data-stu-id="5b960-147">5</span></span></p></td>
<td><p><span data-ttu-id="5b960-148">Usuário</span><span class="sxs-lookup"><span data-stu-id="5b960-148">User</span></span></p></td>
<td><p><span data-ttu-id="5b960-149">Usuário regular.</span><span class="sxs-lookup"><span data-stu-id="5b960-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="5b960-150">Sim</span><span class="sxs-lookup"><span data-stu-id="5b960-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b960-151">8 </span><span class="sxs-lookup"><span data-stu-id="5b960-151">8</span></span></p></td>
<td><p><span data-ttu-id="5b960-152">CC</span><span class="sxs-lookup"><span data-stu-id="5b960-152">DC</span></span></p></td>
<td><p><span data-ttu-id="5b960-153">Controlador de domínio dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b960-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b960-154">9 </span><span class="sxs-lookup"><span data-stu-id="5b960-154">9</span></span></p></td>
<td><p><span data-ttu-id="5b960-155">Group</span><span class="sxs-lookup"><span data-stu-id="5b960-155">Group</span></span></p></td>
<td><p><span data-ttu-id="5b960-156">Grupo de segurança do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b960-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b960-157">10 </span><span class="sxs-lookup"><span data-stu-id="5b960-157">10</span></span></p></td>
<td><p><span data-ttu-id="5b960-158">Folder</span><span class="sxs-lookup"><span data-stu-id="5b960-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="5b960-159">Unidade organizacional ou recipiente do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b960-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="5b960-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="5b960-160">See Also</span></span>


[<span data-ttu-id="5b960-161">tblPrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b960-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

