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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue é uma tabela codificada que contém os valores de visibilidade e comportamento dos atributos usados na tabela de nós.
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814599"
---
# <a name="tblenumvalue"></a><span data-ttu-id="22e12-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="22e12-103">tblEnumValue</span></span>
 
<span data-ttu-id="22e12-104">tblEnumValue é uma tabela codificada que contém os valores de visibilidade e comportamento dos atributos usados na tabela de nós.</span><span class="sxs-lookup"><span data-stu-id="22e12-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="22e12-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="22e12-105">**Columns**</span></span>

|<span data-ttu-id="22e12-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="22e12-106">**Column**</span></span>|<span data-ttu-id="22e12-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="22e12-107">**Type**</span></span>|<span data-ttu-id="22e12-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="22e12-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="22e12-109">valueid</span><span class="sxs-lookup"><span data-stu-id="22e12-109">valueID</span></span>  <br/> |<span data-ttu-id="22e12-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="22e12-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="22e12-111">ID do valor.</span><span class="sxs-lookup"><span data-stu-id="22e12-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="22e12-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="22e12-112">attributeID</span></span>  <br/> |<span data-ttu-id="22e12-113">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="22e12-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="22e12-114">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="22e12-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="22e12-115">atributovalue</span><span class="sxs-lookup"><span data-stu-id="22e12-115">attributeValue</span></span>  <br/> |<span data-ttu-id="22e12-116">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="22e12-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="22e12-117">Nome do valor.</span><span class="sxs-lookup"><span data-stu-id="22e12-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="22e12-118">**As**</span><span class="sxs-lookup"><span data-stu-id="22e12-118">**Keys**</span></span>

|<span data-ttu-id="22e12-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="22e12-119">**Column**</span></span>|<span data-ttu-id="22e12-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="22e12-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="22e12-121">valueid</span><span class="sxs-lookup"><span data-stu-id="22e12-121">valueID</span></span>  <br/> |<span data-ttu-id="22e12-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="22e12-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="22e12-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="22e12-123">attributeID</span></span>  <br/> |<span data-ttu-id="22e12-124">Chave estrangeira com pesquisa na tabela tblEnumAttribute. attributeID.</span><span class="sxs-lookup"><span data-stu-id="22e12-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="22e12-125">**Valores da tabela**</span><span class="sxs-lookup"><span data-stu-id="22e12-125">**Table Values**</span></span>

|<span data-ttu-id="22e12-126">**valueid**</span><span class="sxs-lookup"><span data-stu-id="22e12-126">**valueID**</span></span>|<span data-ttu-id="22e12-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="22e12-127">**attributeID**</span></span>|<span data-ttu-id="22e12-128">**atributovalue**</span><span class="sxs-lookup"><span data-stu-id="22e12-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="22e12-129">2</span><span class="sxs-lookup"><span data-stu-id="22e12-129">2</span></span>  <br/> |<span data-ttu-id="22e12-130">1</span><span class="sxs-lookup"><span data-stu-id="22e12-130">1</span></span>  <br/> |<span data-ttu-id="22e12-131">private</span><span class="sxs-lookup"><span data-stu-id="22e12-131">private</span></span>  <br/> |
|<span data-ttu-id="22e12-132">3</span><span class="sxs-lookup"><span data-stu-id="22e12-132">3</span></span>  <br/> |<span data-ttu-id="22e12-133">1</span><span class="sxs-lookup"><span data-stu-id="22e12-133">1</span></span>  <br/> |<span data-ttu-id="22e12-134">com</span><span class="sxs-lookup"><span data-stu-id="22e12-134">scope</span></span>  <br/> |
|<span data-ttu-id="22e12-135">4</span><span class="sxs-lookup"><span data-stu-id="22e12-135">4</span></span>  <br/> |<span data-ttu-id="22e12-136">2</span><span class="sxs-lookup"><span data-stu-id="22e12-136">2</span></span>  <br/> |<span data-ttu-id="22e12-137">Normalmente</span><span class="sxs-lookup"><span data-stu-id="22e12-137">normal</span></span>  <br/> |
|<span data-ttu-id="22e12-138">5</span><span class="sxs-lookup"><span data-stu-id="22e12-138">5</span></span>  <br/> |<span data-ttu-id="22e12-139">2</span><span class="sxs-lookup"><span data-stu-id="22e12-139">2</span></span>  <br/> |<span data-ttu-id="22e12-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="22e12-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="22e12-141">6</span><span class="sxs-lookup"><span data-stu-id="22e12-141">6</span></span>  <br/> |<span data-ttu-id="22e12-142">1</span><span class="sxs-lookup"><span data-stu-id="22e12-142">1</span></span>  <br/> |<span data-ttu-id="22e12-143">abriu</span><span class="sxs-lookup"><span data-stu-id="22e12-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="22e12-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="22e12-144">See also</span></span>

[<span data-ttu-id="22e12-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="22e12-145">tblNode</span></span>](tblnode.md)
