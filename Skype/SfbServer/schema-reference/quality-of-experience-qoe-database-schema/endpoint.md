---
title: Tabela Endpoint
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: A tabela de pontos de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que participaram em sessões registradas no banco de dados. Cada registro na tabela representa um ponto de extremidade.
ms.openlocfilehash: b64b19a3149fa3d490ea8dc957699c0a114f763c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809549"
---
# <a name="endpoint-table"></a><span data-ttu-id="2f581-104">Tabela Endpoint</span><span class="sxs-lookup"><span data-stu-id="2f581-104">Endpoint table</span></span>
 
<span data-ttu-id="2f581-105">A tabela de pontos de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que participaram em sessões registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2f581-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="2f581-106">Cada registro na tabela representa um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="2f581-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="2f581-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2f581-107">**Column**</span></span>|<span data-ttu-id="2f581-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="2f581-108">**Data Type**</span></span>|<span data-ttu-id="2f581-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="2f581-109">**Key/Index**</span></span>|<span data-ttu-id="2f581-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="2f581-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2f581-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="2f581-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="2f581-112">int</span><span class="sxs-lookup"><span data-stu-id="2f581-112">int</span></span>  <br/> |<span data-ttu-id="2f581-113">Primária</span><span class="sxs-lookup"><span data-stu-id="2f581-113">Primary</span></span>  <br/> |<span data-ttu-id="2f581-114">Número exclusivo que identifica esse ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="2f581-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="2f581-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2f581-115">**Name**</span></span> <br/> |<span data-ttu-id="2f581-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2f581-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2f581-117">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="2f581-117">Unique</span></span>  <br/> |<span data-ttu-id="2f581-118">Nome do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="2f581-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="2f581-119">**Sistema operacional**</span><span class="sxs-lookup"><span data-stu-id="2f581-119">**OS**</span></span> <br/> |<span data-ttu-id="2f581-120">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="2f581-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="2f581-121">Sistema operacional (SO) da empresa.</span><span class="sxs-lookup"><span data-stu-id="2f581-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2f581-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="2f581-122">**CPUName**</span></span> <br/> |<span data-ttu-id="2f581-123">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="2f581-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="2f581-124">Nome da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="2f581-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2f581-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="2f581-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="2f581-126">smallint</span><span class="sxs-lookup"><span data-stu-id="2f581-126">smallint</span></span>  <br/> ||<span data-ttu-id="2f581-127">Número de núcleos da CPU da empresa.</span><span class="sxs-lookup"><span data-stu-id="2f581-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2f581-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="2f581-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="2f581-129">int</span><span class="sxs-lookup"><span data-stu-id="2f581-129">int</span></span>  <br/> ||<span data-ttu-id="2f581-130">Velocidade do processador da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="2f581-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="2f581-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="2f581-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="2f581-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="2f581-132">tinyint</span></span>  <br/> || <span data-ttu-id="2f581-133">Sinalizador de bit que indica se o sistema está em execução em um ambiente virtualizado:</span><span class="sxs-lookup"><span data-stu-id="2f581-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="2f581-134">0x0000-nenhum</span><span class="sxs-lookup"><span data-stu-id="2f581-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="2f581-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="2f581-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="2f581-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="2f581-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="2f581-137">0x0004-Virtual PC</span><span class="sxs-lookup"><span data-stu-id="2f581-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="2f581-138">PC 0x0008-Xen</span><span class="sxs-lookup"><span data-stu-id="2f581-138">0x0008 - Xen PC</span></span> <br/> |
   

