---
title: tblPrincipalInvites
ms.reviewer: ''
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
ms.openlocfilehash: fbf61265f4970b57ffa95a52c8bafa395fb3a331
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876687"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="39a9a-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="39a9a-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="39a9a-104">tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com convite automático ativada.</span><span class="sxs-lookup"><span data-stu-id="39a9a-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="39a9a-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="39a9a-105">**Columns**</span></span>

|<span data-ttu-id="39a9a-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="39a9a-106">**Column**</span></span>|<span data-ttu-id="39a9a-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="39a9a-107">**Type**</span></span>|<span data-ttu-id="39a9a-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="39a9a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="39a9a-109">prinID</span><span class="sxs-lookup"><span data-stu-id="39a9a-109">prinID</span></span>  <br/> |<span data-ttu-id="39a9a-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="39a9a-110">int, not null</span></span>  <br/> |<span data-ttu-id="39a9a-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="39a9a-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="39a9a-112">invID</span><span class="sxs-lookup"><span data-stu-id="39a9a-112">invID</span></span>  <br/> |<span data-ttu-id="39a9a-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="39a9a-113">int, not null</span></span>  <br/> |<span data-ttu-id="39a9a-114">Número sequencial exclusivo (por ID de entidade) gerado a partir da tabela tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="39a9a-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="39a9a-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="39a9a-115">nodeID</span></span>  <br/> |<span data-ttu-id="39a9a-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="39a9a-116">int, not null</span></span>  <br/> |<span data-ttu-id="39a9a-117">ID do nó (somente sala de chat).</span><span class="sxs-lookup"><span data-stu-id="39a9a-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="39a9a-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="39a9a-118">createdOn</span></span>  <br/> |<span data-ttu-id="39a9a-119">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="39a9a-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="39a9a-120">Hora da criação.</span><span class="sxs-lookup"><span data-stu-id="39a9a-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="39a9a-121">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="39a9a-121">**Keys**</span></span>

|<span data-ttu-id="39a9a-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="39a9a-122">**Column**</span></span>|<span data-ttu-id="39a9a-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="39a9a-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="39a9a-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="39a9a-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="39a9a-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="39a9a-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="39a9a-126">prinID</span><span class="sxs-lookup"><span data-stu-id="39a9a-126">prinID</span></span>  <br/> |<span data-ttu-id="39a9a-127">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="39a9a-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="39a9a-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="39a9a-128">nodeID</span></span>  <br/> |<span data-ttu-id="39a9a-129">Chave estrangeira com pesquisa na tabela Tblnode.</span><span class="sxs-lookup"><span data-stu-id="39a9a-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

