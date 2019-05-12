---
title: Tabela Conference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: A tabela de conferência é uma tabela de suporte. Cada registro representa uma conferência ou sessão ponto a ponto.
ms.openlocfilehash: 0914e98aed4aea16e5301ccae454e925663454a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920163"
---
# <a name="conference-table"></a><span data-ttu-id="d2d36-104">Tabela Conference</span><span class="sxs-lookup"><span data-stu-id="d2d36-104">Conference table</span></span>
 
<span data-ttu-id="d2d36-105">A tabela de conferência é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="d2d36-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="d2d36-106">Cada registro representa uma conferência ou sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="d2d36-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="d2d36-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d2d36-107">**Column**</span></span>|<span data-ttu-id="d2d36-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d2d36-108">**Data Type**</span></span>|<span data-ttu-id="d2d36-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="d2d36-109">**Key/Index**</span></span>|<span data-ttu-id="d2d36-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="d2d36-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d2d36-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="d2d36-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="d2d36-112">int</span><span class="sxs-lookup"><span data-stu-id="d2d36-112">int</span></span>  <br/> |<span data-ttu-id="d2d36-113">Primária</span><span class="sxs-lookup"><span data-stu-id="d2d36-113">Primary</span></span>  <br/> |<span data-ttu-id="d2d36-114">Número exclusivo que identifica o registro desta conferência.</span><span class="sxs-lookup"><span data-stu-id="d2d36-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="d2d36-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="d2d36-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="d2d36-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d2d36-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d2d36-117">exclusivo</span><span class="sxs-lookup"><span data-stu-id="d2d36-117">unique</span></span>  <br/> |<span data-ttu-id="d2d36-118">Caso se trate de uma conferência ou DialogID se este de URI de conferência é uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="d2d36-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="d2d36-119">**Soma de verificação**</span><span class="sxs-lookup"><span data-stu-id="d2d36-119">**Checksum**</span></span> <br/> |<span data-ttu-id="d2d36-120">int</span><span class="sxs-lookup"><span data-stu-id="d2d36-120">int</span></span>  <br/> |<span data-ttu-id="d2d36-121">índice</span><span class="sxs-lookup"><span data-stu-id="d2d36-121">index</span></span>  <br/> |<span data-ttu-id="d2d36-122">Soma de verificação o URI de conferência.</span><span class="sxs-lookup"><span data-stu-id="d2d36-122">Checksum of the conference URI.</span></span> <span data-ttu-id="d2d36-123">Isso é usado internamente.</span><span class="sxs-lookup"><span data-stu-id="d2d36-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="d2d36-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d2d36-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d2d36-125">datetime</span><span class="sxs-lookup"><span data-stu-id="d2d36-125">datetime</span></span>  <br/> ||<span data-ttu-id="d2d36-126">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="d2d36-126">For internal use only.</span></span>  <br/> |
   

