---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute é uma tabela codificada que contém os atributos de visibilidade e comportamento usados na tabela de nós.
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814609"
---
# <a name="tblenumattribute"></a><span data-ttu-id="27258-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="27258-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="27258-104">tblEnumAttribute é uma tabela codificada que contém os atributos de visibilidade e comportamento usados na tabela de nós.</span><span class="sxs-lookup"><span data-stu-id="27258-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="27258-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="27258-105">**Columns**</span></span>

|<span data-ttu-id="27258-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="27258-106">**Column**</span></span>|<span data-ttu-id="27258-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="27258-107">**Type**</span></span>|<span data-ttu-id="27258-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="27258-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="27258-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="27258-109">attributeID</span></span>  <br/> |<span data-ttu-id="27258-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="27258-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="27258-111">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="27258-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="27258-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="27258-112">attributeName</span></span>  <br/> |<span data-ttu-id="27258-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="27258-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="27258-114">Nome do atributo.</span><span class="sxs-lookup"><span data-stu-id="27258-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="27258-115">**Chave**</span><span class="sxs-lookup"><span data-stu-id="27258-115">**Key**</span></span>

|<span data-ttu-id="27258-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="27258-116">**Column**</span></span>|<span data-ttu-id="27258-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="27258-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="27258-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="27258-118">attributeID</span></span>  <br/> |<span data-ttu-id="27258-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="27258-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="27258-120">**Valores da tabela**</span><span class="sxs-lookup"><span data-stu-id="27258-120">**Table Values**</span></span>

|<span data-ttu-id="27258-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="27258-121">**attributeID**</span></span>|<span data-ttu-id="27258-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="27258-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="27258-123">1</span><span class="sxs-lookup"><span data-stu-id="27258-123">1</span></span>  <br/> |<span data-ttu-id="27258-124">Visibilidade.</span><span class="sxs-lookup"><span data-stu-id="27258-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="27258-125">2</span><span class="sxs-lookup"><span data-stu-id="27258-125">2</span></span>  <br/> |<span data-ttu-id="27258-126">Funcionamento.</span><span class="sxs-lookup"><span data-stu-id="27258-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="27258-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="27258-127">See also</span></span>

[<span data-ttu-id="27258-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="27258-128">tblNode</span></span>](tblnode.md)
