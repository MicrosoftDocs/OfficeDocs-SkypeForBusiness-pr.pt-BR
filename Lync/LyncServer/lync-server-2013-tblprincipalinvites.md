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
ms.openlocfilehash: cd93043a9120a6de5a0f1da6ad3af64a2a6d38f7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523718"
---
# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="574cf-102">tblPrincipalInvites no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="574cf-102">tblPrincipalInvites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="574cf-103">_**Última modificação do tópico:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="574cf-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="574cf-104">O tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com a opção de convite automático ativada.</span><span class="sxs-lookup"><span data-stu-id="574cf-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="574cf-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="574cf-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="574cf-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="574cf-106">Column</span></span></th>
<th><span data-ttu-id="574cf-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="574cf-107">Type</span></span></th>
<th><span data-ttu-id="574cf-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="574cf-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="574cf-109">prinID</span><span class="sxs-lookup"><span data-stu-id="574cf-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="574cf-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="574cf-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="574cf-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="574cf-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="574cf-112">invID</span><span class="sxs-lookup"><span data-stu-id="574cf-112">invID</span></span></p></td>
<td><p><span data-ttu-id="574cf-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="574cf-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="574cf-114">Número sequencial exclusivo (por ID de entidade) gerado a partir da tabela tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="574cf-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="574cf-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="574cf-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="574cf-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="574cf-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="574cf-117">ID de nó (somente sala de chat).</span><span class="sxs-lookup"><span data-stu-id="574cf-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="574cf-118">Created</span><span class="sxs-lookup"><span data-stu-id="574cf-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="574cf-119">datetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="574cf-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="574cf-120">Hora da criação.</span><span class="sxs-lookup"><span data-stu-id="574cf-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="574cf-121">Chaves</span><span class="sxs-lookup"><span data-stu-id="574cf-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="574cf-122">Coluna</span><span class="sxs-lookup"><span data-stu-id="574cf-122">Column</span></span></th>
<th><span data-ttu-id="574cf-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="574cf-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="574cf-124">&lt;imprimir, NodeId&gt;</span><span class="sxs-lookup"><span data-stu-id="574cf-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="574cf-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="574cf-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="574cf-126">prinID</span><span class="sxs-lookup"><span data-stu-id="574cf-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="574cf-127">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="574cf-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="574cf-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="574cf-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="574cf-129">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="574cf-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

