---
title: Tabela MonitoredRegionLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: A tabela MonitoredRegionLink é uma tabela de suporte. Cada registro representa um vínculo entre dois países/regiões.
ms.openlocfilehash: 0df5cd8abe957ed952bdf656a67e1d423cc57f33
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884411"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="7dbfb-104">Tabela MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="7dbfb-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="7dbfb-105">A tabela MonitoredRegionLink é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="7dbfb-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="7dbfb-106">Cada registro representa um vínculo entre dois países/regiões.</span><span class="sxs-lookup"><span data-stu-id="7dbfb-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="7dbfb-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="7dbfb-107">**Column**</span></span>|<span data-ttu-id="7dbfb-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="7dbfb-108">**Data Type**</span></span>|<span data-ttu-id="7dbfb-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="7dbfb-109">**Key/Index**</span></span>|<span data-ttu-id="7dbfb-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="7dbfb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7dbfb-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="7dbfb-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="7dbfb-112">int</span><span class="sxs-lookup"><span data-stu-id="7dbfb-112">int</span></span>  <br/> |<span data-ttu-id="7dbfb-113">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="7dbfb-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="7dbfb-114">Referência da [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="7dbfb-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="7dbfb-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="7dbfb-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="7dbfb-116">int</span><span class="sxs-lookup"><span data-stu-id="7dbfb-116">int</span></span>  <br/> |<span data-ttu-id="7dbfb-117">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="7dbfb-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="7dbfb-118">Referência da [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="7dbfb-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

