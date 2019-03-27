---
title: tblEnumValue
ms.reviewer: ''
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
ms.openlocfilehash: 579b2747ea753b8a701d11dd806178427cbb27b3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881166"
---
# <a name="tblenumvalue"></a><span data-ttu-id="2c236-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="2c236-103">tblEnumValue</span></span>
 
<span data-ttu-id="2c236-104">a tabela tblEnumValue é uma tabela embutida em código que contém os valores de visibilidade e comportamento dos atributos que são usados na tabela Node.</span><span class="sxs-lookup"><span data-stu-id="2c236-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="2c236-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="2c236-105">**Columns**</span></span>

|<span data-ttu-id="2c236-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2c236-106">**Column**</span></span>|<span data-ttu-id="2c236-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2c236-107">**Type**</span></span>|<span data-ttu-id="2c236-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2c236-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c236-109">valueID</span><span class="sxs-lookup"><span data-stu-id="2c236-109">valueID</span></span>  <br/> |<span data-ttu-id="2c236-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="2c236-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="2c236-111">ID do valor.</span><span class="sxs-lookup"><span data-stu-id="2c236-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="2c236-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="2c236-112">attributeID</span></span>  <br/> |<span data-ttu-id="2c236-113">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="2c236-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="2c236-114">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="2c236-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="2c236-115">valor de atributo</span><span class="sxs-lookup"><span data-stu-id="2c236-115">attributeValue</span></span>  <br/> |<span data-ttu-id="2c236-116">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="2c236-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="2c236-117">Nome do valor.</span><span class="sxs-lookup"><span data-stu-id="2c236-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="2c236-118">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="2c236-118">**Keys**</span></span>

|<span data-ttu-id="2c236-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2c236-119">**Column**</span></span>|<span data-ttu-id="2c236-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2c236-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2c236-121">valueID</span><span class="sxs-lookup"><span data-stu-id="2c236-121">valueID</span></span>  <br/> |<span data-ttu-id="2c236-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="2c236-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2c236-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="2c236-123">attributeID</span></span>  <br/> |<span data-ttu-id="2c236-124">Chave estrangeira com pesquisa na tabela Tblenumattribute.</span><span class="sxs-lookup"><span data-stu-id="2c236-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="2c236-125">**Valores da tabela**</span><span class="sxs-lookup"><span data-stu-id="2c236-125">**Table Values**</span></span>

|<span data-ttu-id="2c236-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="2c236-126">**valueID**</span></span>|<span data-ttu-id="2c236-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="2c236-127">**attributeID**</span></span>|<span data-ttu-id="2c236-128">**valor de atributo**</span><span class="sxs-lookup"><span data-stu-id="2c236-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c236-129">2</span><span class="sxs-lookup"><span data-stu-id="2c236-129">2</span></span>  <br/> |<span data-ttu-id="2c236-130">1</span><span class="sxs-lookup"><span data-stu-id="2c236-130">1</span></span>  <br/> |<span data-ttu-id="2c236-131">private</span><span class="sxs-lookup"><span data-stu-id="2c236-131">private</span></span>  <br/> |
|<span data-ttu-id="2c236-132">3</span><span class="sxs-lookup"><span data-stu-id="2c236-132">3</span></span>  <br/> |<span data-ttu-id="2c236-133">1</span><span class="sxs-lookup"><span data-stu-id="2c236-133">1</span></span>  <br/> |<span data-ttu-id="2c236-134">escopo</span><span class="sxs-lookup"><span data-stu-id="2c236-134">scope</span></span>  <br/> |
|<span data-ttu-id="2c236-135">4</span><span class="sxs-lookup"><span data-stu-id="2c236-135">4</span></span>  <br/> |<span data-ttu-id="2c236-136">2</span><span class="sxs-lookup"><span data-stu-id="2c236-136">2</span></span>  <br/> |<span data-ttu-id="2c236-137">normal</span><span class="sxs-lookup"><span data-stu-id="2c236-137">normal</span></span>  <br/> |
|<span data-ttu-id="2c236-138">5</span><span class="sxs-lookup"><span data-stu-id="2c236-138">5</span></span>  <br/> |<span data-ttu-id="2c236-139">2</span><span class="sxs-lookup"><span data-stu-id="2c236-139">2</span></span>  <br/> |<span data-ttu-id="2c236-140">auditório</span><span class="sxs-lookup"><span data-stu-id="2c236-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="2c236-141">6</span><span class="sxs-lookup"><span data-stu-id="2c236-141">6</span></span>  <br/> |<span data-ttu-id="2c236-142">1</span><span class="sxs-lookup"><span data-stu-id="2c236-142">1</span></span>  <br/> |<span data-ttu-id="2c236-143">Abrir</span><span class="sxs-lookup"><span data-stu-id="2c236-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2c236-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2c236-144">See also</span></span>

[<span data-ttu-id="2c236-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="2c236-145">tblNode</span></span>](tblnode.md)
