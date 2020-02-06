---
title: Tabela ConferenceUris no Skype for Business Server 2015
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: A tabela ConfereneUris é uma tabela de suporte que armazena uma lista de vários URIs de conferência que participaram de sessões de conferência registradas no banco de dados. Cada registro na tabela representa um URI de conferência.
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815309"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="99daa-104">Tabela ConferenceUris no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="99daa-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="99daa-105">A tabela ConfereneUris é uma tabela de suporte que armazena uma lista de vários URIs de conferência que participaram de sessões de conferência registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="99daa-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="99daa-106">Cada registro na tabela representa um URI de conferência.</span><span class="sxs-lookup"><span data-stu-id="99daa-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="99daa-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="99daa-107">**Column**</span></span>|<span data-ttu-id="99daa-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="99daa-108">**Data Type**</span></span>|<span data-ttu-id="99daa-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="99daa-109">**Key/Index**</span></span>|<span data-ttu-id="99daa-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="99daa-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="99daa-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="99daa-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="99daa-112">datetime</span><span class="sxs-lookup"><span data-stu-id="99daa-112">datetime</span></span>  <br/> |<span data-ttu-id="99daa-113">Primária</span><span class="sxs-lookup"><span data-stu-id="99daa-113">Primary</span></span>  <br/> |<span data-ttu-id="99daa-114">Carimbo de data/hora, usado internamente.</span><span class="sxs-lookup"><span data-stu-id="99daa-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="99daa-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="99daa-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="99daa-116">int</span><span class="sxs-lookup"><span data-stu-id="99daa-116">int</span></span>  <br/> |<span data-ttu-id="99daa-117">Primária</span><span class="sxs-lookup"><span data-stu-id="99daa-117">Primary</span></span>  <br/> |<span data-ttu-id="99daa-118">Número exclusivo que identifica esse URI de conferência.</span><span class="sxs-lookup"><span data-stu-id="99daa-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="99daa-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="99daa-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="99daa-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="99daa-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="99daa-121">URL da conferência.</span><span class="sxs-lookup"><span data-stu-id="99daa-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="99daa-122">**Prova**</span><span class="sxs-lookup"><span data-stu-id="99daa-122">**Checksum**</span></span> <br/> |<span data-ttu-id="99daa-123">int</span><span class="sxs-lookup"><span data-stu-id="99daa-123">int</span></span>  <br/> ||<span data-ttu-id="99daa-124">Soma de verificação de ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="99daa-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="99daa-125">Usado para aumentar a velocidade das pesquisas do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="99daa-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="99daa-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="99daa-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="99daa-127">int</span><span class="sxs-lookup"><span data-stu-id="99daa-127">int</span></span>  <br/> |<span data-ttu-id="99daa-128">Exterior</span><span class="sxs-lookup"><span data-stu-id="99daa-128">Foreign</span></span>  <br/> |<span data-ttu-id="99daa-129">Tipo de URI, como conf: chat para conferência de IM ou conf: áudio-vídeo para videoconferência/videoconferência.</span><span class="sxs-lookup"><span data-stu-id="99daa-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="99daa-130">Consulte a tabela da [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="99daa-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

