---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: a tabela Siopwhitelist é a lista de suplementos registrados que podem ser associados a nós.
ms.openlocfilehash: e5201fff31982da039d864adc4d29d900dbdcf99
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899712"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="fb6bf-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="fb6bf-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="fb6bf-104">a tabela Siopwhitelist é a lista de suplementos registrados que podem ser associados a nós.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="fb6bf-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="fb6bf-105">**Columns**</span></span>

|<span data-ttu-id="fb6bf-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="fb6bf-106">**Column**</span></span>|<span data-ttu-id="fb6bf-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fb6bf-107">**Type**</span></span>|<span data-ttu-id="fb6bf-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fb6bf-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb6bf-109">siopID</span><span class="sxs-lookup"><span data-stu-id="fb6bf-109">siopID</span></span>  <br/> |<span data-ttu-id="fb6bf-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="fb6bf-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="fb6bf-111">GUID do suplemento.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="fb6bf-112">siopName</span><span class="sxs-lookup"><span data-stu-id="fb6bf-112">siopName</span></span>  <br/> |<span data-ttu-id="fb6bf-113">nvarchar (50), não nulo</span><span class="sxs-lookup"><span data-stu-id="fb6bf-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="fb6bf-114">Nome de exibição do add-in.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="fb6bf-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="fb6bf-115">siopUrl</span></span>  <br/> |<span data-ttu-id="fb6bf-116">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="fb6bf-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="fb6bf-117">URL do add-in.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="fb6bf-118">**Chave**</span><span class="sxs-lookup"><span data-stu-id="fb6bf-118">**Key**</span></span>

|<span data-ttu-id="fb6bf-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="fb6bf-119">**Column**</span></span>|<span data-ttu-id="fb6bf-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fb6bf-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fb6bf-121">siopID</span><span class="sxs-lookup"><span data-stu-id="fb6bf-121">siopID</span></span>  <br/> |<span data-ttu-id="fb6bf-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="fb6bf-122">Primary key.</span></span>  <br/> |
   

