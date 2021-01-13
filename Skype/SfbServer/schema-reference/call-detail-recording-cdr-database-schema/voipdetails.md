---
title: Exibição VoIPDetails
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde no mínimo um usuário é um usuário VoIP. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: b42fecc7a0f43f86dba2439a373c7013c605a5e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813071"
---
# <a name="voipdetails-view"></a><span data-ttu-id="33251-104">Exibição VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="33251-104">VoIPDetails view</span></span>
 
<span data-ttu-id="33251-105">O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde no mínimo um usuário é um usuário VoIP.</span><span class="sxs-lookup"><span data-stu-id="33251-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="33251-106">Essa exibição foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="33251-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="33251-107">O visualização VoIPDetails contém todas as colunas no [exibição SessionDetails,](sessiondetails-0.md) além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="33251-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="33251-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="33251-108">**Column**</span></span>|<span data-ttu-id="33251-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="33251-109">**Data Type**</span></span>|<span data-ttu-id="33251-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="33251-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="33251-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="33251-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="33251-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="33251-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="33251-113">URI do telefone do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="33251-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="33251-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="33251-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="33251-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="33251-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="33251-116">URI do telefone do usuário que entrou na sessão.</span><span class="sxs-lookup"><span data-stu-id="33251-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="33251-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="33251-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="33251-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="33251-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="33251-119">URI do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="33251-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="33251-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="33251-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="33251-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33251-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="33251-122">Tipo da URI do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="33251-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="33251-123">Consulte a [tabela UriTypes para](uritypes.md) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="33251-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="33251-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="33251-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="33251-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33251-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="33251-126">Locatário do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="33251-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="33251-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="33251-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="33251-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="33251-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="33251-129">URI do telefone do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="33251-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="33251-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="33251-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="33251-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33251-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="33251-132">Servidor de Mediação usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="33251-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="33251-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="33251-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="33251-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33251-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="33251-135">Servidor de Mediação usado pelo usuário que entrou na sessão.</span><span class="sxs-lookup"><span data-stu-id="33251-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="33251-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="33251-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="33251-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33251-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="33251-138">Gateway usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="33251-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="33251-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="33251-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="33251-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="33251-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="33251-141">Gateway usado pelo usuário que entrou na sessão.</span><span class="sxs-lookup"><span data-stu-id="33251-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

