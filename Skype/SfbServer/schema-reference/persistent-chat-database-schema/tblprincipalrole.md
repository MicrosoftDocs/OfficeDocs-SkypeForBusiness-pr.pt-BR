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
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole contém funções explícitas atribuídas a nós.
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295234"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="5c5ef-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="5c5ef-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="5c5ef-104">tblPrincipalRole contém funções explícitas atribuídas a nós.</span><span class="sxs-lookup"><span data-stu-id="5c5ef-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="5c5ef-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="5c5ef-105">**Columns**</span></span>

|<span data-ttu-id="5c5ef-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="5c5ef-106">**Column**</span></span>|<span data-ttu-id="5c5ef-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5c5ef-107">**Type**</span></span>|<span data-ttu-id="5c5ef-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="5c5ef-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5c5ef-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="5c5ef-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="5c5ef-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="5c5ef-110">int, not null</span></span>  <br/> |<span data-ttu-id="5c5ef-111">ID do nó ao qual a função se aplica.</span><span class="sxs-lookup"><span data-stu-id="5c5ef-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="5c5ef-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="5c5ef-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="5c5ef-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="5c5ef-113">int, not null</span></span>  <br/> |<span data-ttu-id="5c5ef-114">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="5c5ef-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5c5ef-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="5c5ef-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="5c5ef-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="5c5ef-116">int, not null</span></span>  <br/> |<span data-ttu-id="5c5ef-117">ID do tipo de função (de tblRoleType).</span><span class="sxs-lookup"><span data-stu-id="5c5ef-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="5c5ef-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="5c5ef-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="5c5ef-119">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="5c5ef-119">int, not null</span></span>  <br/> |<span data-ttu-id="5c5ef-120">ID da entidade de segurança que atualizou pela última vez esta entrada.</span><span class="sxs-lookup"><span data-stu-id="5c5ef-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="5c5ef-121">**As**</span><span class="sxs-lookup"><span data-stu-id="5c5ef-121">**Keys**</span></span>

|<span data-ttu-id="5c5ef-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="5c5ef-122">**Column**</span></span>|<span data-ttu-id="5c5ef-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="5c5ef-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c5ef-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="5c5ef-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="5c5ef-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="5c5ef-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5c5ef-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="5c5ef-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="5c5ef-127">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="5c5ef-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="5c5ef-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="5c5ef-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="5c5ef-129">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="5c5ef-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="5c5ef-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="5c5ef-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="5c5ef-131">Chave estrangeira com Lookup na tabela tblRoleType. rtypeID.</span><span class="sxs-lookup"><span data-stu-id="5c5ef-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

