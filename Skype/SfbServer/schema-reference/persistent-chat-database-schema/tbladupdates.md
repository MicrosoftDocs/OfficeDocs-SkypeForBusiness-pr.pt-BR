---
title: tblADUpdates
ms.reviewer: ''
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
ms.openlocfilehash: 0e7bde110ad3d0495cb7ddea55e405eac21d96b4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212639"
---
# <a name="tbladupdates"></a><span data-ttu-id="a541f-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="a541f-103">tblADUpdates</span></span>
 
<span data-ttu-id="a541f-104">a tabela tblADUpdates contém alterações de serviços de domínio do Active Directory que ainda não foram processadas pelas etapas posteriores de sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a541f-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="a541f-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="a541f-105">**Columns**</span></span>

|<span data-ttu-id="a541f-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a541f-106">**Column**</span></span>|<span data-ttu-id="a541f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a541f-107">**Type**</span></span>|<span data-ttu-id="a541f-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a541f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a541f-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a541f-109">prinGuid</span></span>  <br/> |<span data-ttu-id="a541f-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="a541f-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="a541f-111">GUID principal do objeto que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="a541f-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="a541f-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="a541f-112">prinADPath</span></span>  <br/> |<span data-ttu-id="a541f-113">nvarchar (384), não nulo</span><span class="sxs-lookup"><span data-stu-id="a541f-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="a541f-114">Nome distinto do objeto.</span><span class="sxs-lookup"><span data-stu-id="a541f-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="a541f-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="a541f-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="a541f-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="a541f-116">bit, not null</span></span>  <br/> |<span data-ttu-id="a541f-117">True se pelo menos um atributo do objeto é alterado.</span><span class="sxs-lookup"><span data-stu-id="a541f-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="a541f-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="a541f-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="a541f-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="a541f-119">bit, not null</span></span>  <br/> |<span data-ttu-id="a541f-120">True se a associação tiver sido alterada.</span><span class="sxs-lookup"><span data-stu-id="a541f-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="a541f-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="a541f-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="a541f-122">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="a541f-122">bit, not null</span></span>  <br/> |<span data-ttu-id="a541f-123">Não usado.</span><span class="sxs-lookup"><span data-stu-id="a541f-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="a541f-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="a541f-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="a541f-125">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="a541f-125">bit, not null</span></span>  <br/> |<span data-ttu-id="a541f-126">True se o objeto foi excluído.</span><span class="sxs-lookup"><span data-stu-id="a541f-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="a541f-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="a541f-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="a541f-128">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="a541f-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="a541f-129">Carimbo de hora de quando a linha foi inserida.</span><span class="sxs-lookup"><span data-stu-id="a541f-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

