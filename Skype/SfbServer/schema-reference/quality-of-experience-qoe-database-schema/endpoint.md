---
title: Tabela endpoint
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: A tabela Endpoint é uma tabela de suporte que armazena informações sobre os pontos de extremidade que participaram de sessões gravadas no banco de dados. Cada registro na tabela representa um ponto de extremidade.
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823061"
---
# <a name="endpoint-table"></a><span data-ttu-id="a3a3b-104">Tabela endpoint</span><span class="sxs-lookup"><span data-stu-id="a3a3b-104">Endpoint table</span></span>
 
<span data-ttu-id="a3a3b-105">A tabela Endpoint é uma tabela de suporte que armazena informações sobre os pontos de extremidade que participaram de sessões gravadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="a3a3b-106">Cada registro na tabela representa um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="a3a3b-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a3a3b-107">**Column**</span></span>|<span data-ttu-id="a3a3b-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a3a3b-108">**Data Type**</span></span>|<span data-ttu-id="a3a3b-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="a3a3b-109">**Key/Index**</span></span>|<span data-ttu-id="a3a3b-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a3a3b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a3a3b-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="a3a3b-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="a3a3b-112">int</span><span class="sxs-lookup"><span data-stu-id="a3a3b-112">int</span></span>  <br/> |<span data-ttu-id="a3a3b-113">Primário</span><span class="sxs-lookup"><span data-stu-id="a3a3b-113">Primary</span></span>  <br/> |<span data-ttu-id="a3a3b-114">Número exclusivo que identifica esse ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="a3a3b-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a3a3b-115">**Name**</span></span> <br/> |<span data-ttu-id="a3a3b-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a3a3b-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a3a3b-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="a3a3b-117">Unique</span></span>  <br/> |<span data-ttu-id="a3a3b-118">Nome do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="a3a3b-119">**Sistema operacional**</span><span class="sxs-lookup"><span data-stu-id="a3a3b-119">**OS**</span></span> <br/> |<span data-ttu-id="a3a3b-120">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="a3a3b-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="a3a3b-121">Sistema operacional (SO) do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="a3a3b-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="a3a3b-122">**CPUName**</span></span> <br/> |<span data-ttu-id="a3a3b-123">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="a3a3b-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="a3a3b-124">Nome da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="a3a3b-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="a3a3b-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="a3a3b-126">smallint</span><span class="sxs-lookup"><span data-stu-id="a3a3b-126">smallint</span></span>  <br/> ||<span data-ttu-id="a3a3b-127">Número de núcleos da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="a3a3b-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="a3a3b-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="a3a3b-129">int</span><span class="sxs-lookup"><span data-stu-id="a3a3b-129">int</span></span>  <br/> ||<span data-ttu-id="a3a3b-130">Velocidade do processador da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a3a3b-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="a3a3b-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="a3a3b-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="a3a3b-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="a3a3b-132">tinyint</span></span>  <br/> || <span data-ttu-id="a3a3b-133">Sinalizador de bits que indica se o sistema está sendo executado em um ambiente virtualizado:</span><span class="sxs-lookup"><span data-stu-id="a3a3b-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="a3a3b-134">0x0000 - Nenhum</span><span class="sxs-lookup"><span data-stu-id="a3a3b-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="a3a3b-135">0x0001 - HyperV</span><span class="sxs-lookup"><span data-stu-id="a3a3b-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="a3a3b-136">0x0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="a3a3b-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="a3a3b-137">0x0004 - Virtual PC</span><span class="sxs-lookup"><span data-stu-id="a3a3b-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="a3a3b-138">0x0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="a3a3b-138">0x0008 - Xen PC</span></span> <br/> |
   

