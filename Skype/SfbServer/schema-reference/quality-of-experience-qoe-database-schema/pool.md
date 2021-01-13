---
title: Tabela Pool
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
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: A tabela Pool é uma tabela de suporte que armazena informações sobre os diversos pools de Front-Ends. Cada registro da tabela representa um pool.
ms.openlocfilehash: e90b9b2a34a184e1d8cdb23dc3d33b1c41367584
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815811"
---
# <a name="pool-table"></a><span data-ttu-id="50cb6-104">Tabela Pool</span><span class="sxs-lookup"><span data-stu-id="50cb6-104">Pool table</span></span>
 
<span data-ttu-id="50cb6-p102">A tabela Pool é uma tabela de suporte que armazena informações sobre os diversos pools de Front-Ends. Cada registro da tabela representa um pool.</span><span class="sxs-lookup"><span data-stu-id="50cb6-p102">The Pool table is a supporting table that stores information about the various Front End pools. Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="50cb6-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="50cb6-107">**Column**</span></span>|<span data-ttu-id="50cb6-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="50cb6-108">**Data Type**</span></span>|<span data-ttu-id="50cb6-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="50cb6-109">**Key/Index**</span></span>|<span data-ttu-id="50cb6-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="50cb6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="50cb6-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="50cb6-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="50cb6-112">int</span><span class="sxs-lookup"><span data-stu-id="50cb6-112">int</span></span>  <br/> |<span data-ttu-id="50cb6-113">Primário</span><span class="sxs-lookup"><span data-stu-id="50cb6-113">Primary</span></span>  <br/> |<span data-ttu-id="50cb6-114">Número único que identifica este pool.</span><span class="sxs-lookup"><span data-stu-id="50cb6-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="50cb6-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="50cb6-115">**PoolName**</span></span> <br/> |<span data-ttu-id="50cb6-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="50cb6-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="50cb6-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="50cb6-117">Unique</span></span>  <br/> |<span data-ttu-id="50cb6-118">FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="50cb6-118">Pool FQDN.</span></span>  <br/> |
   

