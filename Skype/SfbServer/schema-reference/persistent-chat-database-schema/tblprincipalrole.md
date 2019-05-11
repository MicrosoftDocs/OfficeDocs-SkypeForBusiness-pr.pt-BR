---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contém funções explícitas atribuídas a nós.
ms.openlocfilehash: 7c144f2f531af58c7c5693b28b224a2ee4456783
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904178"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="714f4-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="714f4-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="714f4-104">tblPrincipalRole contém funções explícitas atribuídas a nós.</span><span class="sxs-lookup"><span data-stu-id="714f4-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="714f4-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="714f4-105">**Columns**</span></span>

|<span data-ttu-id="714f4-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="714f4-106">**Column**</span></span>|<span data-ttu-id="714f4-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="714f4-107">**Type**</span></span>|<span data-ttu-id="714f4-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="714f4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="714f4-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="714f4-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="714f4-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="714f4-110">int, not null</span></span>  <br/> |<span data-ttu-id="714f4-111">ID do nó ao qual se aplica a função.</span><span class="sxs-lookup"><span data-stu-id="714f4-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="714f4-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="714f4-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="714f4-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="714f4-113">int, not null</span></span>  <br/> |<span data-ttu-id="714f4-114">ID principal.</span><span class="sxs-lookup"><span data-stu-id="714f4-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="714f4-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="714f4-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="714f4-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="714f4-116">int, not null</span></span>  <br/> |<span data-ttu-id="714f4-117">ID do tipo de função (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="714f4-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="714f4-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="714f4-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="714f4-119">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="714f4-119">int, not null</span></span>  <br/> |<span data-ttu-id="714f4-120">ID da entidade que atualizada pela última vez essa entrada.</span><span class="sxs-lookup"><span data-stu-id="714f4-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="714f4-121">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="714f4-121">**Keys**</span></span>

|<span data-ttu-id="714f4-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="714f4-122">**Column**</span></span>|<span data-ttu-id="714f4-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="714f4-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="714f4-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="714f4-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="714f4-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="714f4-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="714f4-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="714f4-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="714f4-127">Chave estrangeira com pesquisa na tabela Tblnode.</span><span class="sxs-lookup"><span data-stu-id="714f4-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="714f4-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="714f4-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="714f4-129">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="714f4-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="714f4-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="714f4-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="714f4-131">Chave estrangeira com pesquisa na tabela Tblroletype.</span><span class="sxs-lookup"><span data-stu-id="714f4-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

