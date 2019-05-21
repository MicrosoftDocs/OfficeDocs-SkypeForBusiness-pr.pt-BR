---
title: Tabela Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: A tabela de pool é uma tabela de suporte que armazena informações sobre os vários pools de front-end. Cada registro na tabela representa um pool.
ms.openlocfilehash: c101a10d40292c89c29e108739195a97fa22e5c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294800"
---
# <a name="pool-table"></a><span data-ttu-id="a5b6d-104">Tabela Pool</span><span class="sxs-lookup"><span data-stu-id="a5b6d-104">Pool table</span></span>
 
<span data-ttu-id="a5b6d-105">A tabela de pool é uma tabela de suporte que armazena informações sobre os vários pools de front-end.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="a5b6d-106">Cada registro na tabela representa um pool.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="a5b6d-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a5b6d-107">**Column**</span></span>|<span data-ttu-id="a5b6d-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a5b6d-108">**Data Type**</span></span>|<span data-ttu-id="a5b6d-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="a5b6d-109">**Key/Index**</span></span>|<span data-ttu-id="a5b6d-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a5b6d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a5b6d-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="a5b6d-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="a5b6d-112">int</span><span class="sxs-lookup"><span data-stu-id="a5b6d-112">int</span></span>  <br/> |<span data-ttu-id="a5b6d-113">Primária</span><span class="sxs-lookup"><span data-stu-id="a5b6d-113">Primary</span></span>  <br/> |<span data-ttu-id="a5b6d-114">Número exclusivo que identifica este pool.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="a5b6d-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="a5b6d-115">**PoolName**</span></span> <br/> |<span data-ttu-id="a5b6d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a5b6d-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a5b6d-117">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="a5b6d-117">Unique</span></span>  <br/> |<span data-ttu-id="a5b6d-118">FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="a5b6d-118">Pool FQDN.</span></span>  <br/> |
   

