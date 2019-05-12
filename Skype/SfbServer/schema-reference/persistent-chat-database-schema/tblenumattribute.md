---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute é uma tabela embutida em código que contém os atributos de visibilidade e comportamento usados na tabela Node.
ms.openlocfilehash: b81e8ae09561220df381290eed212ef752820edd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929949"
---
# <a name="tblenumattribute"></a><span data-ttu-id="f0378-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="f0378-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="f0378-104">tblEnumAttribute é uma tabela embutida em código que contém os atributos de visibilidade e comportamento usados na tabela Node.</span><span class="sxs-lookup"><span data-stu-id="f0378-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="f0378-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="f0378-105">**Columns**</span></span>

|<span data-ttu-id="f0378-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f0378-106">**Column**</span></span>|<span data-ttu-id="f0378-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f0378-107">**Type**</span></span>|<span data-ttu-id="f0378-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f0378-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f0378-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="f0378-109">attributeID</span></span>  <br/> |<span data-ttu-id="f0378-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="f0378-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="f0378-111">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="f0378-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="f0378-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="f0378-112">attributeName</span></span>  <br/> |<span data-ttu-id="f0378-113">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="f0378-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="f0378-114">Nome do atributo.</span><span class="sxs-lookup"><span data-stu-id="f0378-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="f0378-115">**Chave**</span><span class="sxs-lookup"><span data-stu-id="f0378-115">**Key**</span></span>

|<span data-ttu-id="f0378-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f0378-116">**Column**</span></span>|<span data-ttu-id="f0378-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f0378-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f0378-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="f0378-118">attributeID</span></span>  <br/> |<span data-ttu-id="f0378-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="f0378-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="f0378-120">**Valores da tabela**</span><span class="sxs-lookup"><span data-stu-id="f0378-120">**Table Values**</span></span>

|<span data-ttu-id="f0378-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="f0378-121">**attributeID**</span></span>|<span data-ttu-id="f0378-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="f0378-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f0378-123">1</span><span class="sxs-lookup"><span data-stu-id="f0378-123">1</span></span>  <br/> |<span data-ttu-id="f0378-124">Visibilidade.</span><span class="sxs-lookup"><span data-stu-id="f0378-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="f0378-125">2</span><span class="sxs-lookup"><span data-stu-id="f0378-125">2</span></span>  <br/> |<span data-ttu-id="f0378-126">Comportamento.</span><span class="sxs-lookup"><span data-stu-id="f0378-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f0378-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="f0378-127">See also</span></span>

[<span data-ttu-id="f0378-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="f0378-128">tblNode</span></span>](tblnode.md)
