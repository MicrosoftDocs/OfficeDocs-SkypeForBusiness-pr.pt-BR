---
title: Tabela SessionCorrelation
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: A tabela SessionCorrelation é uma tabela de suporte. Cada registro representa um CorrelationID que é usado para correlacionar várias sessões.
ms.openlocfilehash: 36b617517f3642a2150c72369db858eee62a4a87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802651"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="b9bd8-104">Tabela SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="b9bd8-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="b9bd8-105">A tabela SessionCorrelation é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="b9bd8-106">Cada registro representa um CorrelationID usado para correlacionar várias sessões.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="b9bd8-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b9bd8-107">**Column**</span></span>|<span data-ttu-id="b9bd8-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b9bd8-108">**Data Type**</span></span>|<span data-ttu-id="b9bd8-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="b9bd8-109">**Key/Index**</span></span>|<span data-ttu-id="b9bd8-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="b9bd8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b9bd8-111">**Soma de verificação**</span><span class="sxs-lookup"><span data-stu-id="b9bd8-111">**Checksum**</span></span> <br/> |<span data-ttu-id="b9bd8-112">int</span><span class="sxs-lookup"><span data-stu-id="b9bd8-112">int</span></span>  <br/> |||
|<span data-ttu-id="b9bd8-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="b9bd8-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="b9bd8-114">int</span><span class="sxs-lookup"><span data-stu-id="b9bd8-114">int</span></span>  <br/> |<span data-ttu-id="b9bd8-115">Primário</span><span class="sxs-lookup"><span data-stu-id="b9bd8-115">Primary</span></span>  <br/> |<span data-ttu-id="b9bd8-116">Número exclusivo que identifica este Servidor de Conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="b9bd8-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="b9bd8-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="b9bd8-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b9bd8-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b9bd8-119">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="b9bd8-119">Unique</span></span>  <br/> |<span data-ttu-id="b9bd8-120">As sessões correlacionadas terão a mesma ID de correlação.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="b9bd8-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="b9bd8-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="b9bd8-122">datetime</span><span class="sxs-lookup"><span data-stu-id="b9bd8-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="b9bd8-123">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b9bd8-123">For internal use only.</span></span>  <br/> |
   

