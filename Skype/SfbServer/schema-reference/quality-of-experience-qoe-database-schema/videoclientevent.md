---
title: Tabela VideoClientEvent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada com vídeo. Geralmente, uma chamada tem dois registros, um para o chamador e outro para o receptor.
ms.openlocfilehash: 9acd7277fd6bc32074487be1db9874ef6a5c91aa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804989"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="96824-104">Tabela VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="96824-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="96824-105">Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada com vídeo.</span><span class="sxs-lookup"><span data-stu-id="96824-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="96824-106">Geralmente, uma chamada tem dois registros, um para o chamador e outro para o receptor.</span><span class="sxs-lookup"><span data-stu-id="96824-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="96824-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="96824-107">**Column**</span></span>|<span data-ttu-id="96824-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="96824-108">**Data Type**</span></span>|<span data-ttu-id="96824-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="96824-109">**Key/Index**</span></span>|<span data-ttu-id="96824-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="96824-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="96824-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="96824-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="96824-112">datetime</span><span class="sxs-lookup"><span data-stu-id="96824-112">datetime</span></span>  <br/> |<span data-ttu-id="96824-113">Primária</span><span class="sxs-lookup"><span data-stu-id="96824-113">Primary</span></span>  <br/> |<span data-ttu-id="96824-114">Referenciado da [tabela de mídia](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="96824-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="96824-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="96824-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="96824-116">int</span><span class="sxs-lookup"><span data-stu-id="96824-116">int</span></span>  <br/> |<span data-ttu-id="96824-117">Primária</span><span class="sxs-lookup"><span data-stu-id="96824-117">Primary</span></span>  <br/> |<span data-ttu-id="96824-118">Referenciado da [tabela de mídia](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="96824-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="96824-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="96824-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="96824-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="96824-120">tinyint</span></span>  <br/> |<span data-ttu-id="96824-121">Primária</span><span class="sxs-lookup"><span data-stu-id="96824-121">Primary</span></span>  <br/> |<span data-ttu-id="96824-122">Referenciado da [tabela de mídia](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="96824-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="96824-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="96824-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="96824-124">bit</span><span class="sxs-lookup"><span data-stu-id="96824-124">bit</span></span>  <br/> |<span data-ttu-id="96824-125">Primária</span><span class="sxs-lookup"><span data-stu-id="96824-125">Primary</span></span>  <br/> |<span data-ttu-id="96824-126">0: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="96824-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="96824-127">1: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="96824-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="96824-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="96824-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="96824-129">Porcentagem da sessão o evento LowBandwidth foi disparado para o estado ' ruim '.</span><span class="sxs-lookup"><span data-stu-id="96824-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="96824-130">A largura de banda disponível é insuficiente para uma experiência de voz aceitável.</span><span class="sxs-lookup"><span data-stu-id="96824-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="96824-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="96824-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="96824-132">Porcentagem da sessão o evento ReceiveSendQuality foi disparado para o estado ' ruim '.</span><span class="sxs-lookup"><span data-stu-id="96824-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="96824-133">A qualidade da rede em termos de tremulação ou perda de pacote é severa e afeta a qualidade do áudio sendo recebido.</span><span class="sxs-lookup"><span data-stu-id="96824-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

