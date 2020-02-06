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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contém convites para todos os usuários provisionados para todos os nós com convite automático ativado.
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814179"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="d2df9-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="d2df9-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="d2df9-104">tblPrincipalInvites contém convites para todos os usuários provisionados para todos os nós com convite automático ativado.</span><span class="sxs-lookup"><span data-stu-id="d2df9-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="d2df9-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="d2df9-105">**Columns**</span></span>

|<span data-ttu-id="d2df9-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d2df9-106">**Column**</span></span>|<span data-ttu-id="d2df9-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d2df9-107">**Type**</span></span>|<span data-ttu-id="d2df9-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d2df9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d2df9-109">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="d2df9-109">prinID</span></span>  <br/> |<span data-ttu-id="d2df9-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d2df9-110">int, not null</span></span>  <br/> |<span data-ttu-id="d2df9-111">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="d2df9-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d2df9-112">invID</span><span class="sxs-lookup"><span data-stu-id="d2df9-112">invID</span></span>  <br/> |<span data-ttu-id="d2df9-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d2df9-113">int, not null</span></span>  <br/> |<span data-ttu-id="d2df9-114">Número seqüencial exclusivo (por ID da entidade) gerado pela tabela tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="d2df9-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="d2df9-115">NodeId</span><span class="sxs-lookup"><span data-stu-id="d2df9-115">nodeID</span></span>  <br/> |<span data-ttu-id="d2df9-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d2df9-116">int, not null</span></span>  <br/> |<span data-ttu-id="d2df9-117">ID do nó (somente sala de chat).</span><span class="sxs-lookup"><span data-stu-id="d2df9-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="d2df9-118">criar</span><span class="sxs-lookup"><span data-stu-id="d2df9-118">createdOn</span></span>  <br/> |<span data-ttu-id="d2df9-119">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="d2df9-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="d2df9-120">Hora da criação.</span><span class="sxs-lookup"><span data-stu-id="d2df9-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="d2df9-121">**As**</span><span class="sxs-lookup"><span data-stu-id="d2df9-121">**Keys**</span></span>

|<span data-ttu-id="d2df9-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d2df9-122">**Column**</span></span>|<span data-ttu-id="d2df9-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d2df9-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d2df9-124">\<, NodeId\></span><span class="sxs-lookup"><span data-stu-id="d2df9-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="d2df9-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="d2df9-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d2df9-126">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="d2df9-126">prinID</span></span>  <br/> |<span data-ttu-id="d2df9-127">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="d2df9-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="d2df9-128">NodeId</span><span class="sxs-lookup"><span data-stu-id="d2df9-128">nodeID</span></span>  <br/> |<span data-ttu-id="d2df9-129">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="d2df9-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

