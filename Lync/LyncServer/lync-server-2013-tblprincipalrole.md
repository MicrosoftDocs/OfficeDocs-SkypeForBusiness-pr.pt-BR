---
title: 'Lync Server 2013: tblPrincipalRole'
description: 'Lync Server 2013: tblPrincipalRole.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58ffda3136c254ee77f14d33dcb42af5d172c4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573627"
---
# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="7844d-103">tblPrincipalRole no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7844d-103">tblPrincipalRole in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7844d-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="7844d-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="7844d-105">tblPrincipalRole contém funções explícitas atribuídas aos nós.</span><span class="sxs-lookup"><span data-stu-id="7844d-105">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="7844d-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="7844d-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7844d-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="7844d-107">Column</span></span></th>
<th><span data-ttu-id="7844d-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="7844d-108">Type</span></span></th>
<th><span data-ttu-id="7844d-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="7844d-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7844d-110">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="7844d-110">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="7844d-111">int, not null</span><span class="sxs-lookup"><span data-stu-id="7844d-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7844d-112">ID do nó ao qual a função se aplica.</span><span class="sxs-lookup"><span data-stu-id="7844d-112">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7844d-113">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="7844d-113">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="7844d-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="7844d-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7844d-115">ID principal.</span><span class="sxs-lookup"><span data-stu-id="7844d-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7844d-116">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="7844d-116">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="7844d-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="7844d-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7844d-118">ID de tipo de função (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="7844d-118">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7844d-119">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="7844d-119">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="7844d-120">int, not null</span><span class="sxs-lookup"><span data-stu-id="7844d-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="7844d-121">ID da entidade de segurança da última atualização dessa entrada.</span><span class="sxs-lookup"><span data-stu-id="7844d-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="7844d-122">Chaves</span><span class="sxs-lookup"><span data-stu-id="7844d-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7844d-123">Coluna</span><span class="sxs-lookup"><span data-stu-id="7844d-123">Column</span></span></th>
<th><span data-ttu-id="7844d-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="7844d-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7844d-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="7844d-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="7844d-126">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="7844d-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7844d-127">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="7844d-127">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="7844d-128">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="7844d-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7844d-129">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="7844d-129">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="7844d-130">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="7844d-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7844d-131">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="7844d-131">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="7844d-132">Chave estrangeira com pesquisa na tabela tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="7844d-132">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

