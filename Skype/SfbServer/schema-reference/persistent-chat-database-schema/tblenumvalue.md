---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue é uma tabela codificada que contém os valores de visibilidade e comportamento dos atributos usados na tabela de nós.
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295423"
---
# <a name="tblenumvalue"></a><span data-ttu-id="0f945-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="0f945-103">tblEnumValue</span></span>
 
<span data-ttu-id="0f945-104">tblEnumValue é uma tabela codificada que contém os valores de visibilidade e comportamento dos atributos usados na tabela de nós.</span><span class="sxs-lookup"><span data-stu-id="0f945-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="0f945-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="0f945-105">**Columns**</span></span>

|<span data-ttu-id="0f945-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="0f945-106">**Column**</span></span>|<span data-ttu-id="0f945-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0f945-107">**Type**</span></span>|<span data-ttu-id="0f945-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0f945-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0f945-109">valueid</span><span class="sxs-lookup"><span data-stu-id="0f945-109">valueID</span></span>  <br/> |<span data-ttu-id="0f945-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="0f945-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="0f945-111">ID do valor.</span><span class="sxs-lookup"><span data-stu-id="0f945-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="0f945-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="0f945-112">attributeID</span></span>  <br/> |<span data-ttu-id="0f945-113">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="0f945-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="0f945-114">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="0f945-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="0f945-115">atributovalue</span><span class="sxs-lookup"><span data-stu-id="0f945-115">attributeValue</span></span>  <br/> |<span data-ttu-id="0f945-116">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="0f945-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="0f945-117">Nome do valor.</span><span class="sxs-lookup"><span data-stu-id="0f945-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="0f945-118">**As**</span><span class="sxs-lookup"><span data-stu-id="0f945-118">**Keys**</span></span>

|<span data-ttu-id="0f945-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="0f945-119">**Column**</span></span>|<span data-ttu-id="0f945-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0f945-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0f945-121">valueid</span><span class="sxs-lookup"><span data-stu-id="0f945-121">valueID</span></span>  <br/> |<span data-ttu-id="0f945-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="0f945-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0f945-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="0f945-123">attributeID</span></span>  <br/> |<span data-ttu-id="0f945-124">Chave estrangeira com pesquisa na tabela tblEnumAttribute. attributeID.</span><span class="sxs-lookup"><span data-stu-id="0f945-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="0f945-125">**Valores da tabela**</span><span class="sxs-lookup"><span data-stu-id="0f945-125">**Table Values**</span></span>

|<span data-ttu-id="0f945-126">**valueid**</span><span class="sxs-lookup"><span data-stu-id="0f945-126">**valueID**</span></span>|<span data-ttu-id="0f945-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="0f945-127">**attributeID**</span></span>|<span data-ttu-id="0f945-128">**atributovalue**</span><span class="sxs-lookup"><span data-stu-id="0f945-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0f945-129">2</span><span class="sxs-lookup"><span data-stu-id="0f945-129">2</span></span>  <br/> |<span data-ttu-id="0f945-130">1</span><span class="sxs-lookup"><span data-stu-id="0f945-130">1</span></span>  <br/> |<span data-ttu-id="0f945-131">private</span><span class="sxs-lookup"><span data-stu-id="0f945-131">private</span></span>  <br/> |
|<span data-ttu-id="0f945-132">3</span><span class="sxs-lookup"><span data-stu-id="0f945-132">3</span></span>  <br/> |<span data-ttu-id="0f945-133">1</span><span class="sxs-lookup"><span data-stu-id="0f945-133">1</span></span>  <br/> |<span data-ttu-id="0f945-134">com</span><span class="sxs-lookup"><span data-stu-id="0f945-134">scope</span></span>  <br/> |
|<span data-ttu-id="0f945-135">4</span><span class="sxs-lookup"><span data-stu-id="0f945-135">4</span></span>  <br/> |<span data-ttu-id="0f945-136">2</span><span class="sxs-lookup"><span data-stu-id="0f945-136">2</span></span>  <br/> |<span data-ttu-id="0f945-137">Normalmente</span><span class="sxs-lookup"><span data-stu-id="0f945-137">normal</span></span>  <br/> |
|<span data-ttu-id="0f945-138">5</span><span class="sxs-lookup"><span data-stu-id="0f945-138">5</span></span>  <br/> |<span data-ttu-id="0f945-139">2</span><span class="sxs-lookup"><span data-stu-id="0f945-139">2</span></span>  <br/> |<span data-ttu-id="0f945-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="0f945-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="0f945-141">6</span><span class="sxs-lookup"><span data-stu-id="0f945-141">6</span></span>  <br/> |<span data-ttu-id="0f945-142">1</span><span class="sxs-lookup"><span data-stu-id="0f945-142">1</span></span>  <br/> |<span data-ttu-id="0f945-143">abriu</span><span class="sxs-lookup"><span data-stu-id="0f945-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0f945-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="0f945-144">See also</span></span>

[<span data-ttu-id="0f945-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="0f945-145">tblNode</span></span>](tblnode.md)
