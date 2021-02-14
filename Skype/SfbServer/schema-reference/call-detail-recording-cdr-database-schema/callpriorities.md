---
title: Tabela CallPriorities no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: A tabela CallPriorities é uma tabela estática que armazena a lista de prioridades de chamada possíveis, como "emergência", "urgente" ou "normal".
ms.openlocfilehash: 54fdd70dcd939cfeb227862d6152577c4c91d3b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813431"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="10f14-103">Tabela CallPriorities no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="10f14-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="10f14-104">A tabela CallPriorities é uma tabela estática que armazena a lista de prioridades de chamada possíveis, como "emergência", "urgente" ou "normal".</span><span class="sxs-lookup"><span data-stu-id="10f14-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="10f14-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="10f14-105">**Column**</span></span>|<span data-ttu-id="10f14-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="10f14-106">**Data Type**</span></span>|<span data-ttu-id="10f14-107">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="10f14-107">**Key/Index**</span></span>|<span data-ttu-id="10f14-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="10f14-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="10f14-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="10f14-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="10f14-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="10f14-110">tinyint</span></span>  <br/> |<span data-ttu-id="10f14-111">Primário</span><span class="sxs-lookup"><span data-stu-id="10f14-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="10f14-112">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="10f14-112">**Priority**</span></span> <br/> |<span data-ttu-id="10f14-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="10f14-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="10f14-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="10f14-114">Allowed values:</span></span> <br/>  <span data-ttu-id="10f14-115">0 - Desconhecido</span><span class="sxs-lookup"><span data-stu-id="10f14-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="10f14-116">1 - Não Urgente</span><span class="sxs-lookup"><span data-stu-id="10f14-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="10f14-117">2 - Normal</span><span class="sxs-lookup"><span data-stu-id="10f14-117">2 - Normal</span></span> <br/>  <span data-ttu-id="10f14-118">3 - Urgente</span><span class="sxs-lookup"><span data-stu-id="10f14-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="10f14-119">4 - Emergência</span><span class="sxs-lookup"><span data-stu-id="10f14-119">4 - Emergency</span></span> <br/> |
   

