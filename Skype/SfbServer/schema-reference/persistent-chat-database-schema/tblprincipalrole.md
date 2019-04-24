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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212450"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="6898a-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="6898a-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="6898a-104">tblPrincipalRole contém funções explícitas atribuídas a nós.</span><span class="sxs-lookup"><span data-stu-id="6898a-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="6898a-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="6898a-105">**Columns**</span></span>

|<span data-ttu-id="6898a-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6898a-106">**Column**</span></span>|<span data-ttu-id="6898a-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6898a-107">**Type**</span></span>|<span data-ttu-id="6898a-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6898a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6898a-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="6898a-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="6898a-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6898a-110">int, not null</span></span>  <br/> |<span data-ttu-id="6898a-111">ID do nó ao qual se aplica a função.</span><span class="sxs-lookup"><span data-stu-id="6898a-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="6898a-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="6898a-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="6898a-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6898a-113">int, not null</span></span>  <br/> |<span data-ttu-id="6898a-114">ID principal.</span><span class="sxs-lookup"><span data-stu-id="6898a-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="6898a-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="6898a-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="6898a-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6898a-116">int, not null</span></span>  <br/> |<span data-ttu-id="6898a-117">ID do tipo de função (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="6898a-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="6898a-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="6898a-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="6898a-119">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6898a-119">int, not null</span></span>  <br/> |<span data-ttu-id="6898a-120">ID da entidade que atualizada pela última vez essa entrada.</span><span class="sxs-lookup"><span data-stu-id="6898a-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="6898a-121">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="6898a-121">**Keys**</span></span>

|<span data-ttu-id="6898a-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6898a-122">**Column**</span></span>|<span data-ttu-id="6898a-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6898a-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6898a-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="6898a-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="6898a-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="6898a-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="6898a-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="6898a-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="6898a-127">Chave estrangeira com pesquisa na tabela Tblnode.</span><span class="sxs-lookup"><span data-stu-id="6898a-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="6898a-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="6898a-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="6898a-129">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="6898a-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="6898a-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="6898a-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="6898a-131">Chave estrangeira com pesquisa na tabela Tblroletype.</span><span class="sxs-lookup"><span data-stu-id="6898a-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

