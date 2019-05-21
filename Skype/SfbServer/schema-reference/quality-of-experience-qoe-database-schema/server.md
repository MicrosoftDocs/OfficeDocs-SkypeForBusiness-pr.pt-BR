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
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: A tabela do servidor é uma tabela de suporte. Cada registro representa um servidor.
ms.openlocfilehash: 93ba62c262b95b46b76cd445be04a0bc53c5a960
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294709"
---
# <a name="server-table"></a><span data-ttu-id="e4901-104">Tabela Server</span><span class="sxs-lookup"><span data-stu-id="e4901-104">Server table</span></span>
 
<span data-ttu-id="e4901-105">A tabela do servidor é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="e4901-105">The Server table is a supporting table.</span></span> <span data-ttu-id="e4901-106">Cada registro representa um servidor.</span><span class="sxs-lookup"><span data-stu-id="e4901-106">Each record represents one server.</span></span> 
  
|<span data-ttu-id="e4901-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e4901-107">**Column**</span></span>|<span data-ttu-id="e4901-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e4901-108">**Data Type**</span></span>|<span data-ttu-id="e4901-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="e4901-109">**Key/Index**</span></span>|<span data-ttu-id="e4901-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="e4901-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e4901-111">**ServerKey**</span><span class="sxs-lookup"><span data-stu-id="e4901-111">**ServerKey**</span></span> <br/> |<span data-ttu-id="e4901-112">int</span><span class="sxs-lookup"><span data-stu-id="e4901-112">int</span></span>  <br/> |<span data-ttu-id="e4901-113">Primária</span><span class="sxs-lookup"><span data-stu-id="e4901-113">Primary</span></span>  <br/> |<span data-ttu-id="e4901-114">Número exclusivo que identifica o servidor.</span><span class="sxs-lookup"><span data-stu-id="e4901-114">Unique number identifying the server.</span></span>  <br/> |
|<span data-ttu-id="e4901-115">**FQDNOrIP**</span><span class="sxs-lookup"><span data-stu-id="e4901-115">**FQDNOrIP**</span></span> <br/> |<span data-ttu-id="e4901-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e4901-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e4901-117">dedo</span><span class="sxs-lookup"><span data-stu-id="e4901-117">index</span></span>  <br/> |<span data-ttu-id="e4901-118">Cadeia de caracteres de endereço MAC.</span><span class="sxs-lookup"><span data-stu-id="e4901-118">MAC address string.</span></span>  <br/> |
|<span data-ttu-id="e4901-119">**ServerType**</span><span class="sxs-lookup"><span data-stu-id="e4901-119">**ServerType**</span></span> <br/> |<span data-ttu-id="e4901-120">int</span><span class="sxs-lookup"><span data-stu-id="e4901-120">int</span></span>  <br/> |<span data-ttu-id="e4901-121">Exterior</span><span class="sxs-lookup"><span data-stu-id="e4901-121">Foreign</span></span>  <br/> |<span data-ttu-id="e4901-122">1: servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="e4901-122">1: Mediation Server</span></span>  <br/> <span data-ttu-id="e4901-123">2: a/V Conferência Server16394: A/V Edge service32769: gateway</span><span class="sxs-lookup"><span data-stu-id="e4901-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span>  <br/> |
|<span data-ttu-id="e4901-124">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="e4901-124">**PoolName**</span></span> <br/> |<span data-ttu-id="e4901-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="e4901-125">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="e4901-126">Pool ao qual o servidor pertence.</span><span class="sxs-lookup"><span data-stu-id="e4901-126">Pool the server belongs to.</span></span> <span data-ttu-id="e4901-127">Aplicável somente para o servidor de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="e4901-127">Only applicable for the A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="e4901-128">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="e4901-128">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="e4901-129">datetime</span><span class="sxs-lookup"><span data-stu-id="e4901-129">datetime</span></span>  <br/> ||<span data-ttu-id="e4901-130">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e4901-130">For internal use only.</span></span>  <br/> |
   

