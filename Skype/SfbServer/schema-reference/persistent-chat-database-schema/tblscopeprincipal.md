---
title: tblScopePrincipal
ms.reviewer: ''
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
ms.openlocfilehash: e93b92280605dfe01f288435c7cb42b724c22064
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885621"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="84912-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="84912-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="84912-104">tblScopePrincipal inclui os escopos atribuídos a nós.</span><span class="sxs-lookup"><span data-stu-id="84912-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="84912-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="84912-105">**Columns**</span></span>

|<span data-ttu-id="84912-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="84912-106">**Column**</span></span>|<span data-ttu-id="84912-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="84912-107">**Type**</span></span>|<span data-ttu-id="84912-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="84912-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="84912-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="84912-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="84912-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="84912-110">int, not null</span></span>  <br/> |<span data-ttu-id="84912-111">ID do nó de escopo se aplica.</span><span class="sxs-lookup"><span data-stu-id="84912-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="84912-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="84912-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="84912-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="84912-113">int, not null</span></span>  <br/> |<span data-ttu-id="84912-114">ID principal.</span><span class="sxs-lookup"><span data-stu-id="84912-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="84912-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="84912-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="84912-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="84912-116">bit, not null</span></span>  <br/> |<span data-ttu-id="84912-117">True se o tipo de escopo for negar; FALSO se for permitir.</span><span class="sxs-lookup"><span data-stu-id="84912-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="84912-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="84912-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="84912-119">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="84912-119">int, not null</span></span>  <br/> |<span data-ttu-id="84912-120">ID da entidade que atualizada pela última vez essa entrada.</span><span class="sxs-lookup"><span data-stu-id="84912-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="84912-121">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="84912-121">**Keys**</span></span>

|<span data-ttu-id="84912-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="84912-122">**Column**</span></span>|<span data-ttu-id="84912-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="84912-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="84912-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="84912-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="84912-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="84912-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="84912-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="84912-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="84912-127">Chave estrangeira com pesquisa na tabela Tblnode.</span><span class="sxs-lookup"><span data-stu-id="84912-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="84912-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="84912-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="84912-129">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="84912-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

