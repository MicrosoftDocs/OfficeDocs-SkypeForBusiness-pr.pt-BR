---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contém convites para todos os usuários provisionados para todos os nós com convite automático ativado.
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295290"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="546ae-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="546ae-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="546ae-104">tblPrincipalInvites contém convites para todos os usuários provisionados para todos os nós com convite automático ativado.</span><span class="sxs-lookup"><span data-stu-id="546ae-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="546ae-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="546ae-105">**Columns**</span></span>

|<span data-ttu-id="546ae-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="546ae-106">**Column**</span></span>|<span data-ttu-id="546ae-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="546ae-107">**Type**</span></span>|<span data-ttu-id="546ae-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="546ae-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="546ae-109">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="546ae-109">prinID</span></span>  <br/> |<span data-ttu-id="546ae-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="546ae-110">int, not null</span></span>  <br/> |<span data-ttu-id="546ae-111">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="546ae-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="546ae-112">invID</span><span class="sxs-lookup"><span data-stu-id="546ae-112">invID</span></span>  <br/> |<span data-ttu-id="546ae-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="546ae-113">int, not null</span></span>  <br/> |<span data-ttu-id="546ae-114">Número seqüencial exclusivo (por ID da entidade) gerado pela tabela tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="546ae-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="546ae-115">NodeId</span><span class="sxs-lookup"><span data-stu-id="546ae-115">nodeID</span></span>  <br/> |<span data-ttu-id="546ae-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="546ae-116">int, not null</span></span>  <br/> |<span data-ttu-id="546ae-117">ID do nó (somente sala de chat).</span><span class="sxs-lookup"><span data-stu-id="546ae-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="546ae-118">criar</span><span class="sxs-lookup"><span data-stu-id="546ae-118">createdOn</span></span>  <br/> |<span data-ttu-id="546ae-119">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="546ae-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="546ae-120">Hora da criação.</span><span class="sxs-lookup"><span data-stu-id="546ae-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="546ae-121">**As**</span><span class="sxs-lookup"><span data-stu-id="546ae-121">**Keys**</span></span>

|<span data-ttu-id="546ae-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="546ae-122">**Column**</span></span>|<span data-ttu-id="546ae-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="546ae-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="546ae-124">\<, NodeId\></span><span class="sxs-lookup"><span data-stu-id="546ae-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="546ae-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="546ae-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="546ae-126">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="546ae-126">prinID</span></span>  <br/> |<span data-ttu-id="546ae-127">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="546ae-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="546ae-128">NodeId</span><span class="sxs-lookup"><span data-stu-id="546ae-128">nodeID</span></span>  <br/> |<span data-ttu-id="546ae-129">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="546ae-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

