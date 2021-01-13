---
title: Tabela ConferenceUris no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: A tabela ConferenceUris é uma tabela de suporte que armazena uma lista de diversos URIs de conferência que participaram de sessões de conferência gravadas no banco de dados. Cada registro da tabela representa um pool.
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816131"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="06a3f-104">Tabela ConferenceUris no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="06a3f-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="06a3f-p102">A tabela ConferenceUris é uma tabela de suporte que armazena uma lista de diversos URIs de conferência que participaram de sessões de conferência gravadas no banco de dados. Cada registro da tabela representa um pool.</span><span class="sxs-lookup"><span data-stu-id="06a3f-p102">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="06a3f-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="06a3f-107">**Column**</span></span>|<span data-ttu-id="06a3f-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="06a3f-108">**Data Type**</span></span>|<span data-ttu-id="06a3f-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="06a3f-109">**Key/Index**</span></span>|<span data-ttu-id="06a3f-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="06a3f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="06a3f-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="06a3f-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="06a3f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="06a3f-112">datetime</span></span>  <br/> |<span data-ttu-id="06a3f-113">Primário</span><span class="sxs-lookup"><span data-stu-id="06a3f-113">Primary</span></span>  <br/> |<span data-ttu-id="06a3f-114">Carimbo de hora, Interno usado.</span><span class="sxs-lookup"><span data-stu-id="06a3f-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="06a3f-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="06a3f-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="06a3f-116">int</span><span class="sxs-lookup"><span data-stu-id="06a3f-116">int</span></span>  <br/> |<span data-ttu-id="06a3f-117">Primário</span><span class="sxs-lookup"><span data-stu-id="06a3f-117">Primary</span></span>  <br/> |<span data-ttu-id="06a3f-118">Número exclusivo que identifica o URI desta conferência.</span><span class="sxs-lookup"><span data-stu-id="06a3f-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="06a3f-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="06a3f-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="06a3f-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="06a3f-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="06a3f-121">URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="06a3f-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="06a3f-122">**Soma de verificação**</span><span class="sxs-lookup"><span data-stu-id="06a3f-122">**Checksum**</span></span> <br/> |<span data-ttu-id="06a3f-123">int</span><span class="sxs-lookup"><span data-stu-id="06a3f-123">int</span></span>  <br/> ||<span data-ttu-id="06a3f-p103">Soma de verificação do ConferenceUri. Usado para aumentar a velocidade de pesquisas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="06a3f-p103">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="06a3f-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="06a3f-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="06a3f-127">int</span><span class="sxs-lookup"><span data-stu-id="06a3f-127">int</span></span>  <br/> |<span data-ttu-id="06a3f-128">Externo</span><span class="sxs-lookup"><span data-stu-id="06a3f-128">Foreign</span></span>  <br/> |<span data-ttu-id="06a3f-129">Tipo de URI, por exemplo, conf:chat para conferência IM ou conf:audio-video para conferência de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="06a3f-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="06a3f-130">Consulte a [tabela UriTypes para](uritypes.md) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="06a3f-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

