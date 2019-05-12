---
title: Tabela MonitoredRegionLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: A tabela MonitoredRegionLink é uma tabela de suporte. Cada registro representa um vínculo entre dois países/regiões.
ms.openlocfilehash: 125f29a25b2ee039649dd47dcc405e208d0cd254
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920149"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="e0d1d-104">Tabela MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="e0d1d-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="e0d1d-105">A tabela MonitoredRegionLink é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="e0d1d-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="e0d1d-106">Cada registro representa um vínculo entre dois países/regiões.</span><span class="sxs-lookup"><span data-stu-id="e0d1d-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="e0d1d-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e0d1d-107">**Column**</span></span>|<span data-ttu-id="e0d1d-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e0d1d-108">**Data Type**</span></span>|<span data-ttu-id="e0d1d-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="e0d1d-109">**Key/Index**</span></span>|<span data-ttu-id="e0d1d-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="e0d1d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e0d1d-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="e0d1d-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="e0d1d-112">int</span><span class="sxs-lookup"><span data-stu-id="e0d1d-112">int</span></span>  <br/> |<span data-ttu-id="e0d1d-113">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="e0d1d-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e0d1d-114">Referência da [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="e0d1d-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="e0d1d-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="e0d1d-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="e0d1d-116">int</span><span class="sxs-lookup"><span data-stu-id="e0d1d-116">int</span></span>  <br/> |<span data-ttu-id="e0d1d-117">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="e0d1d-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e0d1d-118">Referência da [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="e0d1d-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

