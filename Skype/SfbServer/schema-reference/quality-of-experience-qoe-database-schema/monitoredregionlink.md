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
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: A tabela MonitoredRegionLink é uma tabela de suporte. Cada registro representa um link entre dois países/regiões.
ms.openlocfilehash: fdace97e0a7c9685f59471074cca64ede4fcc63d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294870"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="1f036-104">Tabela MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="1f036-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="1f036-105">A tabela MonitoredRegionLink é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="1f036-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="1f036-106">Cada registro representa um link entre dois países/regiões.</span><span class="sxs-lookup"><span data-stu-id="1f036-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="1f036-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="1f036-107">**Column**</span></span>|<span data-ttu-id="1f036-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="1f036-108">**Data Type**</span></span>|<span data-ttu-id="1f036-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="1f036-109">**Key/Index**</span></span>|<span data-ttu-id="1f036-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="1f036-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1f036-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="1f036-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="1f036-112">int</span><span class="sxs-lookup"><span data-stu-id="1f036-112">int</span></span>  <br/> |<span data-ttu-id="1f036-113">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="1f036-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="1f036-114">Referenciado na [tabela Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="1f036-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="1f036-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="1f036-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="1f036-116">int</span><span class="sxs-lookup"><span data-stu-id="1f036-116">int</span></span>  <br/> |<span data-ttu-id="1f036-117">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="1f036-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="1f036-118">Referenciado na [tabela Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="1f036-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

