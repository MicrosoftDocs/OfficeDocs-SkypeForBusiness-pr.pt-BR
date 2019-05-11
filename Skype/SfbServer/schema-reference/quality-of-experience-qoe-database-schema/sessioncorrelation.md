---
title: Tabela SessionCorrelation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: A tabela SessionCorrelation é uma tabela de suporte. Cada registro representa uma CorrelationID que é utilizado para correlacionar múltiplas sessões.
ms.openlocfilehash: 4efd1aeba45fb12aee646c401f492450f375aa20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907077"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="2399a-104">Tabela SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="2399a-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="2399a-105">A tabela SessionCorrelation é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="2399a-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="2399a-106">Cada registro representa uma CorrelationID que é utilizado para correlacionar múltiplas sessões.</span><span class="sxs-lookup"><span data-stu-id="2399a-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="2399a-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2399a-107">**Column**</span></span>|<span data-ttu-id="2399a-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="2399a-108">**Data Type**</span></span>|<span data-ttu-id="2399a-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="2399a-109">**Key/Index**</span></span>|<span data-ttu-id="2399a-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="2399a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2399a-111">**Soma de verificação**</span><span class="sxs-lookup"><span data-stu-id="2399a-111">**Checksum**</span></span> <br/> |<span data-ttu-id="2399a-112">int</span><span class="sxs-lookup"><span data-stu-id="2399a-112">int</span></span>  <br/> |||
|<span data-ttu-id="2399a-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="2399a-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="2399a-114">int</span><span class="sxs-lookup"><span data-stu-id="2399a-114">int</span></span>  <br/> |<span data-ttu-id="2399a-115">Primária</span><span class="sxs-lookup"><span data-stu-id="2399a-115">Primary</span></span>  <br/> |<span data-ttu-id="2399a-116">Número exclusivo que identifica A / V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="2399a-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="2399a-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="2399a-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="2399a-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2399a-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="2399a-119">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="2399a-119">Unique</span></span>  <br/> |<span data-ttu-id="2399a-120">Sessões que são correlacionadas terão o mesmo ID de correlação.</span><span class="sxs-lookup"><span data-stu-id="2399a-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="2399a-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="2399a-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="2399a-122">datetime</span><span class="sxs-lookup"><span data-stu-id="2399a-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="2399a-123">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2399a-123">For internal use only.</span></span>  <br/> |
   

