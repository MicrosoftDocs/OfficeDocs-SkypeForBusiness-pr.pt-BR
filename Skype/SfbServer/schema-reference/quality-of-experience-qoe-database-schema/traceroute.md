---
title: Tabela de TraceRoute
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: A tabela TraceRoute contém informações de roteamento de chamadas. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805109"
---
# <a name="traceroute-table"></a><span data-ttu-id="2e4a8-104">Tabela de TraceRoute</span><span class="sxs-lookup"><span data-stu-id="2e4a8-104">TraceRoute table</span></span>
 
<span data-ttu-id="2e4a8-105">A tabela TraceRoute contém informações de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="2e4a8-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="2e4a8-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2e4a8-107">**Column**</span></span>|<span data-ttu-id="2e4a8-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="2e4a8-108">**Data Type**</span></span>|<span data-ttu-id="2e4a8-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="2e4a8-109">**Key/Index**</span></span>|<span data-ttu-id="2e4a8-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="2e4a8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2e4a8-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="2e4a8-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="2e4a8-112">datetime</span><span class="sxs-lookup"><span data-stu-id="2e4a8-112">datetime</span></span>  <br/> |<span data-ttu-id="2e4a8-113">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="2e4a8-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2e4a8-114">Data e hora em que a chamada começou.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="2e4a8-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="2e4a8-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="2e4a8-116">int</span><span class="sxs-lookup"><span data-stu-id="2e4a8-116">int</span></span>  <br/> |<span data-ttu-id="2e4a8-117">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="2e4a8-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2e4a8-118">Identificador exclusivo usado para distinguir entre várias chamadas que podem ter começado na mesma data e ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="2e4a8-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="2e4a8-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="2e4a8-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="2e4a8-120">tinyint</span></span>  <br/> |<span data-ttu-id="2e4a8-121">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="2e4a8-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2e4a8-122">Representa o tipo de linha de vídeo usado na chamada.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="2e4a8-123">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="2e4a8-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="2e4a8-124">0-áudio</span><span class="sxs-lookup"><span data-stu-id="2e4a8-124">0 - Audio</span></span>  <br/> <span data-ttu-id="2e4a8-125">1-vídeo</span><span class="sxs-lookup"><span data-stu-id="2e4a8-125">1 - Video</span></span>  <br/> <span data-ttu-id="2e4a8-126">2-vídeo panorâmico</span><span class="sxs-lookup"><span data-stu-id="2e4a8-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="2e4a8-127">3 – compartilhamento de aplicativos/área de trabalho</span><span class="sxs-lookup"><span data-stu-id="2e4a8-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="2e4a8-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="2e4a8-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="2e4a8-129">bit</span><span class="sxs-lookup"><span data-stu-id="2e4a8-129">bit</span></span>  <br/> |<span data-ttu-id="2e4a8-130">Primária</span><span class="sxs-lookup"><span data-stu-id="2e4a8-130">Primary</span></span>  <br/> |<span data-ttu-id="2e4a8-131">Ponto de extremidade que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="2e4a8-132">**Hop**</span><span class="sxs-lookup"><span data-stu-id="2e4a8-132">**Hop**</span></span> <br/> |<span data-ttu-id="2e4a8-133">int</span><span class="sxs-lookup"><span data-stu-id="2e4a8-133">int</span></span>  <br/> ||<span data-ttu-id="2e4a8-134">Salto de rede/</span><span class="sxs-lookup"><span data-stu-id="2e4a8-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="2e4a8-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="2e4a8-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="2e4a8-136">int</span><span class="sxs-lookup"><span data-stu-id="2e4a8-136">int</span></span>  <br/> |<span data-ttu-id="2e4a8-137">Exterior</span><span class="sxs-lookup"><span data-stu-id="2e4a8-137">Foreign</span></span>  <br/> |<span data-ttu-id="2e4a8-138">Identificador exclusivo do endereço IP.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="2e4a8-139">As informações de endereço IP são armazenadas na [tabela IPAddress](ipaddress.md).</span><span class="sxs-lookup"><span data-stu-id="2e4a8-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="2e4a8-140">**RESPOSTA**</span><span class="sxs-lookup"><span data-stu-id="2e4a8-140">**RTT**</span></span> <br/> |<span data-ttu-id="2e4a8-141">int</span><span class="sxs-lookup"><span data-stu-id="2e4a8-141">int</span></span>  <br/> ||<span data-ttu-id="2e4a8-142">Tempo de resposta.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-142">Roundtrip time.</span></span> <span data-ttu-id="2e4a8-143">O tempo de resposta mede a quantidade de tempo que leva para um pacote de voz alcançar seu destino e enviar notificações de volta para que ele seja recebido.</span><span class="sxs-lookup"><span data-stu-id="2e4a8-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

