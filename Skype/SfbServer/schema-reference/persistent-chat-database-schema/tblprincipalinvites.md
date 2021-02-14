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
# <a name="tblprincipalinvites"></a><span data-ttu-id="4b22c-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="4b22c-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="4b22c-104">O tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com a opção de convite automático ativada.</span><span class="sxs-lookup"><span data-stu-id="4b22c-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="4b22c-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="4b22c-105">**Columns**</span></span>

|<span data-ttu-id="4b22c-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4b22c-106">**Column**</span></span>|<span data-ttu-id="4b22c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4b22c-107">**Type**</span></span>|<span data-ttu-id="4b22c-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4b22c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4b22c-109">prinID</span><span class="sxs-lookup"><span data-stu-id="4b22c-109">prinID</span></span>  <br/> |<span data-ttu-id="4b22c-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="4b22c-110">int, not null</span></span>  <br/> |<span data-ttu-id="4b22c-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="4b22c-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="4b22c-112">invID</span><span class="sxs-lookup"><span data-stu-id="4b22c-112">invID</span></span>  <br/> |<span data-ttu-id="4b22c-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="4b22c-113">int, not null</span></span>  <br/> |<span data-ttu-id="4b22c-114">Número sequencial exclusivo (por ID de entidade) gerado a partir da tabela tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="4b22c-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="4b22c-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="4b22c-115">nodeID</span></span>  <br/> |<span data-ttu-id="4b22c-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="4b22c-116">int, not null</span></span>  <br/> |<span data-ttu-id="4b22c-117">ID de nó (somente sala de chat).</span><span class="sxs-lookup"><span data-stu-id="4b22c-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="4b22c-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="4b22c-118">createdOn</span></span>  <br/> |<span data-ttu-id="4b22c-119">datetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="4b22c-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="4b22c-120">Hora da criação.</span><span class="sxs-lookup"><span data-stu-id="4b22c-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="4b22c-121">**Teclas**</span><span class="sxs-lookup"><span data-stu-id="4b22c-121">**Keys**</span></span>

|<span data-ttu-id="4b22c-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4b22c-122">**Column**</span></span>|<span data-ttu-id="4b22c-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4b22c-123">**Description**</span></span>|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |<span data-ttu-id="4b22c-124">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="4b22c-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="4b22c-125">prinID</span><span class="sxs-lookup"><span data-stu-id="4b22c-125">prinID</span></span>  <br/> |<span data-ttu-id="4b22c-126">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="4b22c-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="4b22c-127">nodeID</span><span class="sxs-lookup"><span data-stu-id="4b22c-127">nodeID</span></span>  <br/> |<span data-ttu-id="4b22c-128">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="4b22c-128">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

