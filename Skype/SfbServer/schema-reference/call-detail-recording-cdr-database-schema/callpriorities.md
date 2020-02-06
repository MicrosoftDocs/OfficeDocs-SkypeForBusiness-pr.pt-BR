---
title: Tabela CallPriorities no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: A tabela CallPriorities é uma tabela estática que armazena a lista de possíveis prioridades de chamadas, como ' emergência ', ' urgente ' ou ' normal '.
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815439"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="56c44-103">Tabela CallPriorities no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="56c44-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="56c44-104">A tabela CallPriorities é uma tabela estática que armazena a lista de possíveis prioridades de chamadas, como ' emergência ', ' urgente ' ou ' normal '.</span><span class="sxs-lookup"><span data-stu-id="56c44-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="56c44-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="56c44-105">**Column**</span></span>|<span data-ttu-id="56c44-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="56c44-106">**Data Type**</span></span>|<span data-ttu-id="56c44-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="56c44-107">**Key/Index**</span></span>|<span data-ttu-id="56c44-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="56c44-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="56c44-109">**Priorityid**</span><span class="sxs-lookup"><span data-stu-id="56c44-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="56c44-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="56c44-110">tinyint</span></span>  <br/> |<span data-ttu-id="56c44-111">Primária</span><span class="sxs-lookup"><span data-stu-id="56c44-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="56c44-112">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="56c44-112">**Priority**</span></span> <br/> |<span data-ttu-id="56c44-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="56c44-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="56c44-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="56c44-114">Allowed values:</span></span> <br/>  <span data-ttu-id="56c44-115">0-desconhecido</span><span class="sxs-lookup"><span data-stu-id="56c44-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="56c44-116">1-não urgente</span><span class="sxs-lookup"><span data-stu-id="56c44-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="56c44-117">2-normal</span><span class="sxs-lookup"><span data-stu-id="56c44-117">2 - Normal</span></span> <br/>  <span data-ttu-id="56c44-118">3-urgente</span><span class="sxs-lookup"><span data-stu-id="56c44-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="56c44-119">4-emergência</span><span class="sxs-lookup"><span data-stu-id="56c44-119">4 - Emergency</span></span> <br/> |
   

