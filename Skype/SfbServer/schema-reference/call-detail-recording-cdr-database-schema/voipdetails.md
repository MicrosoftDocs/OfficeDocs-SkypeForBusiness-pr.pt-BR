---
title: Exibir VoIPDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: 6fb1dede975e59c0ae56fe9872472310c914f685
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930026"
---
# <a name="voipdetails-view"></a><span data-ttu-id="a286b-104">Exibir VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="a286b-104">VoIPDetails view</span></span>
 
<span data-ttu-id="a286b-105">O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP.</span><span class="sxs-lookup"><span data-stu-id="a286b-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="a286b-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a286b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a286b-107">O modo de exibição VoIPDetails contém todas as colunas no [SessionDetails view](sessiondetails-0.md) além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="a286b-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="a286b-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a286b-108">**Column**</span></span>|<span data-ttu-id="a286b-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a286b-109">**Data Type**</span></span>|<span data-ttu-id="a286b-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a286b-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a286b-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="a286b-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="a286b-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="a286b-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a286b-113">URI do telefone do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="a286b-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="a286b-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="a286b-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="a286b-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="a286b-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a286b-116">URI do telefone do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="a286b-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="a286b-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="a286b-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="a286b-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="a286b-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a286b-119">URI do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="a286b-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="a286b-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="a286b-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="a286b-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a286b-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a286b-122">Tipo de URI do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="a286b-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="a286b-123">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a286b-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a286b-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="a286b-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="a286b-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a286b-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a286b-126">Locatário do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="a286b-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="a286b-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="a286b-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="a286b-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="a286b-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a286b-129">URI do usuário que desconectou da sessão do telefone.</span><span class="sxs-lookup"><span data-stu-id="a286b-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="a286b-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="a286b-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="a286b-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a286b-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a286b-132">Servidor de mediação usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="a286b-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="a286b-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="a286b-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="a286b-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a286b-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a286b-135">Servidor de mediação usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="a286b-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="a286b-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="a286b-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="a286b-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a286b-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a286b-138">Gateway usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="a286b-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="a286b-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="a286b-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="a286b-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a286b-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a286b-141">Gateway usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="a286b-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

