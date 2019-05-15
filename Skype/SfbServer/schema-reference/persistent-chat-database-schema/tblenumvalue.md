---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: a tabela tblEnumValue é uma tabela embutida em código que contém os valores de visibilidade e comportamento dos atributos que são usados na tabela Node.
ms.openlocfilehash: 00ee5a7a7538fa620e438ead5e986f859ef25a6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929865"
---
# <a name="tblenumvalue"></a><span data-ttu-id="71358-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="71358-103">tblEnumValue</span></span>
 
<span data-ttu-id="71358-104">a tabela tblEnumValue é uma tabela embutida em código que contém os valores de visibilidade e comportamento dos atributos que são usados na tabela Node.</span><span class="sxs-lookup"><span data-stu-id="71358-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="71358-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="71358-105">**Columns**</span></span>

|<span data-ttu-id="71358-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="71358-106">**Column**</span></span>|<span data-ttu-id="71358-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="71358-107">**Type**</span></span>|<span data-ttu-id="71358-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="71358-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="71358-109">valueID</span><span class="sxs-lookup"><span data-stu-id="71358-109">valueID</span></span>  <br/> |<span data-ttu-id="71358-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="71358-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="71358-111">ID do valor.</span><span class="sxs-lookup"><span data-stu-id="71358-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="71358-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="71358-112">attributeID</span></span>  <br/> |<span data-ttu-id="71358-113">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="71358-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="71358-114">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="71358-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="71358-115">valor de atributo</span><span class="sxs-lookup"><span data-stu-id="71358-115">attributeValue</span></span>  <br/> |<span data-ttu-id="71358-116">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="71358-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="71358-117">Nome do valor.</span><span class="sxs-lookup"><span data-stu-id="71358-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="71358-118">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="71358-118">**Keys**</span></span>

|<span data-ttu-id="71358-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="71358-119">**Column**</span></span>|<span data-ttu-id="71358-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="71358-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="71358-121">valueID</span><span class="sxs-lookup"><span data-stu-id="71358-121">valueID</span></span>  <br/> |<span data-ttu-id="71358-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="71358-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="71358-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="71358-123">attributeID</span></span>  <br/> |<span data-ttu-id="71358-124">Chave estrangeira com pesquisa na tabela Tblenumattribute.</span><span class="sxs-lookup"><span data-stu-id="71358-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="71358-125">**Valores da tabela**</span><span class="sxs-lookup"><span data-stu-id="71358-125">**Table Values**</span></span>

|<span data-ttu-id="71358-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="71358-126">**valueID**</span></span>|<span data-ttu-id="71358-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="71358-127">**attributeID**</span></span>|<span data-ttu-id="71358-128">**valor de atributo**</span><span class="sxs-lookup"><span data-stu-id="71358-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="71358-129">2</span><span class="sxs-lookup"><span data-stu-id="71358-129">2</span></span>  <br/> |<span data-ttu-id="71358-130">1</span><span class="sxs-lookup"><span data-stu-id="71358-130">1</span></span>  <br/> |<span data-ttu-id="71358-131">private</span><span class="sxs-lookup"><span data-stu-id="71358-131">private</span></span>  <br/> |
|<span data-ttu-id="71358-132">3</span><span class="sxs-lookup"><span data-stu-id="71358-132">3</span></span>  <br/> |<span data-ttu-id="71358-133">1</span><span class="sxs-lookup"><span data-stu-id="71358-133">1</span></span>  <br/> |<span data-ttu-id="71358-134">escopo</span><span class="sxs-lookup"><span data-stu-id="71358-134">scope</span></span>  <br/> |
|<span data-ttu-id="71358-135">4</span><span class="sxs-lookup"><span data-stu-id="71358-135">4</span></span>  <br/> |<span data-ttu-id="71358-136">2</span><span class="sxs-lookup"><span data-stu-id="71358-136">2</span></span>  <br/> |<span data-ttu-id="71358-137">normal</span><span class="sxs-lookup"><span data-stu-id="71358-137">normal</span></span>  <br/> |
|<span data-ttu-id="71358-138">5</span><span class="sxs-lookup"><span data-stu-id="71358-138">5</span></span>  <br/> |<span data-ttu-id="71358-139">2</span><span class="sxs-lookup"><span data-stu-id="71358-139">2</span></span>  <br/> |<span data-ttu-id="71358-140">auditório</span><span class="sxs-lookup"><span data-stu-id="71358-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="71358-141">6</span><span class="sxs-lookup"><span data-stu-id="71358-141">6</span></span>  <br/> |<span data-ttu-id="71358-142">1</span><span class="sxs-lookup"><span data-stu-id="71358-142">1</span></span>  <br/> |<span data-ttu-id="71358-143">Abrir</span><span class="sxs-lookup"><span data-stu-id="71358-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="71358-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="71358-144">See also</span></span>

[<span data-ttu-id="71358-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="71358-145">tblNode</span></span>](tblnode.md)
