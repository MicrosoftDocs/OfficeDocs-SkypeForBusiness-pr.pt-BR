---
title: Tabela Endpoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: A tabela de ponto de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa um ponto de extremidade.
ms.openlocfilehash: 4917b0817d8fcedbc3a20b2c41d3ed62ce468c5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920107"
---
# <a name="endpoint-table"></a><span data-ttu-id="0ba20-104">Tabela Endpoint</span><span class="sxs-lookup"><span data-stu-id="0ba20-104">Endpoint table</span></span>
 
<span data-ttu-id="0ba20-105">A tabela de ponto de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que tenham participado em sessões gravadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0ba20-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="0ba20-106">Cada registro na tabela representa um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0ba20-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="0ba20-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="0ba20-107">**Column**</span></span>|<span data-ttu-id="0ba20-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="0ba20-108">**Data Type**</span></span>|<span data-ttu-id="0ba20-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="0ba20-109">**Key/Index**</span></span>|<span data-ttu-id="0ba20-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="0ba20-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0ba20-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="0ba20-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="0ba20-112">int</span><span class="sxs-lookup"><span data-stu-id="0ba20-112">int</span></span>  <br/> |<span data-ttu-id="0ba20-113">Primária</span><span class="sxs-lookup"><span data-stu-id="0ba20-113">Primary</span></span>  <br/> |<span data-ttu-id="0ba20-114">Número exclusivo que identifica este ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0ba20-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="0ba20-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0ba20-115">**Name**</span></span> <br/> |<span data-ttu-id="0ba20-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0ba20-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0ba20-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="0ba20-117">Unique</span></span>  <br/> |<span data-ttu-id="0ba20-118">Nome do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0ba20-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="0ba20-119">**Sistema operacional**</span><span class="sxs-lookup"><span data-stu-id="0ba20-119">**OS**</span></span> <br/> |<span data-ttu-id="0ba20-120">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="0ba20-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="0ba20-121">Sistema operacional (SO) do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0ba20-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="0ba20-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="0ba20-122">**CPUName**</span></span> <br/> |<span data-ttu-id="0ba20-123">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="0ba20-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="0ba20-124">Nome da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0ba20-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="0ba20-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="0ba20-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="0ba20-126">smallint</span><span class="sxs-lookup"><span data-stu-id="0ba20-126">smallint</span></span>  <br/> ||<span data-ttu-id="0ba20-127">Número de núcleos de CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0ba20-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="0ba20-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="0ba20-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="0ba20-129">int</span><span class="sxs-lookup"><span data-stu-id="0ba20-129">int</span></span>  <br/> ||<span data-ttu-id="0ba20-130">Velocidade do processador da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0ba20-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="0ba20-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="0ba20-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="0ba20-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="0ba20-132">tinyint</span></span>  <br/> || <span data-ttu-id="0ba20-133">Sinalizador de bit que indica se o sistema está sendo executado em um ambiente virtualizado:</span><span class="sxs-lookup"><span data-stu-id="0ba20-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="0ba20-134">0x0000 - nenhum</span><span class="sxs-lookup"><span data-stu-id="0ba20-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="0ba20-135">0x0001 - Hyper-v</span><span class="sxs-lookup"><span data-stu-id="0ba20-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="0ba20-136">0x0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="0ba20-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="0ba20-137">0x0004 - virtual PC</span><span class="sxs-lookup"><span data-stu-id="0ba20-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="0ba20-138">0x0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="0ba20-138">0x0008 - Xen PC</span></span> <br/> |
   

