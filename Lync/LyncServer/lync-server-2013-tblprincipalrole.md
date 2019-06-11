---
title: 'Lync Server 2013: tblPrincipalRole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 560f454531060a8458c8c920a1e4c5921867f3e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="621ce-102">tblPrincipalRole no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="621ce-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="621ce-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="621ce-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="621ce-104">tblPrincipalRole contém funções explícitas atribuídas a nós.</span><span class="sxs-lookup"><span data-stu-id="621ce-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="621ce-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="621ce-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="621ce-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="621ce-106">Column</span></span></th>
<th><span data-ttu-id="621ce-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="621ce-107">Type</span></span></th>
<th><span data-ttu-id="621ce-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="621ce-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="621ce-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="621ce-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="621ce-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="621ce-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="621ce-111">ID do nó ao qual a função se aplica.</span><span class="sxs-lookup"><span data-stu-id="621ce-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="621ce-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="621ce-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="621ce-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="621ce-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="621ce-114">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="621ce-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="621ce-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="621ce-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="621ce-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="621ce-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="621ce-117">ID do tipo de função (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="621ce-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="621ce-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="621ce-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="621ce-119">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="621ce-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="621ce-120">ID da entidade de segurança que atualizou pela última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="621ce-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="621ce-121">As</span><span class="sxs-lookup"><span data-stu-id="621ce-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="621ce-122">Coluna</span><span class="sxs-lookup"><span data-stu-id="621ce-122">Column</span></span></th>
<th><span data-ttu-id="621ce-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="621ce-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="621ce-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="621ce-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="621ce-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="621ce-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="621ce-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="621ce-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="621ce-127">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="621ce-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="621ce-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="621ce-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="621ce-129">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="621ce-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="621ce-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="621ce-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="621ce-131">Chave estrangeira com Lookup na tabela tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="621ce-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

