---
title: Tabela AppliedBandwidthSource
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma fonte.
ms.openlocfilehash: 49e4fd4b2c2543399d073d5d03e8cccad8b0038e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924847"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="58346-104">Tabela AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="58346-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="58346-105">A tabela AppliedBandwidthSource é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="58346-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="58346-106">Cada registro representa uma fonte.</span><span class="sxs-lookup"><span data-stu-id="58346-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="58346-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="58346-107">**Column**</span></span>|<span data-ttu-id="58346-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="58346-108">**Data Type**</span></span>|<span data-ttu-id="58346-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="58346-109">**Key/Index**</span></span>|<span data-ttu-id="58346-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="58346-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="58346-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="58346-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="58346-112">int</span><span class="sxs-lookup"><span data-stu-id="58346-112">int</span></span>  <br/> |<span data-ttu-id="58346-113">Primária</span><span class="sxs-lookup"><span data-stu-id="58346-113">Primary</span></span>  <br/> |<span data-ttu-id="58346-114">Número exclusivo que identifica a origem.</span><span class="sxs-lookup"><span data-stu-id="58346-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="58346-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="58346-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="58346-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="58346-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="58346-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="58346-117">Unique</span></span>  <br/> |<span data-ttu-id="58346-118">Isso representa a origem do limite de largura de banda que está sendo imposta.</span><span class="sxs-lookup"><span data-stu-id="58346-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="58346-119">Ele descreve onde o limite de largura de banda é proveniente (por exemplo, "Política de servidor", "Ativar o servidor" ou "Modalidade").</span><span class="sxs-lookup"><span data-stu-id="58346-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

