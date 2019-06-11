---
title: 'Lync Server 2013: tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece5ae542060835aefa05edb6e08b766293e2ac1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="d0408-102">tblScopePrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0408-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0408-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d0408-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d0408-104">tblScopePrincipal contém escopos atribuídos a nós.</span><span class="sxs-lookup"><span data-stu-id="d0408-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="d0408-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="d0408-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0408-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="d0408-106">Column</span></span></th>
<th><span data-ttu-id="d0408-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="d0408-107">Type</span></span></th>
<th><span data-ttu-id="d0408-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="d0408-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0408-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="d0408-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="d0408-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d0408-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d0408-111">ID do nó ao qual o escopo se aplica.</span><span class="sxs-lookup"><span data-stu-id="d0408-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0408-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="d0408-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="d0408-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d0408-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d0408-114">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="d0408-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0408-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="d0408-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="d0408-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="d0408-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d0408-117">Verdadeiro se o tipo de escopo for negar; Falso se permitir.</span><span class="sxs-lookup"><span data-stu-id="d0408-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0408-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="d0408-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="d0408-119">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d0408-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d0408-120">ID da entidade de segurança que atualizou pela última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="d0408-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d0408-121">As</span><span class="sxs-lookup"><span data-stu-id="d0408-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0408-122">Coluna</span><span class="sxs-lookup"><span data-stu-id="d0408-122">Column</span></span></th>
<th><span data-ttu-id="d0408-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="d0408-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0408-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="d0408-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="d0408-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="d0408-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0408-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="d0408-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="d0408-127">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="d0408-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0408-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="d0408-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="d0408-129">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="d0408-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

