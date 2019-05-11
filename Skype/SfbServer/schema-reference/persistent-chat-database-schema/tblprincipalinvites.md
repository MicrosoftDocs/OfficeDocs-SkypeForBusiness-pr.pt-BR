---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com convite automático ativada.
ms.openlocfilehash: 5008158dcb1c62c766162595d9bffe1875d56514
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924420"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="60483-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="60483-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="60483-104">tblPrincipalInvites inclui convites para todos os usuários provisionados de todos os nós com convite automático ativada.</span><span class="sxs-lookup"><span data-stu-id="60483-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="60483-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="60483-105">**Columns**</span></span>

|<span data-ttu-id="60483-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="60483-106">**Column**</span></span>|<span data-ttu-id="60483-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="60483-107">**Type**</span></span>|<span data-ttu-id="60483-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="60483-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="60483-109">prinID</span><span class="sxs-lookup"><span data-stu-id="60483-109">prinID</span></span>  <br/> |<span data-ttu-id="60483-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="60483-110">int, not null</span></span>  <br/> |<span data-ttu-id="60483-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="60483-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="60483-112">invID</span><span class="sxs-lookup"><span data-stu-id="60483-112">invID</span></span>  <br/> |<span data-ttu-id="60483-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="60483-113">int, not null</span></span>  <br/> |<span data-ttu-id="60483-114">Número sequencial exclusivo (por ID de entidade) gerado a partir da tabela tblLastInviteId.</span><span class="sxs-lookup"><span data-stu-id="60483-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="60483-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="60483-115">nodeID</span></span>  <br/> |<span data-ttu-id="60483-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="60483-116">int, not null</span></span>  <br/> |<span data-ttu-id="60483-117">ID do nó (somente sala de chat).</span><span class="sxs-lookup"><span data-stu-id="60483-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="60483-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="60483-118">createdOn</span></span>  <br/> |<span data-ttu-id="60483-119">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="60483-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="60483-120">Hora da criação.</span><span class="sxs-lookup"><span data-stu-id="60483-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="60483-121">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="60483-121">**Keys**</span></span>

|<span data-ttu-id="60483-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="60483-122">**Column**</span></span>|<span data-ttu-id="60483-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="60483-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="60483-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="60483-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="60483-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="60483-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="60483-126">prinID</span><span class="sxs-lookup"><span data-stu-id="60483-126">prinID</span></span>  <br/> |<span data-ttu-id="60483-127">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="60483-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="60483-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="60483-128">nodeID</span></span>  <br/> |<span data-ttu-id="60483-129">Chave estrangeira com pesquisa na tabela Tblnode.</span><span class="sxs-lookup"><span data-stu-id="60483-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

