---
title: Exibição VoIPDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: A exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 7f5f1e3cf1540e1a12a9365753e494ff2d8a371e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295661"
---
# <a name="voipdetails-view"></a><span data-ttu-id="3d731-104">Exibição VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="3d731-104">VoIPDetails view</span></span>
 
<span data-ttu-id="3d731-105">A exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP.</span><span class="sxs-lookup"><span data-stu-id="3d731-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="3d731-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d731-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d731-107">A exibição VoIPDetails contém todas as colunas na [exibição SessionDetails](sessiondetails-0.md) , além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="3d731-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="3d731-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3d731-108">**Column**</span></span>|<span data-ttu-id="3d731-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="3d731-109">**Data Type**</span></span>|<span data-ttu-id="3d731-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="3d731-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3d731-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="3d731-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="3d731-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3d731-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3d731-113">URI do telefone do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="3d731-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="3d731-114">**Por telefone**</span><span class="sxs-lookup"><span data-stu-id="3d731-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="3d731-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3d731-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3d731-116">URI do telefone do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="3d731-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="3d731-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="3d731-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="3d731-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3d731-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3d731-119">URL do usuário que desconectou a sessão.</span><span class="sxs-lookup"><span data-stu-id="3d731-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="3d731-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="3d731-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="3d731-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3d731-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3d731-122">Tipo de URI do usuário que desconectou a sessão.</span><span class="sxs-lookup"><span data-stu-id="3d731-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="3d731-123">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3d731-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3d731-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="3d731-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="3d731-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3d731-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3d731-126">Locatário do usuário que desconectou a sessão.</span><span class="sxs-lookup"><span data-stu-id="3d731-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="3d731-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="3d731-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="3d731-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3d731-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3d731-129">URI do telefone do usuário que desconectou a sessão.</span><span class="sxs-lookup"><span data-stu-id="3d731-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="3d731-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="3d731-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="3d731-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3d731-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3d731-132">Servidor de mediação usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="3d731-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="3d731-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="3d731-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="3d731-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3d731-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3d731-135">Servidor de mediação usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="3d731-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="3d731-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="3d731-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="3d731-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3d731-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3d731-138">O gateway usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="3d731-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="3d731-139">**Togateway**</span><span class="sxs-lookup"><span data-stu-id="3d731-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="3d731-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3d731-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3d731-141">O gateway usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="3d731-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

