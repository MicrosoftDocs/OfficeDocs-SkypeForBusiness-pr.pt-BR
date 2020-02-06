---
title: Tabela SessionCorrelation
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: A tabela SessionCorrelation é uma tabela de suporte. Cada registro representa um CorrelationId, que é usado para correlacionar várias sessões.
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805739"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="6de2d-104">Tabela SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="6de2d-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="6de2d-105">A tabela SessionCorrelation é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="6de2d-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="6de2d-106">Cada registro representa um CorrelationId, que é usado para correlacionar várias sessões.</span><span class="sxs-lookup"><span data-stu-id="6de2d-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="6de2d-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6de2d-107">**Column**</span></span>|<span data-ttu-id="6de2d-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="6de2d-108">**Data Type**</span></span>|<span data-ttu-id="6de2d-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="6de2d-109">**Key/Index**</span></span>|<span data-ttu-id="6de2d-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="6de2d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6de2d-111">**Prova**</span><span class="sxs-lookup"><span data-stu-id="6de2d-111">**Checksum**</span></span> <br/> |<span data-ttu-id="6de2d-112">int</span><span class="sxs-lookup"><span data-stu-id="6de2d-112">int</span></span>  <br/> |||
|<span data-ttu-id="6de2d-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="6de2d-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="6de2d-114">int</span><span class="sxs-lookup"><span data-stu-id="6de2d-114">int</span></span>  <br/> |<span data-ttu-id="6de2d-115">Primária</span><span class="sxs-lookup"><span data-stu-id="6de2d-115">Primary</span></span>  <br/> |<span data-ttu-id="6de2d-116">Número exclusivo que identifica esse servidor de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="6de2d-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="6de2d-117">**CorrelationId**</span><span class="sxs-lookup"><span data-stu-id="6de2d-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="6de2d-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6de2d-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6de2d-119">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="6de2d-119">Unique</span></span>  <br/> |<span data-ttu-id="6de2d-120">As sessões correlacionadas terão a mesma ID de correlação.</span><span class="sxs-lookup"><span data-stu-id="6de2d-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="6de2d-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="6de2d-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="6de2d-122">datetime</span><span class="sxs-lookup"><span data-stu-id="6de2d-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="6de2d-123">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="6de2d-123">For internal use only.</span></span>  <br/> |
   

