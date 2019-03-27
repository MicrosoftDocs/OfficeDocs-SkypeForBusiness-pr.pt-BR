---
title: Tabela CallPriorities Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: A tabela CallPriorities é uma tabela estática que armazena a lista de prioridades de chamada possíveis, como "emergência", "urgente" ou "normal".
ms.openlocfilehash: faf4e7f04d7a63b096cb2369c21916e5fcb71a24
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882987"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c325f-103">Tabela CallPriorities Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c325f-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c325f-104">A tabela CallPriorities é uma tabela estática que armazena a lista de prioridades de chamada possíveis, como "emergência", "urgente" ou "normal".</span><span class="sxs-lookup"><span data-stu-id="c325f-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="c325f-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c325f-105">**Column**</span></span>|<span data-ttu-id="c325f-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c325f-106">**Data Type**</span></span>|<span data-ttu-id="c325f-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="c325f-107">**Key/Index**</span></span>|<span data-ttu-id="c325f-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="c325f-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c325f-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="c325f-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="c325f-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="c325f-110">tinyint</span></span>  <br/> |<span data-ttu-id="c325f-111">Primária</span><span class="sxs-lookup"><span data-stu-id="c325f-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="c325f-112">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="c325f-112">**Priority**</span></span> <br/> |<span data-ttu-id="c325f-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c325f-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="c325f-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="c325f-114">Allowed values:</span></span> <br/>  <span data-ttu-id="c325f-115">0 - desconhecido</span><span class="sxs-lookup"><span data-stu-id="c325f-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="c325f-116">1 - não urgente</span><span class="sxs-lookup"><span data-stu-id="c325f-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="c325f-117">2 - Normal</span><span class="sxs-lookup"><span data-stu-id="c325f-117">2 - Normal</span></span> <br/>  <span data-ttu-id="c325f-118">3 - urgente</span><span class="sxs-lookup"><span data-stu-id="c325f-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="c325f-119">4 - emergência</span><span class="sxs-lookup"><span data-stu-id="c325f-119">4 - Emergency</span></span> <br/> |
   

