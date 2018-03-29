---
title: tblEnumValue
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: a tabela tblEnumValue é uma tabela embutida em código que contém os valores de visibilidade e comportamento dos atributos que são usados na tabela Node.
ms.openlocfilehash: 4957f87401dc93cc98d18fa5b1844e13daaefabd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumvalue"></a><span data-ttu-id="afc22-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="afc22-103">tblEnumValue</span></span>
 
<span data-ttu-id="afc22-104">a tabela tblEnumValue é uma tabela embutida em código que contém os valores de visibilidade e comportamento dos atributos que são usados na tabela Node.</span><span class="sxs-lookup"><span data-stu-id="afc22-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="afc22-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="afc22-105">**Columns**</span></span>

|<span data-ttu-id="afc22-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="afc22-106">**Column**</span></span>|<span data-ttu-id="afc22-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="afc22-107">**Type**</span></span>|<span data-ttu-id="afc22-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="afc22-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="afc22-109">valueID</span><span class="sxs-lookup"><span data-stu-id="afc22-109">valueID</span></span>  <br/> |<span data-ttu-id="afc22-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="afc22-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="afc22-111">ID do valor.</span><span class="sxs-lookup"><span data-stu-id="afc22-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="afc22-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="afc22-112">attributeID</span></span>  <br/> |<span data-ttu-id="afc22-113">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="afc22-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="afc22-114">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="afc22-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="afc22-115">valor de atributo</span><span class="sxs-lookup"><span data-stu-id="afc22-115">attributeValue</span></span>  <br/> |<span data-ttu-id="afc22-116">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="afc22-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="afc22-117">Nome do valor.</span><span class="sxs-lookup"><span data-stu-id="afc22-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="afc22-118">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="afc22-118">**Keys**</span></span>

|<span data-ttu-id="afc22-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="afc22-119">**Column**</span></span>|<span data-ttu-id="afc22-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="afc22-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="afc22-121">valueID</span><span class="sxs-lookup"><span data-stu-id="afc22-121">valueID</span></span>  <br/> |<span data-ttu-id="afc22-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="afc22-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="afc22-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="afc22-123">attributeID</span></span>  <br/> |<span data-ttu-id="afc22-124">Chave estrangeira com pesquisa na tabela Tblenumattribute.</span><span class="sxs-lookup"><span data-stu-id="afc22-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="afc22-125">**Valores da tabela**</span><span class="sxs-lookup"><span data-stu-id="afc22-125">**Table Values**</span></span>

|<span data-ttu-id="afc22-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="afc22-126">**valueID**</span></span>|<span data-ttu-id="afc22-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="afc22-127">**attributeID**</span></span>|<span data-ttu-id="afc22-128">**valor de atributo**</span><span class="sxs-lookup"><span data-stu-id="afc22-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="afc22-129">2</span><span class="sxs-lookup"><span data-stu-id="afc22-129">2</span></span>  <br/> |<span data-ttu-id="afc22-130">1</span><span class="sxs-lookup"><span data-stu-id="afc22-130">1</span></span>  <br/> |<span data-ttu-id="afc22-131">private</span><span class="sxs-lookup"><span data-stu-id="afc22-131">private</span></span>  <br/> |
|<span data-ttu-id="afc22-132">3</span><span class="sxs-lookup"><span data-stu-id="afc22-132">3</span></span>  <br/> |<span data-ttu-id="afc22-133">1</span><span class="sxs-lookup"><span data-stu-id="afc22-133">1</span></span>  <br/> |<span data-ttu-id="afc22-134">escopo</span><span class="sxs-lookup"><span data-stu-id="afc22-134">scope</span></span>  <br/> |
|<span data-ttu-id="afc22-135">4</span><span class="sxs-lookup"><span data-stu-id="afc22-135">4</span></span>  <br/> |<span data-ttu-id="afc22-136">2</span><span class="sxs-lookup"><span data-stu-id="afc22-136">2</span></span>  <br/> |<span data-ttu-id="afc22-137">normal</span><span class="sxs-lookup"><span data-stu-id="afc22-137">normal</span></span>  <br/> |
|<span data-ttu-id="afc22-138">5</span><span class="sxs-lookup"><span data-stu-id="afc22-138">5</span></span>  <br/> |<span data-ttu-id="afc22-139">2</span><span class="sxs-lookup"><span data-stu-id="afc22-139">2</span></span>  <br/> |<span data-ttu-id="afc22-140">auditório</span><span class="sxs-lookup"><span data-stu-id="afc22-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="afc22-141">6</span><span class="sxs-lookup"><span data-stu-id="afc22-141">6</span></span>  <br/> |<span data-ttu-id="afc22-142">1</span><span class="sxs-lookup"><span data-stu-id="afc22-142">1</span></span>  <br/> |<span data-ttu-id="afc22-143">Abrir</span><span class="sxs-lookup"><span data-stu-id="afc22-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="afc22-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="afc22-144">See also</span></span>

#### 

[<span data-ttu-id="afc22-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="afc22-145">tblNode</span></span>](tblnode.md)

