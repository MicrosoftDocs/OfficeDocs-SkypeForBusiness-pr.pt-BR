---
title: tblScopePrincipal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal inclui os escopos atribuídos a nós.
ms.openlocfilehash: ba2927598cdff07368cb017866ec41bfa7540f48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="db442-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="db442-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="db442-104">tblScopePrincipal inclui os escopos atribuídos a nós.</span><span class="sxs-lookup"><span data-stu-id="db442-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="db442-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="db442-105">**Columns**</span></span>

|<span data-ttu-id="db442-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="db442-106">**Column**</span></span>|<span data-ttu-id="db442-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="db442-107">**Type**</span></span>|<span data-ttu-id="db442-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="db442-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="db442-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="db442-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="db442-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="db442-110">int, not null</span></span>  <br/> |<span data-ttu-id="db442-111">ID do nó de escopo se aplica.</span><span class="sxs-lookup"><span data-stu-id="db442-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="db442-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="db442-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="db442-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="db442-113">int, not null</span></span>  <br/> |<span data-ttu-id="db442-114">ID principal.</span><span class="sxs-lookup"><span data-stu-id="db442-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="db442-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="db442-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="db442-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="db442-116">bit, not null</span></span>  <br/> |<span data-ttu-id="db442-117">True se o tipo de escopo for negar; FALSO se for permitir.</span><span class="sxs-lookup"><span data-stu-id="db442-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="db442-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="db442-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="db442-119">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="db442-119">int, not null</span></span>  <br/> |<span data-ttu-id="db442-120">ID da entidade que atualizada pela última vez essa entrada.</span><span class="sxs-lookup"><span data-stu-id="db442-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="db442-121">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="db442-121">**Keys**</span></span>

|<span data-ttu-id="db442-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="db442-122">**Column**</span></span>|<span data-ttu-id="db442-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="db442-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="db442-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="db442-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="db442-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="db442-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="db442-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="db442-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="db442-127">Chave estrangeira com pesquisa na tabela Tblnode.</span><span class="sxs-lookup"><span data-stu-id="db442-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="db442-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="db442-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="db442-129">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="db442-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

