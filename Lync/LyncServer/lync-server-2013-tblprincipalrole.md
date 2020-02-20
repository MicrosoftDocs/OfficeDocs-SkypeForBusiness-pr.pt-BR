---
title: 'Lync Server 2013: tblPrincipalRole'
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
ms.openlocfilehash: d4da9525e81856989c5d5046e43b2277ca6a8b2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="4c8e1-102">tblPrincipalRole no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c8e1-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c8e1-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4c8e1-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4c8e1-104">tblPrincipalRole contém funções explícitas atribuídas aos nós.</span><span class="sxs-lookup"><span data-stu-id="4c8e1-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="4c8e1-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="4c8e1-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c8e1-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="4c8e1-106">Column</span></span></th>
<th><span data-ttu-id="4c8e1-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="4c8e1-107">Type</span></span></th>
<th><span data-ttu-id="4c8e1-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="4c8e1-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c8e1-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="4c8e1-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="4c8e1-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="4c8e1-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4c8e1-111">ID do nó ao qual a função se aplica.</span><span class="sxs-lookup"><span data-stu-id="4c8e1-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8e1-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="4c8e1-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="4c8e1-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="4c8e1-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4c8e1-114">ID principal.</span><span class="sxs-lookup"><span data-stu-id="4c8e1-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8e1-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="4c8e1-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="4c8e1-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="4c8e1-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4c8e1-117">ID de tipo de função (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="4c8e1-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8e1-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="4c8e1-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="4c8e1-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="4c8e1-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4c8e1-120">ID da entidade de segurança da última atualização dessa entrada.</span><span class="sxs-lookup"><span data-stu-id="4c8e1-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="4c8e1-121">Chaves</span><span class="sxs-lookup"><span data-stu-id="4c8e1-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c8e1-122">Coluna</span><span class="sxs-lookup"><span data-stu-id="4c8e1-122">Column</span></span></th>
<th><span data-ttu-id="4c8e1-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="4c8e1-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c8e1-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="4c8e1-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="4c8e1-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="4c8e1-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8e1-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="4c8e1-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="4c8e1-127">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="4c8e1-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c8e1-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="4c8e1-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="4c8e1-129">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="4c8e1-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c8e1-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="4c8e1-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="4c8e1-131">Chave estrangeira com pesquisa na tabela tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="4c8e1-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

