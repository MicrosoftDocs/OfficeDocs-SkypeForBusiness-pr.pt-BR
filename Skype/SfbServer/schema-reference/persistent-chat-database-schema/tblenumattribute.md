---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute é uma tabela embutida em código que contém os atributos de visibilidade e comportamento usados na tabela Node.
ms.openlocfilehash: 7555656f02fa7808e54100c03de8f80e0e078678
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212590"
---
# <a name="tblenumattribute"></a><span data-ttu-id="3729f-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="3729f-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="3729f-104">tblEnumAttribute é uma tabela embutida em código que contém os atributos de visibilidade e comportamento usados na tabela Node.</span><span class="sxs-lookup"><span data-stu-id="3729f-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="3729f-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="3729f-105">**Columns**</span></span>

|<span data-ttu-id="3729f-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3729f-106">**Column**</span></span>|<span data-ttu-id="3729f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3729f-107">**Type**</span></span>|<span data-ttu-id="3729f-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3729f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3729f-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="3729f-109">attributeID</span></span>  <br/> |<span data-ttu-id="3729f-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="3729f-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="3729f-111">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="3729f-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="3729f-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="3729f-112">attributeName</span></span>  <br/> |<span data-ttu-id="3729f-113">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="3729f-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="3729f-114">Nome do atributo.</span><span class="sxs-lookup"><span data-stu-id="3729f-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="3729f-115">**Chave**</span><span class="sxs-lookup"><span data-stu-id="3729f-115">**Key**</span></span>

|<span data-ttu-id="3729f-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3729f-116">**Column**</span></span>|<span data-ttu-id="3729f-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3729f-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3729f-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="3729f-118">attributeID</span></span>  <br/> |<span data-ttu-id="3729f-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="3729f-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="3729f-120">**Valores da tabela**</span><span class="sxs-lookup"><span data-stu-id="3729f-120">**Table Values**</span></span>

|<span data-ttu-id="3729f-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="3729f-121">**attributeID**</span></span>|<span data-ttu-id="3729f-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="3729f-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3729f-123">1</span><span class="sxs-lookup"><span data-stu-id="3729f-123">1</span></span>  <br/> |<span data-ttu-id="3729f-124">Visibilidade.</span><span class="sxs-lookup"><span data-stu-id="3729f-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="3729f-125">2</span><span class="sxs-lookup"><span data-stu-id="3729f-125">2</span></span>  <br/> |<span data-ttu-id="3729f-126">Comportamento.</span><span class="sxs-lookup"><span data-stu-id="3729f-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3729f-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="3729f-127">See also</span></span>

[<span data-ttu-id="3729f-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="3729f-128">tblNode</span></span>](tblnode.md)
