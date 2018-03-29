---
title: tblPrincipalInvites
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com convite automático ativada.
ms.openlocfilehash: ae33d45e14340b6374299343f13c8352db1a5021
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="71f11-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="71f11-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="71f11-104">tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com convite automático ativada.</span><span class="sxs-lookup"><span data-stu-id="71f11-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="71f11-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="71f11-105">**Columns**</span></span>

|<span data-ttu-id="71f11-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="71f11-106">**Column**</span></span>|<span data-ttu-id="71f11-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="71f11-107">**Type**</span></span>|<span data-ttu-id="71f11-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="71f11-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="71f11-109">prinID</span><span class="sxs-lookup"><span data-stu-id="71f11-109">prinID</span></span>  <br/> |<span data-ttu-id="71f11-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="71f11-110">int, not null</span></span>  <br/> |<span data-ttu-id="71f11-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="71f11-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="71f11-112">invID</span><span class="sxs-lookup"><span data-stu-id="71f11-112">invID</span></span>  <br/> |<span data-ttu-id="71f11-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="71f11-113">int, not null</span></span>  <br/> |<span data-ttu-id="71f11-114">Número sequencial exclusivo (por ID de entidade) gerado a partir da tabela tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="71f11-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="71f11-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="71f11-115">nodeID</span></span>  <br/> |<span data-ttu-id="71f11-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="71f11-116">int, not null</span></span>  <br/> |<span data-ttu-id="71f11-117">ID do nó (somente sala de chat).</span><span class="sxs-lookup"><span data-stu-id="71f11-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="71f11-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="71f11-118">createdOn</span></span>  <br/> |<span data-ttu-id="71f11-119">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="71f11-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="71f11-120">Hora da criação.</span><span class="sxs-lookup"><span data-stu-id="71f11-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="71f11-121">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="71f11-121">**Keys**</span></span>

|<span data-ttu-id="71f11-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="71f11-122">**Column**</span></span>|<span data-ttu-id="71f11-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="71f11-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="71f11-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="71f11-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="71f11-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="71f11-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="71f11-126">prinID</span><span class="sxs-lookup"><span data-stu-id="71f11-126">prinID</span></span>  <br/> |<span data-ttu-id="71f11-127">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="71f11-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="71f11-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="71f11-128">nodeID</span></span>  <br/> |<span data-ttu-id="71f11-129">Chave estrangeira com pesquisa na tabela Tblnode.</span><span class="sxs-lookup"><span data-stu-id="71f11-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

