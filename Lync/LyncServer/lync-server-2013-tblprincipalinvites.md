---
title: 'Lync Server 2013: tblPrincipalInvites'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75d842772c8c0e02352eacf7f80711aa79c29461
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="b400b-102">tblPrincipalInvites no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b400b-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b400b-103">_**Tópico da última modificação:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="b400b-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="b400b-104">tblPrincipalInvites contém convites para todos os usuários provisionados para todos os nós com convite automático ativado.</span><span class="sxs-lookup"><span data-stu-id="b400b-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="b400b-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="b400b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b400b-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="b400b-106">Column</span></span></th>
<th><span data-ttu-id="b400b-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="b400b-107">Type</span></span></th>
<th><span data-ttu-id="b400b-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="b400b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b400b-109">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="b400b-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="b400b-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="b400b-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b400b-111">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="b400b-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b400b-112">invID</span><span class="sxs-lookup"><span data-stu-id="b400b-112">invID</span></span></p></td>
<td><p><span data-ttu-id="b400b-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="b400b-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b400b-114">Número seqüencial exclusivo (por ID da entidade) gerado pela tabela tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="b400b-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b400b-115">NodeId</span><span class="sxs-lookup"><span data-stu-id="b400b-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="b400b-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="b400b-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b400b-117">ID do nó (somente sala de chat).</span><span class="sxs-lookup"><span data-stu-id="b400b-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b400b-118">criar</span><span class="sxs-lookup"><span data-stu-id="b400b-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="b400b-119">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="b400b-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="b400b-120">Hora da criação.</span><span class="sxs-lookup"><span data-stu-id="b400b-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b400b-121">As</span><span class="sxs-lookup"><span data-stu-id="b400b-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b400b-122">Coluna</span><span class="sxs-lookup"><span data-stu-id="b400b-122">Column</span></span></th>
<th><span data-ttu-id="b400b-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="b400b-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b400b-124">&lt;, NodeId&gt;</span><span class="sxs-lookup"><span data-stu-id="b400b-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="b400b-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="b400b-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b400b-126">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="b400b-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="b400b-127">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="b400b-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b400b-128">NodeId</span><span class="sxs-lookup"><span data-stu-id="b400b-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="b400b-129">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="b400b-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

