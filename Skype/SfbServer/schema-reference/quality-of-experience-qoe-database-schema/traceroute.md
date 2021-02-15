---
title: Tabela TraceRoute
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: A tabela TraceRoute contém informações de roteamento de chamadas. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 7ecad93cca80a9b7cea73f64158b3c0008a1d6e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831316"
---
# <a name="traceroute-table"></a><span data-ttu-id="3d1f4-104">Tabela TraceRoute</span><span class="sxs-lookup"><span data-stu-id="3d1f4-104">TraceRoute table</span></span>
 
<span data-ttu-id="3d1f4-105">A tabela TraceRoute contém informações de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3d1f4-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="3d1f4-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d1f4-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3d1f4-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3d1f4-107">**Column**</span></span>|<span data-ttu-id="3d1f4-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="3d1f4-108">**Data Type**</span></span>|<span data-ttu-id="3d1f4-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="3d1f4-109">**Key/Index**</span></span>|<span data-ttu-id="3d1f4-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="3d1f4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3d1f4-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="3d1f4-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="3d1f4-112">datetime</span><span class="sxs-lookup"><span data-stu-id="3d1f4-112">datetime</span></span>  <br/> |<span data-ttu-id="3d1f4-113">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="3d1f4-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3d1f4-114">Data e hora de início da chamada.</span><span class="sxs-lookup"><span data-stu-id="3d1f4-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="3d1f4-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="3d1f4-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="3d1f4-116">int</span><span class="sxs-lookup"><span data-stu-id="3d1f4-116">int</span></span>  <br/> |<span data-ttu-id="3d1f4-117">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="3d1f4-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3d1f4-118">Identificador exclusivo usado para distinguir entre várias chamadas que podem ter começado na mesma data e hora.</span><span class="sxs-lookup"><span data-stu-id="3d1f4-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="3d1f4-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="3d1f4-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="3d1f4-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="3d1f4-120">tinyint</span></span>  <br/> |<span data-ttu-id="3d1f4-121">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="3d1f4-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3d1f4-p103">Representa o tipo de linha de vídeo usada na chamada. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="3d1f4-p103">Represents the type of video line used in the call. Allowed values are:</span></span>  <br/> <span data-ttu-id="3d1f4-124">0 - Áudio</span><span class="sxs-lookup"><span data-stu-id="3d1f4-124">0 - Audio</span></span>  <br/> <span data-ttu-id="3d1f4-125">1 - Vídeo</span><span class="sxs-lookup"><span data-stu-id="3d1f4-125">1 - Video</span></span>  <br/> <span data-ttu-id="3d1f4-126">2 - Vídeo panorâmico</span><span class="sxs-lookup"><span data-stu-id="3d1f4-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="3d1f4-127">3 - Compartilhamento de aplicativo/área de trabalho</span><span class="sxs-lookup"><span data-stu-id="3d1f4-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="3d1f4-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="3d1f4-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="3d1f4-129">bit</span><span class="sxs-lookup"><span data-stu-id="3d1f4-129">bit</span></span>  <br/> |<span data-ttu-id="3d1f4-130">Primário</span><span class="sxs-lookup"><span data-stu-id="3d1f4-130">Primary</span></span>  <br/> |<span data-ttu-id="3d1f4-131">Ponto de extremidade que executou a chamada.</span><span class="sxs-lookup"><span data-stu-id="3d1f4-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="3d1f4-132">**Salto**</span><span class="sxs-lookup"><span data-stu-id="3d1f4-132">**Hop**</span></span> <br/> |<span data-ttu-id="3d1f4-133">int</span><span class="sxs-lookup"><span data-stu-id="3d1f4-133">int</span></span>  <br/> ||<span data-ttu-id="3d1f4-134">Salto de rede/</span><span class="sxs-lookup"><span data-stu-id="3d1f4-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="3d1f4-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="3d1f4-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="3d1f4-136">int</span><span class="sxs-lookup"><span data-stu-id="3d1f4-136">int</span></span>  <br/> |<span data-ttu-id="3d1f4-137">Externo</span><span class="sxs-lookup"><span data-stu-id="3d1f4-137">Foreign</span></span>  <br/> |<span data-ttu-id="3d1f4-138">Identificador exclusivo do endereço IP.</span><span class="sxs-lookup"><span data-stu-id="3d1f4-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="3d1f4-139">As informações de endereço IP são armazenadas na [tabela IPAddress](ipaddress.md).</span><span class="sxs-lookup"><span data-stu-id="3d1f4-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="3d1f4-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="3d1f4-140">**RTT**</span></span> <br/> |<span data-ttu-id="3d1f4-141">int</span><span class="sxs-lookup"><span data-stu-id="3d1f4-141">int</span></span>  <br/> ||<span data-ttu-id="3d1f4-p105">Tempo de viagem de ida e volta. O tempo de viagem de ida e volta mede quanto tempo leva para que um pacote de voz chegue ao seu destino e retorne uma notificação de recebimento.</span><span class="sxs-lookup"><span data-stu-id="3d1f4-p105">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

