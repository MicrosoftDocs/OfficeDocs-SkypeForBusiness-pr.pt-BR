---
title: Tabela MonitoredRegionLink
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: A tabela MonitoredRegionLink é uma tabela de suporte. Cada registro representa um link entre dois países/regiões.
ms.openlocfilehash: f30ba249f89a2247e0e03c71fc97f05e69c59bcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806341"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="c36b9-104">Tabela MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="c36b9-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="c36b9-105">A tabela MonitoredRegionLink é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="c36b9-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="c36b9-106">Cada registro representa um link entre dois países/regiões.</span><span class="sxs-lookup"><span data-stu-id="c36b9-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="c36b9-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c36b9-107">**Column**</span></span>|<span data-ttu-id="c36b9-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c36b9-108">**Data Type**</span></span>|<span data-ttu-id="c36b9-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="c36b9-109">**Key/Index**</span></span>|<span data-ttu-id="c36b9-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="c36b9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c36b9-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="c36b9-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="c36b9-112">int</span><span class="sxs-lookup"><span data-stu-id="c36b9-112">int</span></span>  <br/> |<span data-ttu-id="c36b9-113">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="c36b9-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="c36b9-114">Referenciado na tabela [Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="c36b9-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="c36b9-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="c36b9-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="c36b9-116">int</span><span class="sxs-lookup"><span data-stu-id="c36b9-116">int</span></span>  <br/> |<span data-ttu-id="c36b9-117">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="c36b9-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="c36b9-118">Referenciado na tabela [Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="c36b9-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

