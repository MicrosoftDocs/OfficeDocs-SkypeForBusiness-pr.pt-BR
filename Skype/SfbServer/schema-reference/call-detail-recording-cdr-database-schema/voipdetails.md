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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: A exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814769"
---
# <a name="voipdetails-view"></a><span data-ttu-id="c8d7c-104">Exibição VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="c8d7c-104">VoIPDetails view</span></span>
 
<span data-ttu-id="c8d7c-105">A exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP.</span><span class="sxs-lookup"><span data-stu-id="c8d7c-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="c8d7c-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8d7c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8d7c-107">A exibição VoIPDetails contém todas as colunas na [exibição SessionDetails](sessiondetails-0.md) , além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="c8d7c-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="c8d7c-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c8d7c-108">**Column**</span></span>|<span data-ttu-id="c8d7c-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c8d7c-109">**Data Type**</span></span>|<span data-ttu-id="c8d7c-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="c8d7c-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c8d7c-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="c8d7c-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="c8d7c-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c8d7c-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c8d7c-113">URI do telefone do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c8d7c-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="c8d7c-114">**Por telefone**</span><span class="sxs-lookup"><span data-stu-id="c8d7c-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="c8d7c-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c8d7c-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c8d7c-116">URI do telefone do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="c8d7c-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="c8d7c-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="c8d7c-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="c8d7c-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c8d7c-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c8d7c-119">URL do usuário que desconectou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c8d7c-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="c8d7c-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="c8d7c-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="c8d7c-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c8d7c-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c8d7c-122">Tipo de URI do usuário que desconectou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c8d7c-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="c8d7c-123">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c8d7c-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c8d7c-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="c8d7c-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="c8d7c-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c8d7c-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c8d7c-126">Locatário do usuário que desconectou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c8d7c-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="c8d7c-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="c8d7c-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="c8d7c-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c8d7c-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c8d7c-129">URI do telefone do usuário que desconectou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c8d7c-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="c8d7c-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="c8d7c-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="c8d7c-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c8d7c-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c8d7c-132">Servidor de mediação usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c8d7c-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="c8d7c-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="c8d7c-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="c8d7c-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c8d7c-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c8d7c-135">Servidor de mediação usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="c8d7c-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="c8d7c-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="c8d7c-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="c8d7c-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c8d7c-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c8d7c-138">O gateway usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c8d7c-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="c8d7c-139">**Togateway**</span><span class="sxs-lookup"><span data-stu-id="c8d7c-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="c8d7c-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c8d7c-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c8d7c-141">O gateway usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="c8d7c-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

