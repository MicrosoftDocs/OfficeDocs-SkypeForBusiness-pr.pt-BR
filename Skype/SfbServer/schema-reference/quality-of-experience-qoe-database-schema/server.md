---
title: Tabela Server
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: A tabela Server é uma tabela de suporte. Cada registro representa um servidor.
ms.openlocfilehash: 7f26ed9053c65acb8cfd2e586edbd77fdfa7472b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802701"
---
# <a name="server-table"></a><span data-ttu-id="7cbc6-104">Tabela Server</span><span class="sxs-lookup"><span data-stu-id="7cbc6-104">Server table</span></span>
 
<span data-ttu-id="7cbc6-105">A tabela Server é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="7cbc6-105">The Server table is a supporting table.</span></span> <span data-ttu-id="7cbc6-106">Cada registro representa um servidor.</span><span class="sxs-lookup"><span data-stu-id="7cbc6-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="7cbc6-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="7cbc6-107">**Column**</span></span>|<span data-ttu-id="7cbc6-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="7cbc6-108">**Data Type**</span></span>|<span data-ttu-id="7cbc6-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="7cbc6-109">**Key/Index**</span></span>|<span data-ttu-id="7cbc6-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="7cbc6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7cbc6-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="7cbc6-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="7cbc6-112">int</span><span class="sxs-lookup"><span data-stu-id="7cbc6-112">int</span></span>  <br/> |<span data-ttu-id="7cbc6-113">Primário</span><span class="sxs-lookup"><span data-stu-id="7cbc6-113">Primary</span></span>  <br/> |<span data-ttu-id="7cbc6-114">Número exclusivo que identifica o servidor.</span><span class="sxs-lookup"><span data-stu-id="7cbc6-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="7cbc6-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="7cbc6-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="7cbc6-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7cbc6-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7cbc6-117">index</span><span class="sxs-lookup"><span data-stu-id="7cbc6-117">index</span></span>  <br/> |<span data-ttu-id="7cbc6-118">Cadeia de caracteres de endereço MAC.</span><span class="sxs-lookup"><span data-stu-id="7cbc6-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="7cbc6-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="7cbc6-119">**ServerType**</span></span> <br/> |<span data-ttu-id="7cbc6-120">int</span><span class="sxs-lookup"><span data-stu-id="7cbc6-120">int</span></span>  <br/> |<span data-ttu-id="7cbc6-121">Externo</span><span class="sxs-lookup"><span data-stu-id="7cbc6-121">Foreign</span></span>  <br/> |<span data-ttu-id="7cbc6-122">1: Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="7cbc6-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="7cbc6-123">2: Servidor de Conferência A/V16394: Serviço de Borda A/V32769: Gateway</span><span class="sxs-lookup"><span data-stu-id="7cbc6-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="7cbc6-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="7cbc6-124">**PoolName**</span></span> <br/> |<span data-ttu-id="7cbc6-125">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="7cbc6-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="7cbc6-126">Pool ao que o servidor pertence.</span><span class="sxs-lookup"><span data-stu-id="7cbc6-126">Pool the server belongs to.</span></span> <span data-ttu-id="7cbc6-127">Aplicável somente ao Servidor de Conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="7cbc6-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="7cbc6-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="7cbc6-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="7cbc6-129">datetime</span><span class="sxs-lookup"><span data-stu-id="7cbc6-129">datetime</span></span>  <br/> ||<span data-ttu-id="7cbc6-130">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="7cbc6-130">For internal use only.</span></span>  <br/> |
   

