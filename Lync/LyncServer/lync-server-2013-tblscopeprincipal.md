---
title: 'Lync Server 2013: tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72c6f15b2f0a219871436fe4451984abfddc947a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="d671c-102">tblScopePrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d671c-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d671c-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d671c-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d671c-104">tblScopePrincipal contém escopos atribuídos a nós.</span><span class="sxs-lookup"><span data-stu-id="d671c-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="d671c-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="d671c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d671c-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="d671c-106">Column</span></span></th>
<th><span data-ttu-id="d671c-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="d671c-107">Type</span></span></th>
<th><span data-ttu-id="d671c-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="d671c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d671c-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="d671c-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="d671c-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d671c-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d671c-111">ID do nó ao qual o escopo se aplica.</span><span class="sxs-lookup"><span data-stu-id="d671c-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d671c-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="d671c-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="d671c-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d671c-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d671c-114">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="d671c-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d671c-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="d671c-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="d671c-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="d671c-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="d671c-117">Verdadeiro se o tipo de escopo for negar; Falso se permitir.</span><span class="sxs-lookup"><span data-stu-id="d671c-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d671c-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="d671c-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="d671c-119">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d671c-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d671c-120">ID da entidade de segurança que atualizou pela última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="d671c-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d671c-121">As</span><span class="sxs-lookup"><span data-stu-id="d671c-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d671c-122">Coluna</span><span class="sxs-lookup"><span data-stu-id="d671c-122">Column</span></span></th>
<th><span data-ttu-id="d671c-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="d671c-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d671c-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="d671c-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="d671c-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="d671c-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d671c-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="d671c-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="d671c-127">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="d671c-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d671c-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="d671c-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="d671c-129">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="d671c-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

