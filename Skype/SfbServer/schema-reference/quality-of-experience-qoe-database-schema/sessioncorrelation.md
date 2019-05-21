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
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: A tabela SessionCorrelation é uma tabela de suporte. Cada registro representa um CorrelationId, que é usado para correlacionar várias sessões.
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294653"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="0c6b2-104">Tabela SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="0c6b2-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="0c6b2-105">A tabela SessionCorrelation é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="0c6b2-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="0c6b2-106">Cada registro representa um CorrelationId, que é usado para correlacionar várias sessões.</span><span class="sxs-lookup"><span data-stu-id="0c6b2-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="0c6b2-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="0c6b2-107">**Column**</span></span>|<span data-ttu-id="0c6b2-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="0c6b2-108">**Data Type**</span></span>|<span data-ttu-id="0c6b2-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="0c6b2-109">**Key/Index**</span></span>|<span data-ttu-id="0c6b2-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="0c6b2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0c6b2-111">**Prova**</span><span class="sxs-lookup"><span data-stu-id="0c6b2-111">**Checksum**</span></span> <br/> |<span data-ttu-id="0c6b2-112">int</span><span class="sxs-lookup"><span data-stu-id="0c6b2-112">int</span></span>  <br/> |||
|<span data-ttu-id="0c6b2-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="0c6b2-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="0c6b2-114">int</span><span class="sxs-lookup"><span data-stu-id="0c6b2-114">int</span></span>  <br/> |<span data-ttu-id="0c6b2-115">Primária</span><span class="sxs-lookup"><span data-stu-id="0c6b2-115">Primary</span></span>  <br/> |<span data-ttu-id="0c6b2-116">Número exclusivo que identifica esse servidor de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="0c6b2-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="0c6b2-117">**CorrelationId**</span><span class="sxs-lookup"><span data-stu-id="0c6b2-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="0c6b2-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0c6b2-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0c6b2-119">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="0c6b2-119">Unique</span></span>  <br/> |<span data-ttu-id="0c6b2-120">As sessões correlacionadas terão a mesma ID de correlação.</span><span class="sxs-lookup"><span data-stu-id="0c6b2-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="0c6b2-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="0c6b2-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="0c6b2-122">datetime</span><span class="sxs-lookup"><span data-stu-id="0c6b2-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="0c6b2-123">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="0c6b2-123">For internal use only.</span></span>  <br/> |
   

