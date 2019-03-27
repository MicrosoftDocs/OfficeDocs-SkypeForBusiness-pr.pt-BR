---
title: Tabela ConferenceUris Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: A tabela de ConfereneUris é uma tabela de suporte que armazena uma lista de uma conferência diversos URIs que tenham participado em sessões de conferência registradas no banco de dados. Cada registro na tabela representa um URI de conferência.
ms.openlocfilehash: 6f373774b652e9858af84dd4c16b51fcb3c5d493
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887768"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2b8ec-104">Tabela ConferenceUris Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2b8ec-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2b8ec-105">A tabela de ConfereneUris é uma tabela de suporte que armazena uma lista de uma conferência diversos URIs que tenham participado em sessões de conferência registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2b8ec-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="2b8ec-106">Cada registro na tabela representa um URI de conferência.</span><span class="sxs-lookup"><span data-stu-id="2b8ec-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="2b8ec-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2b8ec-107">**Column**</span></span>|<span data-ttu-id="2b8ec-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="2b8ec-108">**Data Type**</span></span>|<span data-ttu-id="2b8ec-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="2b8ec-109">**Key/Index**</span></span>|<span data-ttu-id="2b8ec-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="2b8ec-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b8ec-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="2b8ec-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="2b8ec-112">datetime</span><span class="sxs-lookup"><span data-stu-id="2b8ec-112">datetime</span></span>  <br/> |<span data-ttu-id="2b8ec-113">Primária</span><span class="sxs-lookup"><span data-stu-id="2b8ec-113">Primary</span></span>  <br/> |<span data-ttu-id="2b8ec-114">Carimbo de hora, interno usado.</span><span class="sxs-lookup"><span data-stu-id="2b8ec-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="2b8ec-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="2b8ec-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="2b8ec-116">int</span><span class="sxs-lookup"><span data-stu-id="2b8ec-116">int</span></span>  <br/> |<span data-ttu-id="2b8ec-117">Primária</span><span class="sxs-lookup"><span data-stu-id="2b8ec-117">Primary</span></span>  <br/> |<span data-ttu-id="2b8ec-118">Número exclusivo que identifica o URI desta conferência.</span><span class="sxs-lookup"><span data-stu-id="2b8ec-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="2b8ec-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="2b8ec-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="2b8ec-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="2b8ec-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="2b8ec-121">URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="2b8ec-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="2b8ec-122">**Soma de verificação**</span><span class="sxs-lookup"><span data-stu-id="2b8ec-122">**Checksum**</span></span> <br/> |<span data-ttu-id="2b8ec-123">int</span><span class="sxs-lookup"><span data-stu-id="2b8ec-123">int</span></span>  <br/> ||<span data-ttu-id="2b8ec-124">Soma de verificação de ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="2b8ec-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="2b8ec-125">Usado para aumenta a velocidade de pesquisas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2b8ec-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="2b8ec-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="2b8ec-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="2b8ec-127">int</span><span class="sxs-lookup"><span data-stu-id="2b8ec-127">int</span></span>  <br/> |<span data-ttu-id="2b8ec-128">Externa</span><span class="sxs-lookup"><span data-stu-id="2b8ec-128">Foreign</span></span>  <br/> |<span data-ttu-id="2b8ec-129">Tipo de URI, como conf:chat para conferência de mensagem Instantânea ou conf:audio-vídeo para conferência de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="2b8ec-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="2b8ec-130">Consulte a tabela de [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2b8ec-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

