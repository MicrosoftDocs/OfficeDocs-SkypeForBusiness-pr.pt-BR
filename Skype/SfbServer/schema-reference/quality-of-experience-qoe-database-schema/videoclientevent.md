---
title: Tabela VideoClientEvent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contém um evento do cliente para um ponto de extremidade em uma chamada de vídeo. Normalmente, uma chamada tem dois registros, um para o chamador e um para o receptor.
ms.openlocfilehash: 314e4df9313a3d111d71b6eaa06565edcbb765d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891234"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="0f506-104">Tabela VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="0f506-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="0f506-105">Cada registro contém um evento do cliente para um ponto de extremidade em uma chamada de vídeo.</span><span class="sxs-lookup"><span data-stu-id="0f506-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="0f506-106">Normalmente, uma chamada tem dois registros, um para o chamador e um para o receptor.</span><span class="sxs-lookup"><span data-stu-id="0f506-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="0f506-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="0f506-107">**Column**</span></span>|<span data-ttu-id="0f506-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="0f506-108">**Data Type**</span></span>|<span data-ttu-id="0f506-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="0f506-109">**Key/Index**</span></span>|<span data-ttu-id="0f506-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="0f506-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0f506-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="0f506-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="0f506-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0f506-112">datetime</span></span>  <br/> |<span data-ttu-id="0f506-113">Primária</span><span class="sxs-lookup"><span data-stu-id="0f506-113">Primary</span></span>  <br/> |<span data-ttu-id="0f506-114">Referenciado de [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="0f506-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0f506-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="0f506-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="0f506-116">int</span><span class="sxs-lookup"><span data-stu-id="0f506-116">int</span></span>  <br/> |<span data-ttu-id="0f506-117">Primária</span><span class="sxs-lookup"><span data-stu-id="0f506-117">Primary</span></span>  <br/> |<span data-ttu-id="0f506-118">Referenciado de [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="0f506-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0f506-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="0f506-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="0f506-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="0f506-120">tinyint</span></span>  <br/> |<span data-ttu-id="0f506-121">Primária</span><span class="sxs-lookup"><span data-stu-id="0f506-121">Primary</span></span>  <br/> |<span data-ttu-id="0f506-122">Referenciado de [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="0f506-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0f506-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="0f506-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="0f506-124">bit</span><span class="sxs-lookup"><span data-stu-id="0f506-124">bit</span></span>  <br/> |<span data-ttu-id="0f506-125">Primária</span><span class="sxs-lookup"><span data-stu-id="0f506-125">Primary</span></span>  <br/> |<span data-ttu-id="0f506-126">0: dados do receptor</span><span class="sxs-lookup"><span data-stu-id="0f506-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="0f506-127">1: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="0f506-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="0f506-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="0f506-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="0f506-129">Porcentagem da sessão que o evento LowBandwidth foi acionado para o estado 'Ruim'.</span><span class="sxs-lookup"><span data-stu-id="0f506-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="0f506-130">A largura de banda disponível é insuficiente para uma experiência aceitável de voz.</span><span class="sxs-lookup"><span data-stu-id="0f506-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="0f506-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="0f506-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="0f506-132">Porcentagem da sessão que o evento ReceiveSendQuality foi acionado para o estado 'Ruim'.</span><span class="sxs-lookup"><span data-stu-id="0f506-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="0f506-133">Qualidade da rede em termos de perda de pacote ou jitter é grave e afeta a qualidade do áudio que está sendo recebido.</span><span class="sxs-lookup"><span data-stu-id="0f506-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

