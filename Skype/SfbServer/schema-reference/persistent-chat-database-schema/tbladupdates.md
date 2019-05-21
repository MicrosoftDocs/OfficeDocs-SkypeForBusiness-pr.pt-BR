---
title: tblADUpdates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: o tblADUpdates contém alterações dos serviços de domínio Active Directory que ainda não foram processadas pelas etapas de sincronização posteriores do Active Directory.
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295556"
---
# <a name="tbladupdates"></a><span data-ttu-id="a632f-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="a632f-103">tblADUpdates</span></span>
 
<span data-ttu-id="a632f-104">o tblADUpdates contém alterações dos serviços de domínio Active Directory que ainda não foram processadas pelas etapas de sincronização posteriores do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a632f-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="a632f-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="a632f-105">**Columns**</span></span>

|<span data-ttu-id="a632f-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a632f-106">**Column**</span></span>|<span data-ttu-id="a632f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a632f-107">**Type**</span></span>|<span data-ttu-id="a632f-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a632f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a632f-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="a632f-109">prinGuid</span></span>  <br/> |<span data-ttu-id="a632f-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="a632f-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="a632f-111">O principal GUID do objeto que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="a632f-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="a632f-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="a632f-112">prinADPath</span></span>  <br/> |<span data-ttu-id="a632f-113">nvarchar (384), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="a632f-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="a632f-114">Nome diferenciado do objeto.</span><span class="sxs-lookup"><span data-stu-id="a632f-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="a632f-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="a632f-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="a632f-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="a632f-116">bit, not null</span></span>  <br/> |<span data-ttu-id="a632f-117">True se pelo menos um atributo do objeto foi alterado.</span><span class="sxs-lookup"><span data-stu-id="a632f-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="a632f-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="a632f-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="a632f-119">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="a632f-119">bit, not null</span></span>  <br/> |<span data-ttu-id="a632f-120">Verdadeiro se a associação for alterada.</span><span class="sxs-lookup"><span data-stu-id="a632f-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="a632f-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="a632f-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="a632f-122">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="a632f-122">bit, not null</span></span>  <br/> |<span data-ttu-id="a632f-123">Não usado.</span><span class="sxs-lookup"><span data-stu-id="a632f-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="a632f-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="a632f-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="a632f-125">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="a632f-125">bit, not null</span></span>  <br/> |<span data-ttu-id="a632f-126">Verdadeiro se o objeto foi excluído.</span><span class="sxs-lookup"><span data-stu-id="a632f-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="a632f-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="a632f-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="a632f-128">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="a632f-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="a632f-129">Carimbo de data/hora de quando a linha foi inserida.</span><span class="sxs-lookup"><span data-stu-id="a632f-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

