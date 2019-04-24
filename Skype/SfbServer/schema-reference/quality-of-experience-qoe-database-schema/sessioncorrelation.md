---
title: Tabela SessionCorrelation
ms.reviewer: ''
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
ms.openlocfilehash: 8c41ab5c52c6b4d06a3c3953e8d969488680e8d3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212113"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="6526b-104">Tabela SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="6526b-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="6526b-105">A tabela SessionCorrelation é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="6526b-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="6526b-106">Cada registro representa uma CorrelationID que é utilizado para correlacionar múltiplas sessões.</span><span class="sxs-lookup"><span data-stu-id="6526b-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="6526b-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6526b-107">**Column**</span></span>|<span data-ttu-id="6526b-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="6526b-108">**Data Type**</span></span>|<span data-ttu-id="6526b-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="6526b-109">**Key/Index**</span></span>|<span data-ttu-id="6526b-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="6526b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6526b-111">**Soma de verificação**</span><span class="sxs-lookup"><span data-stu-id="6526b-111">**Checksum**</span></span> <br/> |<span data-ttu-id="6526b-112">int</span><span class="sxs-lookup"><span data-stu-id="6526b-112">int</span></span>  <br/> |||
|<span data-ttu-id="6526b-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="6526b-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="6526b-114">int</span><span class="sxs-lookup"><span data-stu-id="6526b-114">int</span></span>  <br/> |<span data-ttu-id="6526b-115">Primária</span><span class="sxs-lookup"><span data-stu-id="6526b-115">Primary</span></span>  <br/> |<span data-ttu-id="6526b-116">Número exclusivo que identifica A / V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="6526b-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="6526b-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="6526b-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="6526b-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6526b-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6526b-119">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="6526b-119">Unique</span></span>  <br/> |<span data-ttu-id="6526b-120">Sessões que são correlacionadas terão o mesmo ID de correlação.</span><span class="sxs-lookup"><span data-stu-id="6526b-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="6526b-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="6526b-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="6526b-122">datetime</span><span class="sxs-lookup"><span data-stu-id="6526b-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="6526b-123">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="6526b-123">For internal use only.</span></span>  <br/> |
   

