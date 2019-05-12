---
title: Tabela VideoClientEvent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contém um evento do cliente para um ponto de extremidade em uma chamada de vídeo. Normalmente, uma chamada tem dois registros, um para o chamador e um para o receptor.
ms.openlocfilehash: 58179630534733985e062bbe0fafa1bbfd8499db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906823"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="b999c-104">Tabela VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="b999c-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="b999c-105">Cada registro contém um evento do cliente para um ponto de extremidade em uma chamada de vídeo.</span><span class="sxs-lookup"><span data-stu-id="b999c-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="b999c-106">Normalmente, uma chamada tem dois registros, um para o chamador e um para o receptor.</span><span class="sxs-lookup"><span data-stu-id="b999c-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="b999c-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b999c-107">**Column**</span></span>|<span data-ttu-id="b999c-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b999c-108">**Data Type**</span></span>|<span data-ttu-id="b999c-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="b999c-109">**Key/Index**</span></span>|<span data-ttu-id="b999c-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="b999c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b999c-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="b999c-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="b999c-112">datetime</span><span class="sxs-lookup"><span data-stu-id="b999c-112">datetime</span></span>  <br/> |<span data-ttu-id="b999c-113">Primária</span><span class="sxs-lookup"><span data-stu-id="b999c-113">Primary</span></span>  <br/> |<span data-ttu-id="b999c-114">Referenciado de [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="b999c-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="b999c-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="b999c-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="b999c-116">int</span><span class="sxs-lookup"><span data-stu-id="b999c-116">int</span></span>  <br/> |<span data-ttu-id="b999c-117">Primária</span><span class="sxs-lookup"><span data-stu-id="b999c-117">Primary</span></span>  <br/> |<span data-ttu-id="b999c-118">Referenciado de [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="b999c-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="b999c-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="b999c-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="b999c-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="b999c-120">tinyint</span></span>  <br/> |<span data-ttu-id="b999c-121">Primária</span><span class="sxs-lookup"><span data-stu-id="b999c-121">Primary</span></span>  <br/> |<span data-ttu-id="b999c-122">Referenciado de [MediaLine table](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="b999c-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="b999c-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="b999c-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="b999c-124">bit</span><span class="sxs-lookup"><span data-stu-id="b999c-124">bit</span></span>  <br/> |<span data-ttu-id="b999c-125">Primária</span><span class="sxs-lookup"><span data-stu-id="b999c-125">Primary</span></span>  <br/> |<span data-ttu-id="b999c-126">0: dados do receptor</span><span class="sxs-lookup"><span data-stu-id="b999c-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="b999c-127">1: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="b999c-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="b999c-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="b999c-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="b999c-129">Porcentagem da sessão que o evento LowBandwidth foi acionado para o estado 'Ruim'.</span><span class="sxs-lookup"><span data-stu-id="b999c-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="b999c-130">A largura de banda disponível é insuficiente para uma experiência aceitável de voz.</span><span class="sxs-lookup"><span data-stu-id="b999c-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="b999c-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="b999c-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="b999c-132">Porcentagem da sessão que o evento ReceiveSendQuality foi acionado para o estado 'Ruim'.</span><span class="sxs-lookup"><span data-stu-id="b999c-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="b999c-133">Qualidade da rede em termos de perda de pacote ou jitter é grave e afeta a qualidade do áudio que está sendo recebido.</span><span class="sxs-lookup"><span data-stu-id="b999c-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

