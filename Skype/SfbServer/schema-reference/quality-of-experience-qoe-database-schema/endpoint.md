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
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: A tabela de pontos de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que participaram em sessões registradas no banco de dados. Cada registro na tabela representa um ponto de extremidade.
ms.openlocfilehash: 7d582d382784d04d4495de972aa20673862284f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294989"
---
# <a name="endpoint-table"></a><span data-ttu-id="d7c9e-104">Tabela Endpoint</span><span class="sxs-lookup"><span data-stu-id="d7c9e-104">Endpoint table</span></span>
 
<span data-ttu-id="d7c9e-105">A tabela de pontos de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que participaram em sessões registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d7c9e-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="d7c9e-106">Cada registro na tabela representa um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="d7c9e-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="d7c9e-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d7c9e-107">**Column**</span></span>|<span data-ttu-id="d7c9e-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d7c9e-108">**Data Type**</span></span>|<span data-ttu-id="d7c9e-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="d7c9e-109">**Key/Index**</span></span>|<span data-ttu-id="d7c9e-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="d7c9e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d7c9e-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="d7c9e-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="d7c9e-112">int</span><span class="sxs-lookup"><span data-stu-id="d7c9e-112">int</span></span>  <br/> |<span data-ttu-id="d7c9e-113">Primária</span><span class="sxs-lookup"><span data-stu-id="d7c9e-113">Primary</span></span>  <br/> |<span data-ttu-id="d7c9e-114">Número exclusivo que identifica esse ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="d7c9e-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="d7c9e-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="d7c9e-115">**Name**</span></span> <br/> |<span data-ttu-id="d7c9e-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d7c9e-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d7c9e-117">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="d7c9e-117">Unique</span></span>  <br/> |<span data-ttu-id="d7c9e-118">Nome do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="d7c9e-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="d7c9e-119">**Sistema operacional**</span><span class="sxs-lookup"><span data-stu-id="d7c9e-119">**OS**</span></span> <br/> |<span data-ttu-id="d7c9e-120">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="d7c9e-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="d7c9e-121">Sistema operacional (SO) da empresa.</span><span class="sxs-lookup"><span data-stu-id="d7c9e-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="d7c9e-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="d7c9e-122">**CPUName**</span></span> <br/> |<span data-ttu-id="d7c9e-123">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="d7c9e-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="d7c9e-124">Nome da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="d7c9e-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="d7c9e-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="d7c9e-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="d7c9e-126">smallint</span><span class="sxs-lookup"><span data-stu-id="d7c9e-126">smallint</span></span>  <br/> ||<span data-ttu-id="d7c9e-127">Número de núcleos da CPU da empresa.</span><span class="sxs-lookup"><span data-stu-id="d7c9e-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="d7c9e-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="d7c9e-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="d7c9e-129">int</span><span class="sxs-lookup"><span data-stu-id="d7c9e-129">int</span></span>  <br/> ||<span data-ttu-id="d7c9e-130">Velocidade do processador da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="d7c9e-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="d7c9e-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="d7c9e-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="d7c9e-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="d7c9e-132">tinyint</span></span>  <br/> || <span data-ttu-id="d7c9e-133">Sinalizador de bit que indica se o sistema está em execução em um ambiente virtualizado:</span><span class="sxs-lookup"><span data-stu-id="d7c9e-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="d7c9e-134">0x0000-nenhum</span><span class="sxs-lookup"><span data-stu-id="d7c9e-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="d7c9e-135">0x0001-HyperV</span><span class="sxs-lookup"><span data-stu-id="d7c9e-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="d7c9e-136">0x0002-VMWare</span><span class="sxs-lookup"><span data-stu-id="d7c9e-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="d7c9e-137">0x0004-Virtual PC</span><span class="sxs-lookup"><span data-stu-id="d7c9e-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="d7c9e-138">PC 0x0008-Xen</span><span class="sxs-lookup"><span data-stu-id="d7c9e-138">0x0008 - Xen PC</span></span> <br/> |
   

