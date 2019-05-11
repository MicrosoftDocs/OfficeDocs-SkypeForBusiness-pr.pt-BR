---
title: Tabela MediaList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.
ms.openlocfilehash: 3eaa40cb5ae03129edaa36effa7b40012fc38429
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930648"
---
# <a name="medialist-table"></a><span data-ttu-id="e211b-103">Tabela MediaList</span><span class="sxs-lookup"><span data-stu-id="e211b-103">MediaList table</span></span>
 
<span data-ttu-id="e211b-104">MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.</span><span class="sxs-lookup"><span data-stu-id="e211b-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="e211b-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e211b-105">**Column**</span></span>|<span data-ttu-id="e211b-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e211b-106">**Data Type**</span></span>|<span data-ttu-id="e211b-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="e211b-107">**Key/Index**</span></span>|<span data-ttu-id="e211b-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="e211b-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e211b-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="e211b-109">**MediaId**</span></span> <br/> |<span data-ttu-id="e211b-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="e211b-110">tinyint</span></span>  <br/> |<span data-ttu-id="e211b-111">Primária</span><span class="sxs-lookup"><span data-stu-id="e211b-111">Primary</span></span>  <br/> |<span data-ttu-id="e211b-112">Valores: 1-7</span><span class="sxs-lookup"><span data-stu-id="e211b-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="e211b-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="e211b-113">**Media**</span></span> <br/> |<span data-ttu-id="e211b-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e211b-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="e211b-115">Mapeamento estático dos valores de MediaID e Media:</span><span class="sxs-lookup"><span data-stu-id="e211b-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="e211b-116">1 – IM</span><span class="sxs-lookup"><span data-stu-id="e211b-116">1 -- IM</span></span> <br/>  <span data-ttu-id="e211b-117">2 - arquivo transferência</span><span class="sxs-lookup"><span data-stu-id="e211b-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="e211b-118">3 - assistência remota</span><span class="sxs-lookup"><span data-stu-id="e211b-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="e211b-119">4 - compartilhamento de aplicativos de</span><span class="sxs-lookup"><span data-stu-id="e211b-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="e211b-120">5 – Áudio</span><span class="sxs-lookup"><span data-stu-id="e211b-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="e211b-121">6 – Vídeo</span><span class="sxs-lookup"><span data-stu-id="e211b-121">6 -- Video</span></span> <br/>  <span data-ttu-id="e211b-122">7 - convidar app</span><span class="sxs-lookup"><span data-stu-id="e211b-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="e211b-123">Se você está tentando determinar o tipo de modalidade dos valores em LcsCDR.SessionDetailsView.MediaTypes, use o seguinte snippet Join: </span><span class="sxs-lookup"><span data-stu-id="e211b-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
