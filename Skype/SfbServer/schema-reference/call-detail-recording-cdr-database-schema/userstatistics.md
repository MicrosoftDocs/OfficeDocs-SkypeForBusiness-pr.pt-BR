---
title: Tabela UserStatistics
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
ms.openlocfilehash: c4a7952eada01033836811555d2e448d13133a27
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="userstatistics-table"></a><span data-ttu-id="6dc8a-105">Tabela UserStatistics</span><span class="sxs-lookup"><span data-stu-id="6dc8a-105">UserStatistics table</span></span>
 
<span data-ttu-id="6dc8a-106">A tabela UserStatistics é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="6dc8a-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="6dc8a-107">Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema.</span><span class="sxs-lookup"><span data-stu-id="6dc8a-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="6dc8a-108">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dc8a-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="6dc8a-109">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6dc8a-109">**Column**</span></span>|<span data-ttu-id="6dc8a-110">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="6dc8a-110">**Data Type**</span></span>|<span data-ttu-id="6dc8a-111">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="6dc8a-111">**Key/Index**</span></span>|<span data-ttu-id="6dc8a-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="6dc8a-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6dc8a-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="6dc8a-113">**UserId**</span></span> <br/> |<span data-ttu-id="6dc8a-114">int</span><span class="sxs-lookup"><span data-stu-id="6dc8a-114">int</span></span>  <br/> |<span data-ttu-id="6dc8a-115">Primária</span><span class="sxs-lookup"><span data-stu-id="6dc8a-115">Primary</span></span>  <br/> |<span data-ttu-id="6dc8a-116">Número exclusivo que identifica este usuário.</span><span class="sxs-lookup"><span data-stu-id="6dc8a-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="6dc8a-117">**Hora do último login**</span><span class="sxs-lookup"><span data-stu-id="6dc8a-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="6dc8a-118">datetime</span><span class="sxs-lookup"><span data-stu-id="6dc8a-118">datetime</span></span>  <br/> ||<span data-ttu-id="6dc8a-119">Última vez em que o usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="6dc8a-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="6dc8a-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="6dc8a-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="6dc8a-121">datetime</span><span class="sxs-lookup"><span data-stu-id="6dc8a-121">datetime</span></span>  <br/> ||<span data-ttu-id="6dc8a-122">Última vez que o usuário organizou uma conferência.</span><span class="sxs-lookup"><span data-stu-id="6dc8a-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="6dc8a-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="6dc8a-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="6dc8a-124">datetime</span><span class="sxs-lookup"><span data-stu-id="6dc8a-124">datetime</span></span>  <br/> ||<span data-ttu-id="6dc8a-125">Última vez em que o usuário enfrentou uma falha de ligação.</span><span class="sxs-lookup"><span data-stu-id="6dc8a-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="6dc8a-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="6dc8a-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="6dc8a-127">datetime</span><span class="sxs-lookup"><span data-stu-id="6dc8a-127">datetime</span></span>  <br/> ||<span data-ttu-id="6dc8a-128">Última vez em que o usuário enfrentou uma falha de ligação como um organizador da conferência.</span><span class="sxs-lookup"><span data-stu-id="6dc8a-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

