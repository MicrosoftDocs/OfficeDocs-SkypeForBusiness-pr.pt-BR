---
title: tblEnumAttribute
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
ms.openlocfilehash: bd386bc77d15c627597a5680277235a05d0c8039
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504863"
---
# <a name="tblenumattribute"></a><span data-ttu-id="6678c-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="6678c-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="6678c-104">tblEnumAttribute é uma tabela embutida em código que contém os atributos de visibilidade e comportamento usados na tabela Node.</span><span class="sxs-lookup"><span data-stu-id="6678c-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="6678c-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="6678c-105">**Columns**</span></span>

|<span data-ttu-id="6678c-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6678c-106">**Column**</span></span>|<span data-ttu-id="6678c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6678c-107">**Type**</span></span>|<span data-ttu-id="6678c-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6678c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6678c-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="6678c-109">attributeID</span></span>  <br/> |<span data-ttu-id="6678c-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="6678c-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="6678c-111">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="6678c-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="6678c-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="6678c-112">attributeName</span></span>  <br/> |<span data-ttu-id="6678c-113">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="6678c-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="6678c-114">Nome do atributo.</span><span class="sxs-lookup"><span data-stu-id="6678c-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="6678c-115">**Chave**</span><span class="sxs-lookup"><span data-stu-id="6678c-115">**Key**</span></span>

|<span data-ttu-id="6678c-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6678c-116">**Column**</span></span>|<span data-ttu-id="6678c-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6678c-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6678c-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="6678c-118">attributeID</span></span>  <br/> |<span data-ttu-id="6678c-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="6678c-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="6678c-120">**Valores da tabela**</span><span class="sxs-lookup"><span data-stu-id="6678c-120">**Table Values**</span></span>

|<span data-ttu-id="6678c-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="6678c-121">**attributeID**</span></span>|<span data-ttu-id="6678c-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="6678c-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6678c-123">1</span><span class="sxs-lookup"><span data-stu-id="6678c-123">1</span></span>  <br/> |<span data-ttu-id="6678c-124">Visibilidade.</span><span class="sxs-lookup"><span data-stu-id="6678c-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="6678c-125">2</span><span class="sxs-lookup"><span data-stu-id="6678c-125">2</span></span>  <br/> |<span data-ttu-id="6678c-126">Comportamento.</span><span class="sxs-lookup"><span data-stu-id="6678c-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6678c-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6678c-127">See also</span></span>

[<span data-ttu-id="6678c-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="6678c-128">tblNode</span></span>](tblnode.md)