---
title: Tabela MediaList
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.
ms.openlocfilehash: b44a6dd8a4263f50cd187b6c4b154815e1e6350a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="medialist-table"></a><span data-ttu-id="321f1-103">Tabela MediaList</span><span class="sxs-lookup"><span data-stu-id="321f1-103">MediaList table</span></span>
 
<span data-ttu-id="321f1-104">MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.</span><span class="sxs-lookup"><span data-stu-id="321f1-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="321f1-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="321f1-105">**Column**</span></span>|<span data-ttu-id="321f1-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="321f1-106">**Data Type**</span></span>|<span data-ttu-id="321f1-107">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="321f1-107">**Key/Index**</span></span>|<span data-ttu-id="321f1-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="321f1-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="321f1-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="321f1-109">**MediaId**</span></span> <br/> |<span data-ttu-id="321f1-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="321f1-110">tinyint</span></span>  <br/> |<span data-ttu-id="321f1-111">Primária</span><span class="sxs-lookup"><span data-stu-id="321f1-111">Primary</span></span>  <br/> |<span data-ttu-id="321f1-112">Valores: 1-7</span><span class="sxs-lookup"><span data-stu-id="321f1-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="321f1-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="321f1-113">**Media**</span></span> <br/> |<span data-ttu-id="321f1-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="321f1-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="321f1-115">Mapeamento estático dos valores de MediaID e Media:</span><span class="sxs-lookup"><span data-stu-id="321f1-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="321f1-116">1 – IM</span><span class="sxs-lookup"><span data-stu-id="321f1-116">1 -- IM</span></span> <br/>  <span data-ttu-id="321f1-117">2 - arquivo transferência</span><span class="sxs-lookup"><span data-stu-id="321f1-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="321f1-118">3 - assistência remota</span><span class="sxs-lookup"><span data-stu-id="321f1-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="321f1-119">4 - compartilhamento de aplicativos de</span><span class="sxs-lookup"><span data-stu-id="321f1-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="321f1-120">5 – Áudio</span><span class="sxs-lookup"><span data-stu-id="321f1-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="321f1-121">6 – Vídeo</span><span class="sxs-lookup"><span data-stu-id="321f1-121">6 -- Video</span></span> <br/>  <span data-ttu-id="321f1-122">7 - convidar app</span><span class="sxs-lookup"><span data-stu-id="321f1-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="321f1-123">Se você está tentando determinar o tipo de modalidade dos valores em LcsCDR.SessionDetailsView.MediaTypes, use o seguinte snippet Join: </span><span class="sxs-lookup"><span data-stu-id="321f1-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```


