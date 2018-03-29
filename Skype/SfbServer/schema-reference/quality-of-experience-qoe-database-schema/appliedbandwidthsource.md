---
title: Tabela AppliedBandwidthSource
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma fonte.
ms.openlocfilehash: e15df92423a3408e3cb8ae40a0788e1f165961df
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="e89c0-104">Tabela AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="e89c0-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="e89c0-105">A tabela AppliedBandwidthSource é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="e89c0-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="e89c0-106">Cada registro representa uma fonte.</span><span class="sxs-lookup"><span data-stu-id="e89c0-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="e89c0-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e89c0-107">**Column**</span></span>|<span data-ttu-id="e89c0-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e89c0-108">**Data Type**</span></span>|<span data-ttu-id="e89c0-109">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="e89c0-109">**Key/Index**</span></span>|<span data-ttu-id="e89c0-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="e89c0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e89c0-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="e89c0-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="e89c0-112">int</span><span class="sxs-lookup"><span data-stu-id="e89c0-112">int</span></span>  <br/> |<span data-ttu-id="e89c0-113">Primária</span><span class="sxs-lookup"><span data-stu-id="e89c0-113">Primary</span></span>  <br/> |<span data-ttu-id="e89c0-114">Número exclusivo que identifica a origem.</span><span class="sxs-lookup"><span data-stu-id="e89c0-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="e89c0-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="e89c0-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="e89c0-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="e89c0-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="e89c0-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="e89c0-117">Unique</span></span>  <br/> |<span data-ttu-id="e89c0-118">Isso representa a origem do limite de largura de banda que está sendo imposta.</span><span class="sxs-lookup"><span data-stu-id="e89c0-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="e89c0-119">Ele descreve onde o limite de largura de banda é proveniente (por exemplo, "Política de servidor", "Ativar o servidor" ou "Modalidade").</span><span class="sxs-lookup"><span data-stu-id="e89c0-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

