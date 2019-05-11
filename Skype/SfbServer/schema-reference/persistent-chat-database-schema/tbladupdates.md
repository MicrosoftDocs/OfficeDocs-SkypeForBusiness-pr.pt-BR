---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: a tabela tblADUpdates contém alterações de serviços de domínio do Active Directory que ainda não foram processadas pelas etapas posteriores de sincronização do Active Directory.
ms.openlocfilehash: 4ed1abe2d5926c8b34ddccb28133ecc34ddaa03a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929858"
---
# <a name="tbladupdates"></a><span data-ttu-id="abd7b-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="abd7b-103">tblADUpdates</span></span>
 
<span data-ttu-id="abd7b-104">a tabela tblADUpdates contém alterações de serviços de domínio do Active Directory que ainda não foram processadas pelas etapas posteriores de sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="abd7b-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="abd7b-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="abd7b-105">**Columns**</span></span>

|<span data-ttu-id="abd7b-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="abd7b-106">**Column**</span></span>|<span data-ttu-id="abd7b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="abd7b-107">**Type**</span></span>|<span data-ttu-id="abd7b-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="abd7b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="abd7b-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="abd7b-109">prinGuid</span></span>  <br/> |<span data-ttu-id="abd7b-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="abd7b-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="abd7b-111">GUID principal do objeto que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="abd7b-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="abd7b-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="abd7b-112">prinADPath</span></span>  <br/> |<span data-ttu-id="abd7b-113">nvarchar (384), não nulo</span><span class="sxs-lookup"><span data-stu-id="abd7b-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="abd7b-114">Nome distinto do objeto.</span><span class="sxs-lookup"><span data-stu-id="abd7b-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="abd7b-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="abd7b-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="abd7b-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="abd7b-116">bit, not null</span></span>  <br/> |<span data-ttu-id="abd7b-117">True se pelo menos um atributo do objeto é alterado.</span><span class="sxs-lookup"><span data-stu-id="abd7b-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="abd7b-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="abd7b-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="abd7b-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="abd7b-119">bit, not null</span></span>  <br/> |<span data-ttu-id="abd7b-120">True se a associação tiver sido alterada.</span><span class="sxs-lookup"><span data-stu-id="abd7b-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="abd7b-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="abd7b-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="abd7b-122">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="abd7b-122">bit, not null</span></span>  <br/> |<span data-ttu-id="abd7b-123">Não usado.</span><span class="sxs-lookup"><span data-stu-id="abd7b-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="abd7b-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="abd7b-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="abd7b-125">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="abd7b-125">bit, not null</span></span>  <br/> |<span data-ttu-id="abd7b-126">True se o objeto foi excluído.</span><span class="sxs-lookup"><span data-stu-id="abd7b-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="abd7b-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="abd7b-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="abd7b-128">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="abd7b-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="abd7b-129">Carimbo de hora de quando a linha foi inserida.</span><span class="sxs-lookup"><span data-stu-id="abd7b-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

