---
title: Tabela ErrorCategory no Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'A tabela ErrorCategory contém o nome amigável para cada Skype para a classificação de diagnóstico Business Server 2015. Por padrão, o Skype para Business Server 2015 usa as seguintes classificações:'
ms.openlocfilehash: 70322d30b516d003fcac015a4eda7382a13cd2be
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213113"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8131e-104">Tabela ErrorCategory no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8131e-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8131e-105">A tabela ErrorCategory contém o nome amigável para cada Skype para a classificação de diagnóstico Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8131e-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="8131e-106">Por padrão, o Skype para Business Server 2015 usa as seguintes classificações:</span><span class="sxs-lookup"><span data-stu-id="8131e-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="8131e-107">0--êxito</span><span class="sxs-lookup"><span data-stu-id="8131e-107">0 -- Success</span></span>
    
- <span data-ttu-id="8131e-108">1-- falha esperada</span><span class="sxs-lookup"><span data-stu-id="8131e-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="8131e-109">2 - Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="8131e-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="8131e-110">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8131e-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="8131e-111">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="8131e-111">**Column**</span></span>|<span data-ttu-id="8131e-112">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="8131e-112">**Data Type**</span></span>|<span data-ttu-id="8131e-113">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="8131e-113">**Key/Index**</span></span>|<span data-ttu-id="8131e-114">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="8131e-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8131e-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="8131e-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="8131e-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="8131e-116">tinyint</span></span>  <br/> |<span data-ttu-id="8131e-117">Primária</span><span class="sxs-lookup"><span data-stu-id="8131e-117">Primary</span></span>  <br/> |<span data-ttu-id="8131e-118">Identificador exclusivo para a classificação.</span><span class="sxs-lookup"><span data-stu-id="8131e-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="8131e-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="8131e-119">**Name**</span></span> <br/> |<span data-ttu-id="8131e-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8131e-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="8131e-121">Valor e o nome amigável atribuído para a classificação.</span><span class="sxs-lookup"><span data-stu-id="8131e-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="8131e-122">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="8131e-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="8131e-123">0--êxito</span><span class="sxs-lookup"><span data-stu-id="8131e-123">0 -- Success</span></span> <br/>  <span data-ttu-id="8131e-124">1-- falha esperada</span><span class="sxs-lookup"><span data-stu-id="8131e-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="8131e-125">2 - Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="8131e-125">2 - Unexpected failure</span></span> <br/> |
   

