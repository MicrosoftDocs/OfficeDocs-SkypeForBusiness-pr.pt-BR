---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contém funções explícitas atribuídas a nós.
ms.openlocfilehash: 69cfb0cb2b821064801a07510758514bb5d33128
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890766"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="b6d0b-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="b6d0b-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="b6d0b-104">tblPrincipalRole contém funções explícitas atribuídas a nós.</span><span class="sxs-lookup"><span data-stu-id="b6d0b-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="b6d0b-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="b6d0b-105">**Columns**</span></span>

|<span data-ttu-id="b6d0b-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b6d0b-106">**Column**</span></span>|<span data-ttu-id="b6d0b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b6d0b-107">**Type**</span></span>|<span data-ttu-id="b6d0b-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b6d0b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b6d0b-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="b6d0b-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="b6d0b-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="b6d0b-110">int, not null</span></span>  <br/> |<span data-ttu-id="b6d0b-111">ID do nó ao qual se aplica a função.</span><span class="sxs-lookup"><span data-stu-id="b6d0b-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="b6d0b-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="b6d0b-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="b6d0b-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="b6d0b-113">int, not null</span></span>  <br/> |<span data-ttu-id="b6d0b-114">ID principal.</span><span class="sxs-lookup"><span data-stu-id="b6d0b-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b6d0b-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="b6d0b-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="b6d0b-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="b6d0b-116">int, not null</span></span>  <br/> |<span data-ttu-id="b6d0b-117">ID do tipo de função (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="b6d0b-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="b6d0b-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="b6d0b-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="b6d0b-119">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="b6d0b-119">int, not null</span></span>  <br/> |<span data-ttu-id="b6d0b-120">ID da entidade que atualizada pela última vez essa entrada.</span><span class="sxs-lookup"><span data-stu-id="b6d0b-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="b6d0b-121">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="b6d0b-121">**Keys**</span></span>

|<span data-ttu-id="b6d0b-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b6d0b-122">**Column**</span></span>|<span data-ttu-id="b6d0b-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b6d0b-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6d0b-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="b6d0b-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="b6d0b-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="b6d0b-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b6d0b-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="b6d0b-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="b6d0b-127">Chave estrangeira com pesquisa na tabela Tblnode.</span><span class="sxs-lookup"><span data-stu-id="b6d0b-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="b6d0b-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="b6d0b-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="b6d0b-129">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="b6d0b-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="b6d0b-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="b6d0b-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="b6d0b-131">Chave estrangeira com pesquisa na tabela Tblroletype.</span><span class="sxs-lookup"><span data-stu-id="b6d0b-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

