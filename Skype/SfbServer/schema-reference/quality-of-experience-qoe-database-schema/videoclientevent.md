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
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada com vídeo. Geralmente, uma chamada tem dois registros, um para o chamador e outro para o receptor.
ms.openlocfilehash: b8e93206ea30622baa82adcec5ee9a80235521c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294548"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="a8ce5-104">Tabela VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="a8ce5-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="a8ce5-105">Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada com vídeo.</span><span class="sxs-lookup"><span data-stu-id="a8ce5-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="a8ce5-106">Geralmente, uma chamada tem dois registros, um para o chamador e outro para o receptor.</span><span class="sxs-lookup"><span data-stu-id="a8ce5-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="a8ce5-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a8ce5-107">**Column**</span></span>|<span data-ttu-id="a8ce5-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a8ce5-108">**Data Type**</span></span>|<span data-ttu-id="a8ce5-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="a8ce5-109">**Key/Index**</span></span>|<span data-ttu-id="a8ce5-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a8ce5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a8ce5-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="a8ce5-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="a8ce5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="a8ce5-112">datetime</span></span>  <br/> |<span data-ttu-id="a8ce5-113">Primária</span><span class="sxs-lookup"><span data-stu-id="a8ce5-113">Primary</span></span>  <br/> |<span data-ttu-id="a8ce5-114">Referenciado da [tabela de mídia](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="a8ce5-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="a8ce5-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="a8ce5-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="a8ce5-116">int</span><span class="sxs-lookup"><span data-stu-id="a8ce5-116">int</span></span>  <br/> |<span data-ttu-id="a8ce5-117">Primária</span><span class="sxs-lookup"><span data-stu-id="a8ce5-117">Primary</span></span>  <br/> |<span data-ttu-id="a8ce5-118">Referenciado da [tabela de mídia](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="a8ce5-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="a8ce5-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="a8ce5-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="a8ce5-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="a8ce5-120">tinyint</span></span>  <br/> |<span data-ttu-id="a8ce5-121">Primária</span><span class="sxs-lookup"><span data-stu-id="a8ce5-121">Primary</span></span>  <br/> |<span data-ttu-id="a8ce5-122">Referenciado da [tabela de mídia](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="a8ce5-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="a8ce5-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="a8ce5-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="a8ce5-124">bit</span><span class="sxs-lookup"><span data-stu-id="a8ce5-124">bit</span></span>  <br/> |<span data-ttu-id="a8ce5-125">Primária</span><span class="sxs-lookup"><span data-stu-id="a8ce5-125">Primary</span></span>  <br/> |<span data-ttu-id="a8ce5-126">0: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="a8ce5-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="a8ce5-127">1: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="a8ce5-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="a8ce5-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="a8ce5-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="a8ce5-129">Porcentagem da sessão o evento LowBandwidth foi disparado para o estado ' ruim '.</span><span class="sxs-lookup"><span data-stu-id="a8ce5-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="a8ce5-130">A largura de banda disponível é insuficiente para uma experiência de voz aceitável.</span><span class="sxs-lookup"><span data-stu-id="a8ce5-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="a8ce5-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="a8ce5-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="a8ce5-132">Porcentagem da sessão o evento ReceiveSendQuality foi disparado para o estado ' ruim '.</span><span class="sxs-lookup"><span data-stu-id="a8ce5-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="a8ce5-133">A qualidade da rede em termos de tremulação ou perda de pacote é severa e afeta a qualidade do áudio sendo recebido.</span><span class="sxs-lookup"><span data-stu-id="a8ce5-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

