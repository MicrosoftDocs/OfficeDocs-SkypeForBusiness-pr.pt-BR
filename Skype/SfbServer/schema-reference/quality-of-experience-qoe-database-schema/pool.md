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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: A tabela de pool é uma tabela de suporte que armazena informações sobre os vários pools de front-end. Cada registro na tabela representa um pool.
ms.openlocfilehash: 2b6dfb924c3e7a79a323ebbabd90e74ba08ebf04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807399"
---
# <a name="pool-table"></a><span data-ttu-id="4ecff-104">Tabela Pool</span><span class="sxs-lookup"><span data-stu-id="4ecff-104">Pool table</span></span>
 
<span data-ttu-id="4ecff-105">A tabela de pool é uma tabela de suporte que armazena informações sobre os vários pools de front-end.</span><span class="sxs-lookup"><span data-stu-id="4ecff-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="4ecff-106">Cada registro na tabela representa um pool.</span><span class="sxs-lookup"><span data-stu-id="4ecff-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="4ecff-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4ecff-107">**Column**</span></span>|<span data-ttu-id="4ecff-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4ecff-108">**Data Type**</span></span>|<span data-ttu-id="4ecff-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="4ecff-109">**Key/Index**</span></span>|<span data-ttu-id="4ecff-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="4ecff-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4ecff-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="4ecff-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="4ecff-112">int</span><span class="sxs-lookup"><span data-stu-id="4ecff-112">int</span></span>  <br/> |<span data-ttu-id="4ecff-113">Primária</span><span class="sxs-lookup"><span data-stu-id="4ecff-113">Primary</span></span>  <br/> |<span data-ttu-id="4ecff-114">Número exclusivo que identifica este pool.</span><span class="sxs-lookup"><span data-stu-id="4ecff-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="4ecff-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="4ecff-115">**PoolName**</span></span> <br/> |<span data-ttu-id="4ecff-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4ecff-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4ecff-117">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="4ecff-117">Unique</span></span>  <br/> |<span data-ttu-id="4ecff-118">FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="4ecff-118">Pool FQDN.</span></span>  <br/> |
   

