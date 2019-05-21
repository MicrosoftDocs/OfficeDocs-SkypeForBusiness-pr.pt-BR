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
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contém escopos atribuídos a nós.
ms.openlocfilehash: 2fd8e434710c7bcd266c427fa492e23adacedb22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295192"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="6d3ca-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="6d3ca-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="6d3ca-104">tblScopePrincipal contém escopos atribuídos a nós.</span><span class="sxs-lookup"><span data-stu-id="6d3ca-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="6d3ca-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="6d3ca-105">**Columns**</span></span>

|<span data-ttu-id="6d3ca-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6d3ca-106">**Column**</span></span>|<span data-ttu-id="6d3ca-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6d3ca-107">**Type**</span></span>|<span data-ttu-id="6d3ca-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6d3ca-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6d3ca-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="6d3ca-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="6d3ca-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6d3ca-110">int, not null</span></span>  <br/> |<span data-ttu-id="6d3ca-111">ID do nó ao qual o escopo se aplica.</span><span class="sxs-lookup"><span data-stu-id="6d3ca-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="6d3ca-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="6d3ca-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="6d3ca-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6d3ca-113">int, not null</span></span>  <br/> |<span data-ttu-id="6d3ca-114">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="6d3ca-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="6d3ca-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="6d3ca-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="6d3ca-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="6d3ca-116">bit, not null</span></span>  <br/> |<span data-ttu-id="6d3ca-117">Verdadeiro se o tipo de escopo for negar; Falso se permitir.</span><span class="sxs-lookup"><span data-stu-id="6d3ca-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="6d3ca-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="6d3ca-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="6d3ca-119">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6d3ca-119">int, not null</span></span>  <br/> |<span data-ttu-id="6d3ca-120">ID da entidade de segurança que atualizou pela última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="6d3ca-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="6d3ca-121">**As**</span><span class="sxs-lookup"><span data-stu-id="6d3ca-121">**Keys**</span></span>

|<span data-ttu-id="6d3ca-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6d3ca-122">**Column**</span></span>|<span data-ttu-id="6d3ca-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6d3ca-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6d3ca-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="6d3ca-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="6d3ca-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="6d3ca-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="6d3ca-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="6d3ca-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="6d3ca-127">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="6d3ca-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="6d3ca-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="6d3ca-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="6d3ca-129">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="6d3ca-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

