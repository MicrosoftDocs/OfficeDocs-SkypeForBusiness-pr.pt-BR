---
title: Tabela ErrorCategory no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'A tabela ErrorCategory contém o nome amigável para cada classificação de diagnóstico do Skype for Business Server 2015. Por padrão, o Skype for Business Server 2015 usa as seguintes classificações:'
ms.openlocfilehash: f3ad3f86a382b900d53c5e86140a46d7f32ca1c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815249"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2040a-104">Tabela ErrorCategory no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2040a-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2040a-105">A tabela ErrorCategory contém o nome amigável para cada classificação de diagnóstico do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2040a-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="2040a-106">Por padrão, o Skype for Business Server 2015 usa as seguintes classificações:</span><span class="sxs-lookup"><span data-stu-id="2040a-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="2040a-107">0--sucesso</span><span class="sxs-lookup"><span data-stu-id="2040a-107">0 -- Success</span></span>
    
- <span data-ttu-id="2040a-108">1--falha prevista</span><span class="sxs-lookup"><span data-stu-id="2040a-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="2040a-109">2-falha inesperada</span><span class="sxs-lookup"><span data-stu-id="2040a-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="2040a-110">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2040a-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="2040a-111">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2040a-111">**Column**</span></span>|<span data-ttu-id="2040a-112">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="2040a-112">**Data Type**</span></span>|<span data-ttu-id="2040a-113">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="2040a-113">**Key/Index**</span></span>|<span data-ttu-id="2040a-114">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="2040a-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2040a-115">**CódigoDaCategoria**</span><span class="sxs-lookup"><span data-stu-id="2040a-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="2040a-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="2040a-116">tinyint</span></span>  <br/> |<span data-ttu-id="2040a-117">Primária</span><span class="sxs-lookup"><span data-stu-id="2040a-117">Primary</span></span>  <br/> |<span data-ttu-id="2040a-118">Identificador exclusivo da classificação.</span><span class="sxs-lookup"><span data-stu-id="2040a-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="2040a-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2040a-119">**Name**</span></span> <br/> |<span data-ttu-id="2040a-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2040a-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="2040a-121">Valor e nome amigável atribuídos à classificação.</span><span class="sxs-lookup"><span data-stu-id="2040a-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="2040a-122">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="2040a-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="2040a-123">0--sucesso</span><span class="sxs-lookup"><span data-stu-id="2040a-123">0 -- Success</span></span> <br/>  <span data-ttu-id="2040a-124">1--falha prevista</span><span class="sxs-lookup"><span data-stu-id="2040a-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="2040a-125">2-falha inesperada</span><span class="sxs-lookup"><span data-stu-id="2040a-125">2 - Unexpected failure</span></span> <br/> |
   

