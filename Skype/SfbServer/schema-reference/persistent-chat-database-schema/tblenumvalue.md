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
# <a name="tblenumvalue"></a><span data-ttu-id="73453-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="73453-103">tblEnumValue</span></span>
 
<span data-ttu-id="73453-104">A tabela tblEnumValue é uma tabela embutida em código que contém os valores de Visibilidade e Comportamento dos atributos usados na tabela Nó.</span><span class="sxs-lookup"><span data-stu-id="73453-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="73453-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="73453-105">**Columns**</span></span>

|<span data-ttu-id="73453-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="73453-106">**Column**</span></span>|<span data-ttu-id="73453-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="73453-107">**Type**</span></span>|<span data-ttu-id="73453-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="73453-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73453-109">valueID</span><span class="sxs-lookup"><span data-stu-id="73453-109">valueID</span></span>  <br/> |<span data-ttu-id="73453-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="73453-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="73453-111">ID do valor.</span><span class="sxs-lookup"><span data-stu-id="73453-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="73453-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="73453-112">attributeID</span></span>  <br/> |<span data-ttu-id="73453-113">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="73453-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="73453-114">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="73453-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="73453-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="73453-115">attributeValue</span></span>  <br/> |<span data-ttu-id="73453-116">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="73453-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="73453-117">Nome do valor.</span><span class="sxs-lookup"><span data-stu-id="73453-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="73453-118">**Teclas**</span><span class="sxs-lookup"><span data-stu-id="73453-118">**Keys**</span></span>

|<span data-ttu-id="73453-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="73453-119">**Column**</span></span>|<span data-ttu-id="73453-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="73453-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="73453-121">valueID</span><span class="sxs-lookup"><span data-stu-id="73453-121">valueID</span></span>  <br/> |<span data-ttu-id="73453-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="73453-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="73453-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="73453-123">attributeID</span></span>  <br/> |<span data-ttu-id="73453-124">Chave estrangeira com pesquisa na tabela tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="73453-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="73453-125">**Valores da tabela**</span><span class="sxs-lookup"><span data-stu-id="73453-125">**Table Values**</span></span>

|<span data-ttu-id="73453-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="73453-126">**valueID**</span></span>|<span data-ttu-id="73453-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="73453-127">**attributeID**</span></span>|<span data-ttu-id="73453-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="73453-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="73453-129">2 </span><span class="sxs-lookup"><span data-stu-id="73453-129">2</span></span>  <br/> |<span data-ttu-id="73453-130">1 </span><span class="sxs-lookup"><span data-stu-id="73453-130">1</span></span>  <br/> |<span data-ttu-id="73453-131">private</span><span class="sxs-lookup"><span data-stu-id="73453-131">private</span></span>  <br/> |
|<span data-ttu-id="73453-132">3 </span><span class="sxs-lookup"><span data-stu-id="73453-132">3</span></span>  <br/> |<span data-ttu-id="73453-133">1 </span><span class="sxs-lookup"><span data-stu-id="73453-133">1</span></span>  <br/> |<span data-ttu-id="73453-134">escopo</span><span class="sxs-lookup"><span data-stu-id="73453-134">scope</span></span>  <br/> |
|<span data-ttu-id="73453-135">4 </span><span class="sxs-lookup"><span data-stu-id="73453-135">4</span></span>  <br/> |<span data-ttu-id="73453-136">2 </span><span class="sxs-lookup"><span data-stu-id="73453-136">2</span></span>  <br/> |<span data-ttu-id="73453-137">normal</span><span class="sxs-lookup"><span data-stu-id="73453-137">normal</span></span>  <br/> |
|<span data-ttu-id="73453-138">5 </span><span class="sxs-lookup"><span data-stu-id="73453-138">5</span></span>  <br/> |<span data-ttu-id="73453-139">2 </span><span class="sxs-lookup"><span data-stu-id="73453-139">2</span></span>  <br/> |<span data-ttu-id="73453-140">auditório</span><span class="sxs-lookup"><span data-stu-id="73453-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="73453-141">6 </span><span class="sxs-lookup"><span data-stu-id="73453-141">6</span></span>  <br/> |<span data-ttu-id="73453-142">1 </span><span class="sxs-lookup"><span data-stu-id="73453-142">1</span></span>  <br/> |<span data-ttu-id="73453-143">abrir</span><span class="sxs-lookup"><span data-stu-id="73453-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="73453-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="73453-144">See also</span></span>

[<span data-ttu-id="73453-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="73453-145">tblNode</span></span>](tblnode.md)
