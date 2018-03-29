---
title: Tabela SessionCorrelation
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: A tabela SessionCorrelation é uma tabela de suporte. Cada registro representa uma CorrelationID que é utilizado para correlacionar múltiplas sessões.
ms.openlocfilehash: 8a9c9661b10548bf3ebf402aa4654fced2ca709b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="aa2c0-104">Tabela SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="aa2c0-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="aa2c0-105">A tabela SessionCorrelation é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="aa2c0-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="aa2c0-106">Cada registro representa uma CorrelationID que é utilizado para correlacionar múltiplas sessões.</span><span class="sxs-lookup"><span data-stu-id="aa2c0-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="aa2c0-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="aa2c0-107">**Column**</span></span>|<span data-ttu-id="aa2c0-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="aa2c0-108">**Data Type**</span></span>|<span data-ttu-id="aa2c0-109">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="aa2c0-109">**Key/Index**</span></span>|<span data-ttu-id="aa2c0-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="aa2c0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aa2c0-111">**Soma de verificação**</span><span class="sxs-lookup"><span data-stu-id="aa2c0-111">**Checksum**</span></span> <br/> |<span data-ttu-id="aa2c0-112">int</span><span class="sxs-lookup"><span data-stu-id="aa2c0-112">int</span></span>  <br/> |||
|<span data-ttu-id="aa2c0-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="aa2c0-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="aa2c0-114">int</span><span class="sxs-lookup"><span data-stu-id="aa2c0-114">int</span></span>  <br/> |<span data-ttu-id="aa2c0-115">Primária</span><span class="sxs-lookup"><span data-stu-id="aa2c0-115">Primary</span></span>  <br/> |<span data-ttu-id="aa2c0-116">Número exclusivo que identifica A / V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="aa2c0-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="aa2c0-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="aa2c0-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="aa2c0-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa2c0-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="aa2c0-119">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="aa2c0-119">Unique</span></span>  <br/> |<span data-ttu-id="aa2c0-120">Sessões que são correlacionadas terão o mesmo ID de correlação.</span><span class="sxs-lookup"><span data-stu-id="aa2c0-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="aa2c0-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="aa2c0-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="aa2c0-122">datetime</span><span class="sxs-lookup"><span data-stu-id="aa2c0-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="aa2c0-123">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="aa2c0-123">For internal use only.</span></span>  <br/> |
   

