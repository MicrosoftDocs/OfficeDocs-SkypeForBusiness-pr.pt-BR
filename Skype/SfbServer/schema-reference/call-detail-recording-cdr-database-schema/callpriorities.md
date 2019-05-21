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
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: A tabela CallPriorities é uma tabela estática que armazena a lista de possíveis prioridades de chamadas, como ' emergência ', ' urgente ' ou ' normal '.
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296564"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0e69a-103">Tabela CallPriorities no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0e69a-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0e69a-104">A tabela CallPriorities é uma tabela estática que armazena a lista de possíveis prioridades de chamadas, como ' emergência ', ' urgente ' ou ' normal '.</span><span class="sxs-lookup"><span data-stu-id="0e69a-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="0e69a-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="0e69a-105">**Column**</span></span>|<span data-ttu-id="0e69a-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="0e69a-106">**Data Type**</span></span>|<span data-ttu-id="0e69a-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="0e69a-107">**Key/Index**</span></span>|<span data-ttu-id="0e69a-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="0e69a-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0e69a-109">**Priorityid**</span><span class="sxs-lookup"><span data-stu-id="0e69a-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="0e69a-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="0e69a-110">tinyint</span></span>  <br/> |<span data-ttu-id="0e69a-111">Primária</span><span class="sxs-lookup"><span data-stu-id="0e69a-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="0e69a-112">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="0e69a-112">**Priority**</span></span> <br/> |<span data-ttu-id="0e69a-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0e69a-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="0e69a-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="0e69a-114">Allowed values:</span></span> <br/>  <span data-ttu-id="0e69a-115">0-desconhecido</span><span class="sxs-lookup"><span data-stu-id="0e69a-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="0e69a-116">1-não urgente</span><span class="sxs-lookup"><span data-stu-id="0e69a-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="0e69a-117">2-normal</span><span class="sxs-lookup"><span data-stu-id="0e69a-117">2 - Normal</span></span> <br/>  <span data-ttu-id="0e69a-118">3-urgente</span><span class="sxs-lookup"><span data-stu-id="0e69a-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="0e69a-119">4-emergência</span><span class="sxs-lookup"><span data-stu-id="0e69a-119">4 - Emergency</span></span> <br/> |
   

