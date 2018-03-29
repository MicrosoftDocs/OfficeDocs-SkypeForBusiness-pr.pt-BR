---
title: Tabela MonitoredRegionLink
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
ms.openlocfilehash: 471291788dabee412bffef641624afad2a2c10b4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="ee748-104">Tabela MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="ee748-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="ee748-105">A tabela MonitoredRegionLink é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="ee748-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="ee748-106">Cada registro representa um vínculo entre dois países/regiões.</span><span class="sxs-lookup"><span data-stu-id="ee748-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="ee748-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ee748-107">**Column**</span></span>|<span data-ttu-id="ee748-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ee748-108">**Data Type**</span></span>|<span data-ttu-id="ee748-109">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="ee748-109">**Key/Index**</span></span>|<span data-ttu-id="ee748-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="ee748-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ee748-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="ee748-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="ee748-112">int</span><span class="sxs-lookup"><span data-stu-id="ee748-112">int</span></span>  <br/> |<span data-ttu-id="ee748-113">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="ee748-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ee748-114">Referência da [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="ee748-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="ee748-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="ee748-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="ee748-116">int</span><span class="sxs-lookup"><span data-stu-id="ee748-116">int</span></span>  <br/> |<span data-ttu-id="ee748-117">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="ee748-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ee748-118">Referência da [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="ee748-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

