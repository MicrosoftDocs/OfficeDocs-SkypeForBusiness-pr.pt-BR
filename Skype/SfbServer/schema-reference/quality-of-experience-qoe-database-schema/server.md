---
title: Tabela Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: A tabela de servidor é uma tabela de suporte. Cada registro representa um servidor.
ms.openlocfilehash: 877743f5d589cd4fea34039786b33bd410069bb3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874305"
---
# <a name="server-table"></a><span data-ttu-id="9ca65-104">Tabela Server</span><span class="sxs-lookup"><span data-stu-id="9ca65-104">Server table</span></span>
 
<span data-ttu-id="9ca65-105">A tabela de servidor é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="9ca65-105">The Server table is a supporting table.</span></span> <span data-ttu-id="9ca65-106">Cada registro representa um servidor.</span><span class="sxs-lookup"><span data-stu-id="9ca65-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="9ca65-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9ca65-107">**Column**</span></span>|<span data-ttu-id="9ca65-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9ca65-108">**Data Type**</span></span>|<span data-ttu-id="9ca65-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="9ca65-109">**Key/Index**</span></span>|<span data-ttu-id="9ca65-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="9ca65-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9ca65-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="9ca65-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="9ca65-112">int</span><span class="sxs-lookup"><span data-stu-id="9ca65-112">int</span></span>  <br/> |<span data-ttu-id="9ca65-113">Primária</span><span class="sxs-lookup"><span data-stu-id="9ca65-113">Primary</span></span>  <br/> |<span data-ttu-id="9ca65-114">Número exclusivo que identifica o servidor.</span><span class="sxs-lookup"><span data-stu-id="9ca65-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="9ca65-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="9ca65-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="9ca65-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9ca65-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9ca65-117">índice</span><span class="sxs-lookup"><span data-stu-id="9ca65-117">index</span></span>  <br/> |<span data-ttu-id="9ca65-118">Cadeia de caracteres de endereço MAC.</span><span class="sxs-lookup"><span data-stu-id="9ca65-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="9ca65-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="9ca65-119">**ServerType**</span></span> <br/> |<span data-ttu-id="9ca65-120">int</span><span class="sxs-lookup"><span data-stu-id="9ca65-120">int</span></span>  <br/> |<span data-ttu-id="9ca65-121">Externa</span><span class="sxs-lookup"><span data-stu-id="9ca65-121">Foreign</span></span>  <br/> |<span data-ttu-id="9ca65-122">1: servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="9ca65-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="9ca65-123">2: A / V Conferencing Server16394: uma borda a / V v32769: Gateway</span><span class="sxs-lookup"><span data-stu-id="9ca65-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="9ca65-124">**Nome_conjunto**</span><span class="sxs-lookup"><span data-stu-id="9ca65-124">**PoolName**</span></span> <br/> |<span data-ttu-id="9ca65-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="9ca65-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="9ca65-126">Pool que ao qual o servidor pertence.</span><span class="sxs-lookup"><span data-stu-id="9ca65-126">Pool the server belongs to.</span></span> <span data-ttu-id="9ca65-127">Só se aplica A / V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="9ca65-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="9ca65-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="9ca65-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="9ca65-129">datetime</span><span class="sxs-lookup"><span data-stu-id="9ca65-129">datetime</span></span>  <br/> ||<span data-ttu-id="9ca65-130">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="9ca65-130">For internal use only.</span></span>  <br/> |
   

