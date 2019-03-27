---
title: Tabela UserStatistics
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: A tabela UserStatistics é uma tabela de suporte. Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 45f34a1e8905d19b5ce48d94824591f25ec1ef28
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883592"
---
# <a name="userstatistics-table"></a><span data-ttu-id="5c08e-105">Tabela UserStatistics</span><span class="sxs-lookup"><span data-stu-id="5c08e-105">UserStatistics table</span></span>
 
<span data-ttu-id="5c08e-106">A tabela UserStatistics é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="5c08e-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="5c08e-107">Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema.</span><span class="sxs-lookup"><span data-stu-id="5c08e-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="5c08e-108">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5c08e-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5c08e-109">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="5c08e-109">**Column**</span></span>|<span data-ttu-id="5c08e-110">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5c08e-110">**Data Type**</span></span>|<span data-ttu-id="5c08e-111">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="5c08e-111">**Key/Index**</span></span>|<span data-ttu-id="5c08e-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="5c08e-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5c08e-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="5c08e-113">**UserId**</span></span> <br/> |<span data-ttu-id="5c08e-114">int</span><span class="sxs-lookup"><span data-stu-id="5c08e-114">int</span></span>  <br/> |<span data-ttu-id="5c08e-115">Primária</span><span class="sxs-lookup"><span data-stu-id="5c08e-115">Primary</span></span>  <br/> |<span data-ttu-id="5c08e-116">Número exclusivo que identifica este usuário.</span><span class="sxs-lookup"><span data-stu-id="5c08e-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="5c08e-117">**Hora do último login**</span><span class="sxs-lookup"><span data-stu-id="5c08e-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="5c08e-118">datetime</span><span class="sxs-lookup"><span data-stu-id="5c08e-118">datetime</span></span>  <br/> ||<span data-ttu-id="5c08e-119">Última vez em que o usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="5c08e-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="5c08e-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="5c08e-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="5c08e-121">datetime</span><span class="sxs-lookup"><span data-stu-id="5c08e-121">datetime</span></span>  <br/> ||<span data-ttu-id="5c08e-122">Última vez que o usuário organizou uma conferência.</span><span class="sxs-lookup"><span data-stu-id="5c08e-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="5c08e-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="5c08e-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="5c08e-124">datetime</span><span class="sxs-lookup"><span data-stu-id="5c08e-124">datetime</span></span>  <br/> ||<span data-ttu-id="5c08e-125">Última vez em que o usuário enfrentou uma falha de ligação.</span><span class="sxs-lookup"><span data-stu-id="5c08e-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="5c08e-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="5c08e-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="5c08e-127">datetime</span><span class="sxs-lookup"><span data-stu-id="5c08e-127">datetime</span></span>  <br/> ||<span data-ttu-id="5c08e-128">Última vez em que o usuário enfrentou uma falha de ligação como um organizador da conferência.</span><span class="sxs-lookup"><span data-stu-id="5c08e-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

