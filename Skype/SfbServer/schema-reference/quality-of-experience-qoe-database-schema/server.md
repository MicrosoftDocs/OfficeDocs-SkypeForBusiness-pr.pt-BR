---
title: Tabela Server
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: A tabela do servidor é uma tabela de suporte. Cada registro representa um servidor.
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806129"
---
# <a name="server-table"></a><span data-ttu-id="07479-104">Tabela Server</span><span class="sxs-lookup"><span data-stu-id="07479-104">Server table</span></span>
 
<span data-ttu-id="07479-105">A tabela do servidor é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="07479-105">The Server table is a supporting table.</span></span> <span data-ttu-id="07479-106">Cada registro representa um servidor.</span><span class="sxs-lookup"><span data-stu-id="07479-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="07479-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="07479-107">**Column**</span></span>|<span data-ttu-id="07479-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="07479-108">**Data Type**</span></span>|<span data-ttu-id="07479-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="07479-109">**Key/Index**</span></span>|<span data-ttu-id="07479-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="07479-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07479-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="07479-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="07479-112">int</span><span class="sxs-lookup"><span data-stu-id="07479-112">int</span></span>  <br/> |<span data-ttu-id="07479-113">Primária</span><span class="sxs-lookup"><span data-stu-id="07479-113">Primary</span></span>  <br/> |<span data-ttu-id="07479-114">Número exclusivo que identifica o servidor.</span><span class="sxs-lookup"><span data-stu-id="07479-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="07479-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="07479-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="07479-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="07479-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="07479-117">dedo</span><span class="sxs-lookup"><span data-stu-id="07479-117">index</span></span>  <br/> |<span data-ttu-id="07479-118">Cadeia de caracteres de endereço MAC.</span><span class="sxs-lookup"><span data-stu-id="07479-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="07479-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="07479-119">**ServerType**</span></span> <br/> |<span data-ttu-id="07479-120">int</span><span class="sxs-lookup"><span data-stu-id="07479-120">int</span></span>  <br/> |<span data-ttu-id="07479-121">Exterior</span><span class="sxs-lookup"><span data-stu-id="07479-121">Foreign</span></span>  <br/> |<span data-ttu-id="07479-122">1: servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="07479-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="07479-123">2: a/V Conferência Server16394: A/V Edge service32769: gateway</span><span class="sxs-lookup"><span data-stu-id="07479-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="07479-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="07479-124">**PoolName**</span></span> <br/> |<span data-ttu-id="07479-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="07479-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="07479-126">Pool ao qual o servidor pertence.</span><span class="sxs-lookup"><span data-stu-id="07479-126">Pool the server belongs to.</span></span> <span data-ttu-id="07479-127">Aplicável somente para o servidor de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="07479-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="07479-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="07479-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="07479-129">datetime</span><span class="sxs-lookup"><span data-stu-id="07479-129">datetime</span></span>  <br/> ||<span data-ttu-id="07479-130">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="07479-130">For internal use only.</span></span>  <br/> |
   

