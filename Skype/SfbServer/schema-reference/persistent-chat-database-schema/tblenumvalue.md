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
ms.openlocfilehash: 4e17e5fc167342c106e7b5354d90c7fc284785c3
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505073"
---
# <a name="tblenumvalue"></a><span data-ttu-id="370cd-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="370cd-103">tblEnumValue</span></span>
 
<span data-ttu-id="370cd-104">a tabela tblEnumValue é uma tabela embutida em código que contém os valores de visibilidade e comportamento dos atributos que são usados na tabela Node.</span><span class="sxs-lookup"><span data-stu-id="370cd-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="370cd-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="370cd-105">**Columns**</span></span>

|<span data-ttu-id="370cd-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="370cd-106">**Column**</span></span>|<span data-ttu-id="370cd-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="370cd-107">**Type**</span></span>|<span data-ttu-id="370cd-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="370cd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="370cd-109">valueID</span><span class="sxs-lookup"><span data-stu-id="370cd-109">valueID</span></span>  <br/> |<span data-ttu-id="370cd-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="370cd-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="370cd-111">ID do valor.</span><span class="sxs-lookup"><span data-stu-id="370cd-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="370cd-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="370cd-112">attributeID</span></span>  <br/> |<span data-ttu-id="370cd-113">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="370cd-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="370cd-114">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="370cd-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="370cd-115">valor de atributo</span><span class="sxs-lookup"><span data-stu-id="370cd-115">attributeValue</span></span>  <br/> |<span data-ttu-id="370cd-116">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="370cd-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="370cd-117">Nome do valor.</span><span class="sxs-lookup"><span data-stu-id="370cd-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="370cd-118">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="370cd-118">**Keys**</span></span>

|<span data-ttu-id="370cd-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="370cd-119">**Column**</span></span>|<span data-ttu-id="370cd-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="370cd-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="370cd-121">valueID</span><span class="sxs-lookup"><span data-stu-id="370cd-121">valueID</span></span>  <br/> |<span data-ttu-id="370cd-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="370cd-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="370cd-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="370cd-123">attributeID</span></span>  <br/> |<span data-ttu-id="370cd-124">Chave estrangeira com pesquisa na tabela Tblenumattribute.</span><span class="sxs-lookup"><span data-stu-id="370cd-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="370cd-125">**Valores da tabela**</span><span class="sxs-lookup"><span data-stu-id="370cd-125">**Table Values**</span></span>

|<span data-ttu-id="370cd-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="370cd-126">**valueID**</span></span>|<span data-ttu-id="370cd-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="370cd-127">**attributeID**</span></span>|<span data-ttu-id="370cd-128">**valor de atributo**</span><span class="sxs-lookup"><span data-stu-id="370cd-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="370cd-129">2</span><span class="sxs-lookup"><span data-stu-id="370cd-129">2</span></span>  <br/> |<span data-ttu-id="370cd-130">1</span><span class="sxs-lookup"><span data-stu-id="370cd-130">1</span></span>  <br/> |<span data-ttu-id="370cd-131">private</span><span class="sxs-lookup"><span data-stu-id="370cd-131">private</span></span>  <br/> |
|<span data-ttu-id="370cd-132">3</span><span class="sxs-lookup"><span data-stu-id="370cd-132">3</span></span>  <br/> |<span data-ttu-id="370cd-133">1</span><span class="sxs-lookup"><span data-stu-id="370cd-133">1</span></span>  <br/> |<span data-ttu-id="370cd-134">escopo</span><span class="sxs-lookup"><span data-stu-id="370cd-134">scope</span></span>  <br/> |
|<span data-ttu-id="370cd-135">4</span><span class="sxs-lookup"><span data-stu-id="370cd-135">4</span></span>  <br/> |<span data-ttu-id="370cd-136">2</span><span class="sxs-lookup"><span data-stu-id="370cd-136">2</span></span>  <br/> |<span data-ttu-id="370cd-137">normal</span><span class="sxs-lookup"><span data-stu-id="370cd-137">normal</span></span>  <br/> |
|<span data-ttu-id="370cd-138">5</span><span class="sxs-lookup"><span data-stu-id="370cd-138">5</span></span>  <br/> |<span data-ttu-id="370cd-139">2</span><span class="sxs-lookup"><span data-stu-id="370cd-139">2</span></span>  <br/> |<span data-ttu-id="370cd-140">auditório</span><span class="sxs-lookup"><span data-stu-id="370cd-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="370cd-141">6</span><span class="sxs-lookup"><span data-stu-id="370cd-141">6</span></span>  <br/> |<span data-ttu-id="370cd-142">1</span><span class="sxs-lookup"><span data-stu-id="370cd-142">1</span></span>  <br/> |<span data-ttu-id="370cd-143">Abrir</span><span class="sxs-lookup"><span data-stu-id="370cd-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="370cd-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="370cd-144">See also</span></span>

[<span data-ttu-id="370cd-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="370cd-145">tblNode</span></span>](tblnode.md)