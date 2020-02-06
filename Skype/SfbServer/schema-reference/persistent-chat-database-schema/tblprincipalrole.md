---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contém funções explícitas atribuídas a nós.
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813359"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="9c539-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="9c539-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="9c539-104">tblPrincipalRole contém funções explícitas atribuídas a nós.</span><span class="sxs-lookup"><span data-stu-id="9c539-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="9c539-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="9c539-105">**Columns**</span></span>

|<span data-ttu-id="9c539-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9c539-106">**Column**</span></span>|<span data-ttu-id="9c539-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9c539-107">**Type**</span></span>|<span data-ttu-id="9c539-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9c539-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9c539-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="9c539-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="9c539-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="9c539-110">int, not null</span></span>  <br/> |<span data-ttu-id="9c539-111">ID do nó ao qual a função se aplica.</span><span class="sxs-lookup"><span data-stu-id="9c539-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="9c539-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="9c539-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="9c539-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="9c539-113">int, not null</span></span>  <br/> |<span data-ttu-id="9c539-114">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="9c539-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="9c539-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="9c539-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="9c539-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="9c539-116">int, not null</span></span>  <br/> |<span data-ttu-id="9c539-117">ID do tipo de função (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="9c539-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="9c539-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="9c539-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="9c539-119">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="9c539-119">int, not null</span></span>  <br/> |<span data-ttu-id="9c539-120">ID da entidade de segurança que atualizou pela última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="9c539-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="9c539-121">**As**</span><span class="sxs-lookup"><span data-stu-id="9c539-121">**Keys**</span></span>

|<span data-ttu-id="9c539-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9c539-122">**Column**</span></span>|<span data-ttu-id="9c539-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9c539-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9c539-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="9c539-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="9c539-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="9c539-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="9c539-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="9c539-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="9c539-127">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="9c539-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="9c539-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="9c539-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="9c539-129">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="9c539-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="9c539-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="9c539-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="9c539-131">Chave estrangeira com Lookup na tabela tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="9c539-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

