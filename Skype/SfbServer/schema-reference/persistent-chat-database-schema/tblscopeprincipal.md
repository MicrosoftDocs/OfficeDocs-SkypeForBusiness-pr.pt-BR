---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal inclui os escopos atribuídos aos nós.
ms.openlocfilehash: efda792ab6f6c6cc7b188a9dffdaa7c324b24797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831511"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="f2d26-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="f2d26-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="f2d26-104">tblScopePrincipal inclui os escopos atribuídos aos nós.</span><span class="sxs-lookup"><span data-stu-id="f2d26-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="f2d26-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="f2d26-105">**Columns**</span></span>

|<span data-ttu-id="f2d26-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f2d26-106">**Column**</span></span>|<span data-ttu-id="f2d26-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f2d26-107">**Type**</span></span>|<span data-ttu-id="f2d26-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f2d26-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f2d26-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="f2d26-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="f2d26-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="f2d26-110">int, not null</span></span>  <br/> |<span data-ttu-id="f2d26-111">Identificação do nó ao qual o escopo se aplica.</span><span class="sxs-lookup"><span data-stu-id="f2d26-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="f2d26-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="f2d26-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="f2d26-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="f2d26-113">int, not null</span></span>  <br/> |<span data-ttu-id="f2d26-114">ID da Entidade de Segurança.</span><span class="sxs-lookup"><span data-stu-id="f2d26-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f2d26-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="f2d26-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="f2d26-116">bit, não vazio</span><span class="sxs-lookup"><span data-stu-id="f2d26-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f2d26-117">Verdadeiro se o tipo de escopo for Negar; falso se for Permitir.</span><span class="sxs-lookup"><span data-stu-id="f2d26-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="f2d26-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="f2d26-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="f2d26-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="f2d26-119">int, not null</span></span>  <br/> |<span data-ttu-id="f2d26-120">ID da entidade de segurança da última atualização dessa entrada.</span><span class="sxs-lookup"><span data-stu-id="f2d26-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="f2d26-121">**Teclas**</span><span class="sxs-lookup"><span data-stu-id="f2d26-121">**Keys**</span></span>

|<span data-ttu-id="f2d26-122">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f2d26-122">**Column**</span></span>|<span data-ttu-id="f2d26-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f2d26-123">**Description**</span></span>|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |<span data-ttu-id="f2d26-124">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="f2d26-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f2d26-125">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="f2d26-125">scopeNodeID</span></span>  <br/> |<span data-ttu-id="f2d26-126">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="f2d26-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="f2d26-127">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="f2d26-127">scopePrinID</span></span>  <br/> |<span data-ttu-id="f2d26-128">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="f2d26-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

