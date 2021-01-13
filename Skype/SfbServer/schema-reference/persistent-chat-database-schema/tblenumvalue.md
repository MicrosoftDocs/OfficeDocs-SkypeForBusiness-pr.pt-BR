---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: A tabela tblEnumValue é uma tabela embutida em código que contém os valores de Visibilidade e Comportamento dos atributos usados na tabela Nó.
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816021"
---
# <a name="tblenumvalue"></a><span data-ttu-id="060e4-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="060e4-103">tblEnumValue</span></span>
 
<span data-ttu-id="060e4-104">A tabela tblEnumValue é uma tabela embutida em código que contém os valores de Visibilidade e Comportamento dos atributos usados na tabela Nó.</span><span class="sxs-lookup"><span data-stu-id="060e4-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="060e4-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="060e4-105">**Columns**</span></span>

|<span data-ttu-id="060e4-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="060e4-106">**Column**</span></span>|<span data-ttu-id="060e4-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="060e4-107">**Type**</span></span>|<span data-ttu-id="060e4-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="060e4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="060e4-109">valueID</span><span class="sxs-lookup"><span data-stu-id="060e4-109">valueID</span></span>  <br/> |<span data-ttu-id="060e4-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="060e4-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="060e4-111">ID do valor.</span><span class="sxs-lookup"><span data-stu-id="060e4-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="060e4-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="060e4-112">attributeID</span></span>  <br/> |<span data-ttu-id="060e4-113">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="060e4-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="060e4-114">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="060e4-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="060e4-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="060e4-115">attributeValue</span></span>  <br/> |<span data-ttu-id="060e4-116">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="060e4-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="060e4-117">Nome do valor.</span><span class="sxs-lookup"><span data-stu-id="060e4-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="060e4-118">**Teclas**</span><span class="sxs-lookup"><span data-stu-id="060e4-118">**Keys**</span></span>

|<span data-ttu-id="060e4-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="060e4-119">**Column**</span></span>|<span data-ttu-id="060e4-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="060e4-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="060e4-121">valueID</span><span class="sxs-lookup"><span data-stu-id="060e4-121">valueID</span></span>  <br/> |<span data-ttu-id="060e4-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="060e4-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="060e4-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="060e4-123">attributeID</span></span>  <br/> |<span data-ttu-id="060e4-124">Chave estrangeira com pesquisa na tabela tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="060e4-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="060e4-125">**Valores da tabela**</span><span class="sxs-lookup"><span data-stu-id="060e4-125">**Table Values**</span></span>

|<span data-ttu-id="060e4-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="060e4-126">**valueID**</span></span>|<span data-ttu-id="060e4-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="060e4-127">**attributeID**</span></span>|<span data-ttu-id="060e4-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="060e4-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="060e4-129">2 </span><span class="sxs-lookup"><span data-stu-id="060e4-129">2</span></span>  <br/> |<span data-ttu-id="060e4-130">1 </span><span class="sxs-lookup"><span data-stu-id="060e4-130">1</span></span>  <br/> |<span data-ttu-id="060e4-131">private</span><span class="sxs-lookup"><span data-stu-id="060e4-131">private</span></span>  <br/> |
|<span data-ttu-id="060e4-132">3 </span><span class="sxs-lookup"><span data-stu-id="060e4-132">3</span></span>  <br/> |<span data-ttu-id="060e4-133">1 </span><span class="sxs-lookup"><span data-stu-id="060e4-133">1</span></span>  <br/> |<span data-ttu-id="060e4-134">escopo</span><span class="sxs-lookup"><span data-stu-id="060e4-134">scope</span></span>  <br/> |
|<span data-ttu-id="060e4-135">4 </span><span class="sxs-lookup"><span data-stu-id="060e4-135">4</span></span>  <br/> |<span data-ttu-id="060e4-136">2 </span><span class="sxs-lookup"><span data-stu-id="060e4-136">2</span></span>  <br/> |<span data-ttu-id="060e4-137">normal</span><span class="sxs-lookup"><span data-stu-id="060e4-137">normal</span></span>  <br/> |
|<span data-ttu-id="060e4-138">5 </span><span class="sxs-lookup"><span data-stu-id="060e4-138">5</span></span>  <br/> |<span data-ttu-id="060e4-139">2 </span><span class="sxs-lookup"><span data-stu-id="060e4-139">2</span></span>  <br/> |<span data-ttu-id="060e4-140">auditório</span><span class="sxs-lookup"><span data-stu-id="060e4-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="060e4-141">6 </span><span class="sxs-lookup"><span data-stu-id="060e4-141">6</span></span>  <br/> |<span data-ttu-id="060e4-142">1 </span><span class="sxs-lookup"><span data-stu-id="060e4-142">1</span></span>  <br/> |<span data-ttu-id="060e4-143">abrir</span><span class="sxs-lookup"><span data-stu-id="060e4-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="060e4-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="060e4-144">See also</span></span>

[<span data-ttu-id="060e4-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="060e4-145">tblNode</span></span>](tblnode.md)
