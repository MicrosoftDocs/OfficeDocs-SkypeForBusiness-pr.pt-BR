---
title: Tabela VideoClientEvent
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Cada registro contém evento de cliente para um ponto de extremidade em uma chamada de vídeo. Normalmente, uma chamada tem dois registros, um para o chamador e outro para o chamador.
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821391"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="dcacd-104">Tabela VideoClientEvent</span><span class="sxs-lookup"><span data-stu-id="dcacd-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="dcacd-105">Cada registro contém evento de cliente para um ponto de extremidade em uma chamada de vídeo.</span><span class="sxs-lookup"><span data-stu-id="dcacd-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="dcacd-106">Normalmente, uma chamada tem dois registros, um para o chamador e outro para o chamador.</span><span class="sxs-lookup"><span data-stu-id="dcacd-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="dcacd-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="dcacd-107">**Column**</span></span>|<span data-ttu-id="dcacd-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="dcacd-108">**Data Type**</span></span>|<span data-ttu-id="dcacd-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="dcacd-109">**Key/Index**</span></span>|<span data-ttu-id="dcacd-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="dcacd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dcacd-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="dcacd-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="dcacd-112">datetime</span><span class="sxs-lookup"><span data-stu-id="dcacd-112">datetime</span></span>  <br/> |<span data-ttu-id="dcacd-113">Primário</span><span class="sxs-lookup"><span data-stu-id="dcacd-113">Primary</span></span>  <br/> |<span data-ttu-id="dcacd-114">Referenciado na tabela [MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="dcacd-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="dcacd-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="dcacd-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="dcacd-116">int</span><span class="sxs-lookup"><span data-stu-id="dcacd-116">int</span></span>  <br/> |<span data-ttu-id="dcacd-117">Primário</span><span class="sxs-lookup"><span data-stu-id="dcacd-117">Primary</span></span>  <br/> |<span data-ttu-id="dcacd-118">Referenciado na tabela [MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="dcacd-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="dcacd-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="dcacd-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="dcacd-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="dcacd-120">tinyint</span></span>  <br/> |<span data-ttu-id="dcacd-121">Primário</span><span class="sxs-lookup"><span data-stu-id="dcacd-121">Primary</span></span>  <br/> |<span data-ttu-id="dcacd-122">Referenciado na tabela [MediaLine](medialine-0.md).</span><span class="sxs-lookup"><span data-stu-id="dcacd-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="dcacd-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="dcacd-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="dcacd-124">bit</span><span class="sxs-lookup"><span data-stu-id="dcacd-124">bit</span></span>  <br/> |<span data-ttu-id="dcacd-125">Primário</span><span class="sxs-lookup"><span data-stu-id="dcacd-125">Primary</span></span>  <br/> |<span data-ttu-id="dcacd-126">0: Dados do destinatário da chamada</span><span class="sxs-lookup"><span data-stu-id="dcacd-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="dcacd-127">1: Dados do chamador</span><span class="sxs-lookup"><span data-stu-id="dcacd-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="dcacd-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="dcacd-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="dcacd-129">Porcentagem de sessão em que o evento LowBandwidth foi acionado para o estado 'Bad'.</span><span class="sxs-lookup"><span data-stu-id="dcacd-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="dcacd-130">A largura de banda disponível é insuficiente para uma experiência de voz aceitável.</span><span class="sxs-lookup"><span data-stu-id="dcacd-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="dcacd-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="dcacd-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="dcacd-132">Porcentagem de sessão em que o evento ReceiveSendQuality foi acionado para o estado 'Bad'.</span><span class="sxs-lookup"><span data-stu-id="dcacd-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="dcacd-133">A qualidade da rede em termos de trem tremida ou perda de pacotes é grave e afeta a qualidade do áudio recebido.</span><span class="sxs-lookup"><span data-stu-id="dcacd-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

