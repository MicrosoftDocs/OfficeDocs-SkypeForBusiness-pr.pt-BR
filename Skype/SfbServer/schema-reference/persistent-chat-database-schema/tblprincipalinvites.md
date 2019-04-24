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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212464"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="f59d1-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="f59d1-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="f59d1-104">tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com convite automático ativada.</span><span class="sxs-lookup"><span data-stu-id="f59d1-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="f59d1-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="f59d1-105">**Columns**</span></span>

|<span data-ttu-id="f59d1-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f59d1-106">**Column**</span></span>|<span data-ttu-id="f59d1-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f59d1-107">**Type**</span></span>|<span data-ttu-id="f59d1-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f59d1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f59d1-109">prinID</span><span class="sxs-lookup"><span data-stu-id="f59d1-109">prinID</span></span>  <br/> |<span data-ttu-id="f59d1-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="f59d1-110">int, not null</span></span>  <br/> |<span data-ttu-id="f59d1-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="f59d1-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f59d1-112">invID</span><span class="sxs-lookup"><span data-stu-id="f59d1-112">invID</span></span>  <br/> |<span data-ttu-id="f59d1-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="f59d1-113">int, not null</span></span>  <br/> |<span data-ttu-id="f59d1-114">Número sequencial exclusivo (por ID de entidade) gerado a partir da tabela tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="f59d1-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="f59d1-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="f59d1-115">nodeID</span></span>  <br/> |<span data-ttu-id="f59d1-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="f59d1-116">int, not null</span></span>  <br/> |<span data-ttu-id="f59d1-117">ID do nó (somente sala de chat).</span><span class="sxs-lookup"><span data-stu-id="f59d1-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="f59d1-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="f59d1-118">createdOn</span></span>  <br/> |<span data-ttu-id="f59d1-119">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="f59d1-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="f59d1-120">Hora da criação.</span><span class="sxs-lookup"><span data-stu-id="f59d1-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="f59d1-121">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="f59d1-121">**Keys**</span></span>

|<span data-ttu-id="f59d1-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f59d1-122">**Column**</span></span>|<span data-ttu-id="f59d1-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f59d1-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f59d1-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="f59d1-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="f59d1-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="f59d1-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f59d1-126">prinID</span><span class="sxs-lookup"><span data-stu-id="f59d1-126">prinID</span></span>  <br/> |<span data-ttu-id="f59d1-127">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="f59d1-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="f59d1-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="f59d1-128">nodeID</span></span>  <br/> |<span data-ttu-id="f59d1-129">Chave estrangeira com pesquisa na tabela Tblnode.</span><span class="sxs-lookup"><span data-stu-id="f59d1-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

