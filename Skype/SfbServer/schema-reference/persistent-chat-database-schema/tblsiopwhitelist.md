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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList é a lista de suplementos registrados que podem ser associados a nós.
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812109"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="ee4ce-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="ee4ce-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="ee4ce-104">tblSiopWhiteList é a lista de suplementos registrados que podem ser associados a nós.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="ee4ce-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="ee4ce-105">**Columns**</span></span>

|<span data-ttu-id="ee4ce-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ee4ce-106">**Column**</span></span>|<span data-ttu-id="ee4ce-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ee4ce-107">**Type**</span></span>|<span data-ttu-id="ee4ce-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ee4ce-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ee4ce-109">siopID</span><span class="sxs-lookup"><span data-stu-id="ee4ce-109">siopID</span></span>  <br/> |<span data-ttu-id="ee4ce-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="ee4ce-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="ee4ce-111">GUID do suplemento.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="ee4ce-112">siopName</span><span class="sxs-lookup"><span data-stu-id="ee4ce-112">siopName</span></span>  <br/> |<span data-ttu-id="ee4ce-113">nvarchar (50), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="ee4ce-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="ee4ce-114">Display-nome do suplemento.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="ee4ce-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="ee4ce-115">siopUrl</span></span>  <br/> |<span data-ttu-id="ee4ce-116">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="ee4ce-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="ee4ce-117">URL do suplemento.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="ee4ce-118">**Chave**</span><span class="sxs-lookup"><span data-stu-id="ee4ce-118">**Key**</span></span>

|<span data-ttu-id="ee4ce-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ee4ce-119">**Column**</span></span>|<span data-ttu-id="ee4ce-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ee4ce-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee4ce-121">siopID</span><span class="sxs-lookup"><span data-stu-id="ee4ce-121">siopID</span></span>  <br/> |<span data-ttu-id="ee4ce-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="ee4ce-122">Primary key.</span></span>  <br/> |
   

