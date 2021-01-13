---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: O tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com a opção de convite automático ativada.
ms.openlocfilehash: 5bbccd582442001bd2122dcbacdbe3634fcfd649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815851"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="228d8-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="228d8-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="228d8-104">O tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com a opção de convite automático ativada.</span><span class="sxs-lookup"><span data-stu-id="228d8-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="228d8-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="228d8-105">**Columns**</span></span>

|<span data-ttu-id="228d8-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="228d8-106">**Column**</span></span>|<span data-ttu-id="228d8-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="228d8-107">**Type**</span></span>|<span data-ttu-id="228d8-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="228d8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="228d8-109">prinID</span><span class="sxs-lookup"><span data-stu-id="228d8-109">prinID</span></span>  <br/> |<span data-ttu-id="228d8-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="228d8-110">int, not null</span></span>  <br/> |<span data-ttu-id="228d8-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="228d8-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="228d8-112">invID</span><span class="sxs-lookup"><span data-stu-id="228d8-112">invID</span></span>  <br/> |<span data-ttu-id="228d8-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="228d8-113">int, not null</span></span>  <br/> |<span data-ttu-id="228d8-114">Número sequencial exclusivo (por ID de entidade) gerado a partir da tabela tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="228d8-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="228d8-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="228d8-115">nodeID</span></span>  <br/> |<span data-ttu-id="228d8-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="228d8-116">int, not null</span></span>  <br/> |<span data-ttu-id="228d8-117">ID de nó (somente sala de chat).</span><span class="sxs-lookup"><span data-stu-id="228d8-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="228d8-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="228d8-118">createdOn</span></span>  <br/> |<span data-ttu-id="228d8-119">datetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="228d8-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="228d8-120">Hora da criação.</span><span class="sxs-lookup"><span data-stu-id="228d8-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="228d8-121">**Teclas**</span><span class="sxs-lookup"><span data-stu-id="228d8-121">**Keys**</span></span>

|<span data-ttu-id="228d8-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="228d8-122">**Column**</span></span>|<span data-ttu-id="228d8-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="228d8-123">**Description**</span></span>|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |<span data-ttu-id="228d8-124">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="228d8-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="228d8-125">prinID</span><span class="sxs-lookup"><span data-stu-id="228d8-125">prinID</span></span>  <br/> |<span data-ttu-id="228d8-126">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="228d8-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="228d8-127">nodeID</span><span class="sxs-lookup"><span data-stu-id="228d8-127">nodeID</span></span>  <br/> |<span data-ttu-id="228d8-128">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="228d8-128">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

