---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: O tblADUpdates contém alterações dos Serviços de Domínio Active Directory que ainda não foram processadas pelas etapas posteriores de Sincronização do Active Directory.
ms.openlocfilehash: 16bb393eb57e7aaf8d3fea7001157eaabbe70c52
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821381"
---
# <a name="tbladupdates"></a><span data-ttu-id="9ea14-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="9ea14-103">tblADUpdates</span></span>
 
<span data-ttu-id="9ea14-104">O tblADUpdates contém alterações dos Serviços de Domínio Active Directory que ainda não foram processadas pelas etapas posteriores de Sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9ea14-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="9ea14-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="9ea14-105">**Columns**</span></span>

|<span data-ttu-id="9ea14-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9ea14-106">**Column**</span></span>|<span data-ttu-id="9ea14-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9ea14-107">**Type**</span></span>|<span data-ttu-id="9ea14-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9ea14-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9ea14-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="9ea14-109">prinGuid</span></span>  <br/> |<span data-ttu-id="9ea14-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="9ea14-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="9ea14-111">GUID da entidade do objeto que mudou.</span><span class="sxs-lookup"><span data-stu-id="9ea14-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="9ea14-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="9ea14-112">prinADPath</span></span>  <br/> |<span data-ttu-id="9ea14-113">nvarchar (384), não nulo</span><span class="sxs-lookup"><span data-stu-id="9ea14-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="9ea14-114">Nome distinto do objeto.</span><span class="sxs-lookup"><span data-stu-id="9ea14-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="9ea14-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="9ea14-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="9ea14-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="9ea14-116">bit, not null</span></span>  <br/> |<span data-ttu-id="9ea14-117">True se pelo menos um atributo do objeto tiver mudado.</span><span class="sxs-lookup"><span data-stu-id="9ea14-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="9ea14-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="9ea14-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="9ea14-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="9ea14-119">bit, not null</span></span>  <br/> |<span data-ttu-id="9ea14-120">True se a associação tiver sido alterada.</span><span class="sxs-lookup"><span data-stu-id="9ea14-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="9ea14-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="9ea14-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="9ea14-122">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="9ea14-122">bit, not null</span></span>  <br/> |<span data-ttu-id="9ea14-123">Não usado</span><span class="sxs-lookup"><span data-stu-id="9ea14-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="9ea14-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="9ea14-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="9ea14-125">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="9ea14-125">bit, not null</span></span>  <br/> |<span data-ttu-id="9ea14-126">True se o objeto tiver sido excluído.</span><span class="sxs-lookup"><span data-stu-id="9ea14-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="9ea14-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="9ea14-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="9ea14-128">datetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="9ea14-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="9ea14-129">Carimbo de hora de quando a linha foi inserida.</span><span class="sxs-lookup"><span data-stu-id="9ea14-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

