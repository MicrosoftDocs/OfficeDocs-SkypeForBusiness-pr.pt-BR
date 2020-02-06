---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contém escopos atribuídos a nós.
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812439"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="3c1a7-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="3c1a7-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="3c1a7-104">tblScopePrincipal contém escopos atribuídos a nós.</span><span class="sxs-lookup"><span data-stu-id="3c1a7-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="3c1a7-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="3c1a7-105">**Columns**</span></span>

|<span data-ttu-id="3c1a7-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3c1a7-106">**Column**</span></span>|<span data-ttu-id="3c1a7-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3c1a7-107">**Type**</span></span>|<span data-ttu-id="3c1a7-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3c1a7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3c1a7-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="3c1a7-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="3c1a7-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="3c1a7-110">int, not null</span></span>  <br/> |<span data-ttu-id="3c1a7-111">ID do nó ao qual o escopo se aplica.</span><span class="sxs-lookup"><span data-stu-id="3c1a7-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="3c1a7-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="3c1a7-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="3c1a7-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="3c1a7-113">int, not null</span></span>  <br/> |<span data-ttu-id="3c1a7-114">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="3c1a7-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="3c1a7-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="3c1a7-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="3c1a7-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="3c1a7-116">bit, not null</span></span>  <br/> |<span data-ttu-id="3c1a7-117">Verdadeiro se o tipo de escopo for negar; Falso se permitir.</span><span class="sxs-lookup"><span data-stu-id="3c1a7-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="3c1a7-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="3c1a7-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="3c1a7-119">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="3c1a7-119">int, not null</span></span>  <br/> |<span data-ttu-id="3c1a7-120">ID da entidade de segurança que atualizou pela última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="3c1a7-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="3c1a7-121">**As**</span><span class="sxs-lookup"><span data-stu-id="3c1a7-121">**Keys**</span></span>

|<span data-ttu-id="3c1a7-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3c1a7-122">**Column**</span></span>|<span data-ttu-id="3c1a7-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3c1a7-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3c1a7-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="3c1a7-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="3c1a7-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="3c1a7-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3c1a7-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="3c1a7-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="3c1a7-127">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="3c1a7-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="3c1a7-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="3c1a7-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="3c1a7-129">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="3c1a7-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

