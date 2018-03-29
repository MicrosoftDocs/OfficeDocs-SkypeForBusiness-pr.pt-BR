---
title: Exibir VoIPDetails
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: 93c2afb6383817a4d3941d5b427565fb1d0db098
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="voipdetails-view"></a><span data-ttu-id="91596-104">Exibir VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="91596-104">VoIPDetails view</span></span>
 
<span data-ttu-id="91596-105">O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP.</span><span class="sxs-lookup"><span data-stu-id="91596-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="91596-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91596-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="91596-107">O modo de exibição VoIPDetails contém todas as colunas no [SessionDetails view](sessiondetails-0.md) além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="91596-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="91596-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="91596-108">**Column**</span></span>|<span data-ttu-id="91596-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="91596-109">**Data Type**</span></span>|<span data-ttu-id="91596-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="91596-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="91596-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="91596-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="91596-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="91596-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="91596-113">URI do telefone do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="91596-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="91596-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="91596-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="91596-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="91596-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="91596-116">URI do telefone do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="91596-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="91596-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="91596-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="91596-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="91596-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="91596-119">URI do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="91596-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="91596-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="91596-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="91596-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91596-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="91596-122">Tipo de URI do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="91596-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="91596-123">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="91596-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="91596-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="91596-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="91596-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91596-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="91596-126">Locatário do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="91596-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="91596-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="91596-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="91596-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="91596-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="91596-129">URI do usuário que desconectou da sessão do telefone.</span><span class="sxs-lookup"><span data-stu-id="91596-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="91596-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="91596-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="91596-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91596-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="91596-132">Servidor de mediação usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="91596-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="91596-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="91596-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="91596-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91596-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="91596-135">Servidor de mediação usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="91596-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="91596-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="91596-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="91596-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91596-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="91596-138">Gateway usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="91596-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="91596-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="91596-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="91596-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91596-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="91596-141">Gateway usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="91596-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

