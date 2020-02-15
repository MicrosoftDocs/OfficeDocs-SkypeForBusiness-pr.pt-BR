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
ms.openlocfilehash: ddab28b269cf2b720d6935fa6d50f4bf9ea3084a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="69afa-102">tblPrincipalRole no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69afa-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69afa-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="69afa-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="69afa-104">tblPrincipalRole contém funções explícitas atribuídas aos nós.</span><span class="sxs-lookup"><span data-stu-id="69afa-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="69afa-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="69afa-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69afa-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="69afa-106">Column</span></span></th>
<th><span data-ttu-id="69afa-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="69afa-107">Type</span></span></th>
<th><span data-ttu-id="69afa-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="69afa-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69afa-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="69afa-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="69afa-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="69afa-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="69afa-111">ID do nó ao qual a função se aplica.</span><span class="sxs-lookup"><span data-stu-id="69afa-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69afa-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="69afa-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="69afa-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="69afa-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="69afa-114">ID principal.</span><span class="sxs-lookup"><span data-stu-id="69afa-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69afa-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="69afa-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="69afa-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="69afa-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="69afa-117">ID de tipo de função (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="69afa-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69afa-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="69afa-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="69afa-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="69afa-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="69afa-120">ID da entidade de segurança da última atualização dessa entrada.</span><span class="sxs-lookup"><span data-stu-id="69afa-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="69afa-121">Chaves</span><span class="sxs-lookup"><span data-stu-id="69afa-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69afa-122">Coluna</span><span class="sxs-lookup"><span data-stu-id="69afa-122">Column</span></span></th>
<th><span data-ttu-id="69afa-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="69afa-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69afa-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="69afa-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="69afa-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="69afa-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69afa-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="69afa-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="69afa-127">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="69afa-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69afa-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="69afa-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="69afa-129">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="69afa-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69afa-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="69afa-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="69afa-131">Chave estrangeira com pesquisa na tabela tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="69afa-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

