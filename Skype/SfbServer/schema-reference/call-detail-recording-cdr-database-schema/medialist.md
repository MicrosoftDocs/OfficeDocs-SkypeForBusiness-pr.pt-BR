---
title: Tabela MediaList
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 6f593876a1b42163b6f2e75dbe44c1eb26b2ff16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813131"
---
# <a name="medialist-table"></a><span data-ttu-id="7d6fb-103">Tabela MediaList</span><span class="sxs-lookup"><span data-stu-id="7d6fb-103">MediaList table</span></span>
 
<span data-ttu-id="7d6fb-104">MediaList é uma tabela estática que armazena a lista de vários tipos de mídia.</span><span class="sxs-lookup"><span data-stu-id="7d6fb-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="7d6fb-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="7d6fb-105">**Column**</span></span>|<span data-ttu-id="7d6fb-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="7d6fb-106">**Data Type**</span></span>|<span data-ttu-id="7d6fb-107">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="7d6fb-107">**Key/Index**</span></span>|<span data-ttu-id="7d6fb-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="7d6fb-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7d6fb-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="7d6fb-109">**MediaId**</span></span> <br/> |<span data-ttu-id="7d6fb-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="7d6fb-110">tinyint</span></span>  <br/> |<span data-ttu-id="7d6fb-111">Primário</span><span class="sxs-lookup"><span data-stu-id="7d6fb-111">Primary</span></span>  <br/> |<span data-ttu-id="7d6fb-112">Valores: 1 a 7</span><span class="sxs-lookup"><span data-stu-id="7d6fb-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="7d6fb-113">**Mídia**</span><span class="sxs-lookup"><span data-stu-id="7d6fb-113">**Media**</span></span> <br/> |<span data-ttu-id="7d6fb-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7d6fb-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="7d6fb-115">Mapeamento estático dos valores MediaID e Media:</span><span class="sxs-lookup"><span data-stu-id="7d6fb-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="7d6fb-116">1 -- IM</span><span class="sxs-lookup"><span data-stu-id="7d6fb-116">1 -- IM</span></span> <br/>  <span data-ttu-id="7d6fb-117">2 - Transferência de arquivos</span><span class="sxs-lookup"><span data-stu-id="7d6fb-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="7d6fb-118">3 - Assistência Remota</span><span class="sxs-lookup"><span data-stu-id="7d6fb-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="7d6fb-119">4 - Compartilhamento de Aplicativos</span><span class="sxs-lookup"><span data-stu-id="7d6fb-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="7d6fb-120">5 -- Áudio</span><span class="sxs-lookup"><span data-stu-id="7d6fb-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="7d6fb-121">6 -- Vídeo</span><span class="sxs-lookup"><span data-stu-id="7d6fb-121">6 -- Video</span></span> <br/>  <span data-ttu-id="7d6fb-122">7 - Convite do aplicativo</span><span class="sxs-lookup"><span data-stu-id="7d6fb-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="7d6fb-123">Se você estiver tentando determinar o tipo de modalidade para os valores em LcsCDR.SessionDetailsView.MediaTypes, será necessário usar o seguinte trecho de Junção:</span><span class="sxs-lookup"><span data-stu-id="7d6fb-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
