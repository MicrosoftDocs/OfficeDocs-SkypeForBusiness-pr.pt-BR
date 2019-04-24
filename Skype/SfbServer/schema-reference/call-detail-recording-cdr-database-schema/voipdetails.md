---
title: Exibir VoIPDetails
ms.reviewer: ''
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
ms.openlocfilehash: 940c3874d5ce8eb8a4d2261de56b8988b6d3a4c9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212702"
---
# <a name="voipdetails-view"></a><span data-ttu-id="0a111-104">Exibir VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="0a111-104">VoIPDetails view</span></span>
 
<span data-ttu-id="0a111-105">O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP.</span><span class="sxs-lookup"><span data-stu-id="0a111-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="0a111-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0a111-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0a111-107">O modo de exibição VoIPDetails contém todas as colunas no [SessionDetails view](sessiondetails-0.md) além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="0a111-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="0a111-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="0a111-108">**Column**</span></span>|<span data-ttu-id="0a111-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="0a111-109">**Data Type**</span></span>|<span data-ttu-id="0a111-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="0a111-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0a111-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="0a111-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="0a111-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="0a111-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0a111-113">URI do telefone do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="0a111-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="0a111-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="0a111-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="0a111-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="0a111-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0a111-116">URI do telefone do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="0a111-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="0a111-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="0a111-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="0a111-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="0a111-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0a111-119">URI do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="0a111-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="0a111-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="0a111-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="0a111-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0a111-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0a111-122">Tipo de URI do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="0a111-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="0a111-123">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0a111-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0a111-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="0a111-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="0a111-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0a111-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0a111-126">Locatário do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="0a111-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="0a111-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="0a111-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="0a111-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="0a111-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0a111-129">URI do usuário que desconectou da sessão do telefone.</span><span class="sxs-lookup"><span data-stu-id="0a111-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="0a111-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="0a111-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="0a111-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0a111-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0a111-132">Servidor de mediação usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="0a111-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="0a111-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="0a111-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="0a111-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0a111-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0a111-135">Servidor de mediação usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="0a111-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="0a111-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="0a111-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="0a111-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0a111-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0a111-138">Gateway usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="0a111-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="0a111-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="0a111-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="0a111-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0a111-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0a111-141">Gateway usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="0a111-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

