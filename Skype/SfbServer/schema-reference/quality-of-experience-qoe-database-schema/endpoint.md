---
title: Tabela Endpoint
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: A tabela de ponto de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa um ponto de extremidade.
ms.openlocfilehash: f9c304408006ef9caf5521b8f0bbe28c2d917abe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212239"
---
# <a name="endpoint-table"></a><span data-ttu-id="83a79-104">Tabela Endpoint</span><span class="sxs-lookup"><span data-stu-id="83a79-104">Endpoint table</span></span>
 
<span data-ttu-id="83a79-105">A tabela de ponto de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que tenham participado em sessões gravadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="83a79-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="83a79-106">Cada registro na tabela representa um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="83a79-106">Each record in the table represents one endpoint.</span></span>
  
|<span data-ttu-id="83a79-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="83a79-107">**Column**</span></span>|<span data-ttu-id="83a79-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="83a79-108">**Data Type**</span></span>|<span data-ttu-id="83a79-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="83a79-109">**Key/Index**</span></span>|<span data-ttu-id="83a79-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="83a79-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="83a79-111">**EndpointKey**</span><span class="sxs-lookup"><span data-stu-id="83a79-111">**EndpointKey**</span></span> <br/> |<span data-ttu-id="83a79-112">int</span><span class="sxs-lookup"><span data-stu-id="83a79-112">int</span></span>  <br/> |<span data-ttu-id="83a79-113">Primária</span><span class="sxs-lookup"><span data-stu-id="83a79-113">Primary</span></span>  <br/> |<span data-ttu-id="83a79-114">Número exclusivo que identifica este ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="83a79-114">Unique number identifying this endpoint.</span></span>  <br/> |
|<span data-ttu-id="83a79-115">**Nome**</span><span class="sxs-lookup"><span data-stu-id="83a79-115">**Name**</span></span> <br/> |<span data-ttu-id="83a79-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="83a79-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="83a79-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="83a79-117">Unique</span></span>  <br/> |<span data-ttu-id="83a79-118">Nome do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="83a79-118">Endpoint name.</span></span>  <br/> |
|<span data-ttu-id="83a79-119">**Sistema operacional**</span><span class="sxs-lookup"><span data-stu-id="83a79-119">**OS**</span></span> <br/> |<span data-ttu-id="83a79-120">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="83a79-120">nvarchar(128)</span></span>  <br/> | <br/> |<span data-ttu-id="83a79-121">Sistema operacional (SO) do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="83a79-121">Operating system (OS) of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="83a79-122">**CPUName**</span><span class="sxs-lookup"><span data-stu-id="83a79-122">**CPUName**</span></span> <br/> |<span data-ttu-id="83a79-123">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="83a79-123">nvarchar(128)</span></span>  <br/> ||<span data-ttu-id="83a79-124">Nome da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="83a79-124">CPU name of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="83a79-125">**CPUNumberOfCores**</span><span class="sxs-lookup"><span data-stu-id="83a79-125">**CPUNumberOfCores**</span></span> <br/> |<span data-ttu-id="83a79-126">smallint</span><span class="sxs-lookup"><span data-stu-id="83a79-126">smallint</span></span>  <br/> ||<span data-ttu-id="83a79-127">Número de núcleos de CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="83a79-127">Number of CPU cores of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="83a79-128">**CPUProcessorSpeed**</span><span class="sxs-lookup"><span data-stu-id="83a79-128">**CPUProcessorSpeed**</span></span> <br/> |<span data-ttu-id="83a79-129">int</span><span class="sxs-lookup"><span data-stu-id="83a79-129">int</span></span>  <br/> ||<span data-ttu-id="83a79-130">Velocidade do processador da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="83a79-130">CPU processor speed of the endpoint.</span></span>  <br/> |
|<span data-ttu-id="83a79-131">**VirtualizationFlag**</span><span class="sxs-lookup"><span data-stu-id="83a79-131">**VirtualizationFlag**</span></span> <br/> |<span data-ttu-id="83a79-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="83a79-132">tinyint</span></span>  <br/> || <span data-ttu-id="83a79-133">Sinalizador de bit que indica se o sistema está sendo executado em um ambiente virtualizado:</span><span class="sxs-lookup"><span data-stu-id="83a79-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span> <br/>  <span data-ttu-id="83a79-134">0x0000 - nenhum</span><span class="sxs-lookup"><span data-stu-id="83a79-134">0x0000 - None</span></span> <br/>  <span data-ttu-id="83a79-135">0x0001 - Hyper-v</span><span class="sxs-lookup"><span data-stu-id="83a79-135">0x0001 - HyperV</span></span> <br/>  <span data-ttu-id="83a79-136">0x0002 - VMWare</span><span class="sxs-lookup"><span data-stu-id="83a79-136">0x0002 - VMWare</span></span> <br/>  <span data-ttu-id="83a79-137">0x0004 - virtual PC</span><span class="sxs-lookup"><span data-stu-id="83a79-137">0x0004 - Virtual PC</span></span> <br/>  <span data-ttu-id="83a79-138">0x0008 - Xen PC</span><span class="sxs-lookup"><span data-stu-id="83a79-138">0x0008 - Xen PC</span></span> <br/> |
   

