---
title: a tabela tblADUpdates
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: a tabela tblADUpdates contém alterações de serviços de domínio do Active Directory que ainda não foram processadas pelas etapas posteriores de sincronização do Active Directory.
ms.openlocfilehash: 33d2ae6d2113d3f55b0fdf54439e2383ca142589
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tbladupdates"></a><span data-ttu-id="d4112-103">a tabela tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="d4112-103">tblADUpdates</span></span>
 
<span data-ttu-id="d4112-104">a tabela tblADUpdates contém alterações de serviços de domínio do Active Directory que ainda não foram processadas pelas etapas posteriores de sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d4112-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="d4112-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="d4112-105">**Columns**</span></span>

|<span data-ttu-id="d4112-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d4112-106">**Column**</span></span>|<span data-ttu-id="d4112-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d4112-107">**Type**</span></span>|<span data-ttu-id="d4112-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d4112-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4112-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="d4112-109">prinGuid</span></span>  <br/> |<span data-ttu-id="d4112-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="d4112-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="d4112-111">GUID principal do objeto que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="d4112-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="d4112-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="d4112-112">prinADPath</span></span>  <br/> |<span data-ttu-id="d4112-113">nvarchar (384), não nulo</span><span class="sxs-lookup"><span data-stu-id="d4112-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="d4112-114">Nome distinto do objeto.</span><span class="sxs-lookup"><span data-stu-id="d4112-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="d4112-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="d4112-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="d4112-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="d4112-116">bit, not null</span></span>  <br/> |<span data-ttu-id="d4112-117">True se pelo menos um atributo do objeto é alterado.</span><span class="sxs-lookup"><span data-stu-id="d4112-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="d4112-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="d4112-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="d4112-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="d4112-119">bit, not null</span></span>  <br/> |<span data-ttu-id="d4112-120">True se a associação tiver sido alterada.</span><span class="sxs-lookup"><span data-stu-id="d4112-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="d4112-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="d4112-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="d4112-122">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="d4112-122">bit, not null</span></span>  <br/> |<span data-ttu-id="d4112-123">Não usado.</span><span class="sxs-lookup"><span data-stu-id="d4112-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="d4112-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="d4112-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="d4112-125">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="d4112-125">bit, not null</span></span>  <br/> |<span data-ttu-id="d4112-126">True se o objeto foi excluído.</span><span class="sxs-lookup"><span data-stu-id="d4112-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="d4112-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="d4112-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="d4112-128">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="d4112-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="d4112-129">Carimbo de hora de quando a linha foi inserida.</span><span class="sxs-lookup"><span data-stu-id="d4112-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

