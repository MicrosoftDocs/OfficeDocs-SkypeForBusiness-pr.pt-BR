---
title: Tabela MonitoredRegionLink
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: A tabela MonitoredRegionLink é uma tabela de suporte. Cada registro representa um link entre dois países/regiões.
ms.openlocfilehash: a6b92460e2b097460681023f7d6877f02c046bdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807809"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="282ee-104">Tabela MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="282ee-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="282ee-105">A tabela MonitoredRegionLink é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="282ee-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="282ee-106">Cada registro representa um link entre dois países/regiões.</span><span class="sxs-lookup"><span data-stu-id="282ee-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="282ee-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="282ee-107">**Column**</span></span>|<span data-ttu-id="282ee-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="282ee-108">**Data Type**</span></span>|<span data-ttu-id="282ee-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="282ee-109">**Key/Index**</span></span>|<span data-ttu-id="282ee-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="282ee-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="282ee-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="282ee-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="282ee-112">int</span><span class="sxs-lookup"><span data-stu-id="282ee-112">int</span></span>  <br/> |<span data-ttu-id="282ee-113">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="282ee-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="282ee-114">Referenciado na [tabela Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="282ee-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="282ee-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="282ee-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="282ee-116">int</span><span class="sxs-lookup"><span data-stu-id="282ee-116">int</span></span>  <br/> |<span data-ttu-id="282ee-117">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="282ee-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="282ee-118">Referenciado na [tabela Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="282ee-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

