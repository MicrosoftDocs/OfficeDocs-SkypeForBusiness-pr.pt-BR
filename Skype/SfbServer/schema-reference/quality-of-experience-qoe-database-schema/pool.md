---
title: Tabela Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: A tabela de Pool é uma tabela de suporte que armazena informações sobre os vários pools de Front-End. Cada registro na tabela representa um pool.
ms.openlocfilehash: c4451f274e9afadbb7903e4095be22120c430689
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920058"
---
# <a name="pool-table"></a><span data-ttu-id="93296-104">Tabela Pool</span><span class="sxs-lookup"><span data-stu-id="93296-104">Pool table</span></span>
 
<span data-ttu-id="93296-105">A tabela de Pool é uma tabela de suporte que armazena informações sobre os vários pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="93296-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="93296-106">Cada registro na tabela representa um pool.</span><span class="sxs-lookup"><span data-stu-id="93296-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="93296-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="93296-107">**Column**</span></span>|<span data-ttu-id="93296-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="93296-108">**Data Type**</span></span>|<span data-ttu-id="93296-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="93296-109">**Key/Index**</span></span>|<span data-ttu-id="93296-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="93296-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="93296-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="93296-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="93296-112">int</span><span class="sxs-lookup"><span data-stu-id="93296-112">int</span></span>  <br/> |<span data-ttu-id="93296-113">Primária</span><span class="sxs-lookup"><span data-stu-id="93296-113">Primary</span></span>  <br/> |<span data-ttu-id="93296-114">Número exclusivo que identifica este pool.</span><span class="sxs-lookup"><span data-stu-id="93296-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="93296-115">**Nome_conjunto**</span><span class="sxs-lookup"><span data-stu-id="93296-115">**PoolName**</span></span> <br/> |<span data-ttu-id="93296-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="93296-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="93296-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="93296-117">Unique</span></span>  <br/> |<span data-ttu-id="93296-118">FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="93296-118">Pool FQDN.</span></span>  <br/> |
   

