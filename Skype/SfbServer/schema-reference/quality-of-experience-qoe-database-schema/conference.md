---
title: Tabela Conference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: A tabela de conferência é uma tabela de suporte. Cada registro representa uma conferência ou sessão ponto a ponto.
ms.openlocfilehash: bae144ff574f19155e11b8a2fbfd3548df356c2a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212260"
---
# <a name="conference-table"></a><span data-ttu-id="84e2f-104">Tabela Conference</span><span class="sxs-lookup"><span data-stu-id="84e2f-104">Conference table</span></span>
 
<span data-ttu-id="84e2f-105">A tabela de conferência é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="84e2f-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="84e2f-106">Cada registro representa uma conferência ou sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="84e2f-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="84e2f-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="84e2f-107">**Column**</span></span>|<span data-ttu-id="84e2f-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="84e2f-108">**Data Type**</span></span>|<span data-ttu-id="84e2f-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="84e2f-109">**Key/Index**</span></span>|<span data-ttu-id="84e2f-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="84e2f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="84e2f-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="84e2f-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="84e2f-112">int</span><span class="sxs-lookup"><span data-stu-id="84e2f-112">int</span></span>  <br/> |<span data-ttu-id="84e2f-113">Primária</span><span class="sxs-lookup"><span data-stu-id="84e2f-113">Primary</span></span>  <br/> |<span data-ttu-id="84e2f-114">Número exclusivo que identifica o registro desta conferência.</span><span class="sxs-lookup"><span data-stu-id="84e2f-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="84e2f-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="84e2f-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="84e2f-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="84e2f-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="84e2f-117">exclusivo</span><span class="sxs-lookup"><span data-stu-id="84e2f-117">unique</span></span>  <br/> |<span data-ttu-id="84e2f-118">Caso se trate de uma conferência ou DialogID se este de URI de conferência é uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="84e2f-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="84e2f-119">**Soma de verificação**</span><span class="sxs-lookup"><span data-stu-id="84e2f-119">**Checksum**</span></span> <br/> |<span data-ttu-id="84e2f-120">int</span><span class="sxs-lookup"><span data-stu-id="84e2f-120">int</span></span>  <br/> |<span data-ttu-id="84e2f-121">índice</span><span class="sxs-lookup"><span data-stu-id="84e2f-121">index</span></span>  <br/> |<span data-ttu-id="84e2f-122">Soma de verificação o URI de conferência.</span><span class="sxs-lookup"><span data-stu-id="84e2f-122">Checksum of the conference URI.</span></span> <span data-ttu-id="84e2f-123">Isso é usado internamente.</span><span class="sxs-lookup"><span data-stu-id="84e2f-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="84e2f-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="84e2f-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="84e2f-125">datetime</span><span class="sxs-lookup"><span data-stu-id="84e2f-125">datetime</span></span>  <br/> ||<span data-ttu-id="84e2f-126">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="84e2f-126">For internal use only.</span></span>  <br/> |
   

