---
title: Tabela Pool
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: A tabela de Pool é uma tabela de suporte que armazena informações sobre os vários pools de Front-End. Cada registro na tabela representa um pool.
ms.openlocfilehash: 8ce54d4b0a20fa405f34bb14b3eecb9ad395884e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="pool-table"></a><span data-ttu-id="c532c-104">Tabela Pool</span><span class="sxs-lookup"><span data-stu-id="c532c-104">Pool table</span></span>
 
<span data-ttu-id="c532c-105">A tabela de Pool é uma tabela de suporte que armazena informações sobre os vários pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="c532c-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="c532c-106">Cada registro na tabela representa um pool.</span><span class="sxs-lookup"><span data-stu-id="c532c-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="c532c-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c532c-107">**Column**</span></span>|<span data-ttu-id="c532c-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c532c-108">**Data Type**</span></span>|<span data-ttu-id="c532c-109">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="c532c-109">**Key/Index**</span></span>|<span data-ttu-id="c532c-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="c532c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c532c-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="c532c-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="c532c-112">int</span><span class="sxs-lookup"><span data-stu-id="c532c-112">int</span></span>  <br/> |<span data-ttu-id="c532c-113">Primária</span><span class="sxs-lookup"><span data-stu-id="c532c-113">Primary</span></span>  <br/> |<span data-ttu-id="c532c-114">Número exclusivo que identifica este pool.</span><span class="sxs-lookup"><span data-stu-id="c532c-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="c532c-115">**Nome_conjunto**</span><span class="sxs-lookup"><span data-stu-id="c532c-115">**PoolName**</span></span> <br/> |<span data-ttu-id="c532c-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c532c-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c532c-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="c532c-117">Unique</span></span>  <br/> |<span data-ttu-id="c532c-118">FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="c532c-118">Pool FQDN.</span></span>  <br/> |
   

