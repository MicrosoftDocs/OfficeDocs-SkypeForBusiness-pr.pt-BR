---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList é a lista de suplementos registrados que podem ser associados a nós.
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295171"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="bdcd9-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="bdcd9-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="bdcd9-104">tblSiopWhiteList é a lista de suplementos registrados que podem ser associados a nós.</span><span class="sxs-lookup"><span data-stu-id="bdcd9-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="bdcd9-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="bdcd9-105">**Columns**</span></span>

|<span data-ttu-id="bdcd9-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="bdcd9-106">**Column**</span></span>|<span data-ttu-id="bdcd9-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="bdcd9-107">**Type**</span></span>|<span data-ttu-id="bdcd9-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="bdcd9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bdcd9-109">siopID</span><span class="sxs-lookup"><span data-stu-id="bdcd9-109">siopID</span></span>  <br/> |<span data-ttu-id="bdcd9-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="bdcd9-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="bdcd9-111">GUID do suplemento.</span><span class="sxs-lookup"><span data-stu-id="bdcd9-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="bdcd9-112">siopName</span><span class="sxs-lookup"><span data-stu-id="bdcd9-112">siopName</span></span>  <br/> |<span data-ttu-id="bdcd9-113">nvarchar (50), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bdcd9-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="bdcd9-114">Display-nome do suplemento.</span><span class="sxs-lookup"><span data-stu-id="bdcd9-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="bdcd9-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="bdcd9-115">siopUrl</span></span>  <br/> |<span data-ttu-id="bdcd9-116">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="bdcd9-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="bdcd9-117">URL do suplemento.</span><span class="sxs-lookup"><span data-stu-id="bdcd9-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="bdcd9-118">**Chave**</span><span class="sxs-lookup"><span data-stu-id="bdcd9-118">**Key**</span></span>

|<span data-ttu-id="bdcd9-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="bdcd9-119">**Column**</span></span>|<span data-ttu-id="bdcd9-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="bdcd9-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bdcd9-121">siopID</span><span class="sxs-lookup"><span data-stu-id="bdcd9-121">siopID</span></span>  <br/> |<span data-ttu-id="bdcd9-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="bdcd9-122">Primary key.</span></span>  <br/> |
   

