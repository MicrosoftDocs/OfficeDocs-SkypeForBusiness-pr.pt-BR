---
title: Tabela MediaList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.
ms.openlocfilehash: 7742baf17240ca810268721c0e47e37f17e555cd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815029"
---
# <a name="medialist-table"></a><span data-ttu-id="f5abe-103">Tabela MediaList</span><span class="sxs-lookup"><span data-stu-id="f5abe-103">MediaList table</span></span>
 
<span data-ttu-id="f5abe-104">MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.</span><span class="sxs-lookup"><span data-stu-id="f5abe-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="f5abe-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f5abe-105">**Column**</span></span>|<span data-ttu-id="f5abe-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="f5abe-106">**Data Type**</span></span>|<span data-ttu-id="f5abe-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="f5abe-107">**Key/Index**</span></span>|<span data-ttu-id="f5abe-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="f5abe-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f5abe-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="f5abe-109">**MediaId**</span></span> <br/> |<span data-ttu-id="f5abe-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="f5abe-110">tinyint</span></span>  <br/> |<span data-ttu-id="f5abe-111">Primária</span><span class="sxs-lookup"><span data-stu-id="f5abe-111">Primary</span></span>  <br/> |<span data-ttu-id="f5abe-112">Valores: 1-7</span><span class="sxs-lookup"><span data-stu-id="f5abe-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="f5abe-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="f5abe-113">**Media**</span></span> <br/> |<span data-ttu-id="f5abe-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f5abe-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="f5abe-115">Mapeamento estático dos valores de MediaID e Media:</span><span class="sxs-lookup"><span data-stu-id="f5abe-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="f5abe-116">1 – IM</span><span class="sxs-lookup"><span data-stu-id="f5abe-116">1 -- IM</span></span> <br/>  <span data-ttu-id="f5abe-117">Transferência de 2 arquivos</span><span class="sxs-lookup"><span data-stu-id="f5abe-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="f5abe-118">3-assistência remota</span><span class="sxs-lookup"><span data-stu-id="f5abe-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="f5abe-119">4-compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="f5abe-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="f5abe-120">5 – Áudio</span><span class="sxs-lookup"><span data-stu-id="f5abe-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="f5abe-121">6 – Vídeo</span><span class="sxs-lookup"><span data-stu-id="f5abe-121">6 -- Video</span></span> <br/>  <span data-ttu-id="f5abe-122">7-convite do aplicativo</span><span class="sxs-lookup"><span data-stu-id="f5abe-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="f5abe-123">Se você está tentando determinar o tipo de modalidade dos valores em LcsCDR.SessionDetailsView.MediaTypes, use o seguinte snippet Join: </span><span class="sxs-lookup"><span data-stu-id="f5abe-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```json
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
