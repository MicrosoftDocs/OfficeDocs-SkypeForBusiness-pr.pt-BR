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
ms.openlocfilehash: ab3faccea0ba914ca17c9aefcd0ea112e5b58a96
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="c62bd-102">tblScopePrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c62bd-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c62bd-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c62bd-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c62bd-104">tblScopePrincipal inclui os escopos atribuídos aos nós.</span><span class="sxs-lookup"><span data-stu-id="c62bd-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="c62bd-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="c62bd-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c62bd-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="c62bd-106">Column</span></span></th>
<th><span data-ttu-id="c62bd-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="c62bd-107">Type</span></span></th>
<th><span data-ttu-id="c62bd-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="c62bd-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c62bd-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="c62bd-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="c62bd-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="c62bd-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c62bd-111">Identificação do nó ao qual o escopo se aplica.</span><span class="sxs-lookup"><span data-stu-id="c62bd-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c62bd-112">ScopeNodeId</span><span class="sxs-lookup"><span data-stu-id="c62bd-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="c62bd-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="c62bd-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c62bd-114">ID da Entidade de Segurança.</span><span class="sxs-lookup"><span data-stu-id="c62bd-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c62bd-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="c62bd-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="c62bd-116">bit, não vazio</span><span class="sxs-lookup"><span data-stu-id="c62bd-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="c62bd-117">Verdadeiro se o tipo de escopo for Negar; falso se for Permitir.</span><span class="sxs-lookup"><span data-stu-id="c62bd-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c62bd-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="c62bd-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="c62bd-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="c62bd-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c62bd-120">ID da entidade de segurança da última atualização dessa entrada.</span><span class="sxs-lookup"><span data-stu-id="c62bd-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="c62bd-121">Chaves</span><span class="sxs-lookup"><span data-stu-id="c62bd-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c62bd-122">Coluna</span><span class="sxs-lookup"><span data-stu-id="c62bd-122">Column</span></span></th>
<th><span data-ttu-id="c62bd-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="c62bd-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c62bd-124">&lt;scopeNodeID, ScopeNodeId&gt;</span><span class="sxs-lookup"><span data-stu-id="c62bd-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="c62bd-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="c62bd-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c62bd-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="c62bd-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="c62bd-127">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="c62bd-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c62bd-128">ScopeNodeId</span><span class="sxs-lookup"><span data-stu-id="c62bd-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="c62bd-129">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="c62bd-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

