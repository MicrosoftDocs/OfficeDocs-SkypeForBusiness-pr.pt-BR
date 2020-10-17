---
title: 'Lync Server 2013: tblPrincipalInvites'
description: 'Lync Server 2013: tblPrincipalInvites.'
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
ms.openlocfilehash: d30d741864ed2a3cfbec8329215be33c21b3b262
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564667"
---
# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="8dfa3-103">tblPrincipalInvites no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dfa3-103">tblPrincipalInvites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dfa3-104">_**Última modificação do tópico:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="8dfa3-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="8dfa3-105">O tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com a opção de convite automático ativada.</span><span class="sxs-lookup"><span data-stu-id="8dfa3-105">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="8dfa3-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="8dfa3-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dfa3-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="8dfa3-107">Column</span></span></th>
<th><span data-ttu-id="8dfa3-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="8dfa3-108">Type</span></span></th>
<th><span data-ttu-id="8dfa3-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="8dfa3-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dfa3-110">prinID</span><span class="sxs-lookup"><span data-stu-id="8dfa3-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="8dfa3-111">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="8dfa3-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8dfa3-112">ID principal.</span><span class="sxs-lookup"><span data-stu-id="8dfa3-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dfa3-113">invID</span><span class="sxs-lookup"><span data-stu-id="8dfa3-113">invID</span></span></p></td>
<td><p><span data-ttu-id="8dfa3-114">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="8dfa3-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8dfa3-115">Número sequencial exclusivo (por ID de entidade) gerado a partir da tabela tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="8dfa3-115">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dfa3-116">nodeID</span><span class="sxs-lookup"><span data-stu-id="8dfa3-116">nodeID</span></span></p></td>
<td><p><span data-ttu-id="8dfa3-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="8dfa3-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8dfa3-118">ID de nó (somente sala de chat).</span><span class="sxs-lookup"><span data-stu-id="8dfa3-118">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dfa3-119">Created</span><span class="sxs-lookup"><span data-stu-id="8dfa3-119">createdOn</span></span></p></td>
<td><p><span data-ttu-id="8dfa3-120">datetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="8dfa3-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="8dfa3-121">Hora da criação.</span><span class="sxs-lookup"><span data-stu-id="8dfa3-121">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="8dfa3-122">Chaves</span><span class="sxs-lookup"><span data-stu-id="8dfa3-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dfa3-123">Coluna</span><span class="sxs-lookup"><span data-stu-id="8dfa3-123">Column</span></span></th>
<th><span data-ttu-id="8dfa3-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="8dfa3-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dfa3-125">&lt;imprimir, NodeId&gt;</span><span class="sxs-lookup"><span data-stu-id="8dfa3-125">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="8dfa3-126">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="8dfa3-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dfa3-127">prinID</span><span class="sxs-lookup"><span data-stu-id="8dfa3-127">prinID</span></span></p></td>
<td><p><span data-ttu-id="8dfa3-128">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="8dfa3-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dfa3-129">nodeID</span><span class="sxs-lookup"><span data-stu-id="8dfa3-129">nodeID</span></span></p></td>
<td><p><span data-ttu-id="8dfa3-130">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="8dfa3-130">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

