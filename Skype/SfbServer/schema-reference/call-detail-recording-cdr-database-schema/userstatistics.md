---
title: Tabela UserStatistics
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: A tabela UserStatistics é uma tabela de suporte. Cada registro na tabela armazena informações sobre o uso do sistema por um usuário individual. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813101"
---
# <a name="userstatistics-table"></a><span data-ttu-id="cd241-105">Tabela UserStatistics</span><span class="sxs-lookup"><span data-stu-id="cd241-105">UserStatistics table</span></span>
 
<span data-ttu-id="cd241-106">A tabela UserStatistics é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="cd241-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="cd241-107">Cada registro na tabela armazena informações sobre o uso do sistema por um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="cd241-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="cd241-108">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd241-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cd241-109">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cd241-109">**Column**</span></span>|<span data-ttu-id="cd241-110">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="cd241-110">**Data Type**</span></span>|<span data-ttu-id="cd241-111">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="cd241-111">**Key/Index**</span></span>|<span data-ttu-id="cd241-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="cd241-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cd241-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="cd241-113">**UserId**</span></span> <br/> |<span data-ttu-id="cd241-114">int</span><span class="sxs-lookup"><span data-stu-id="cd241-114">int</span></span>  <br/> |<span data-ttu-id="cd241-115">Primário</span><span class="sxs-lookup"><span data-stu-id="cd241-115">Primary</span></span>  <br/> |<span data-ttu-id="cd241-116">Número único que identifica este usuário.</span><span class="sxs-lookup"><span data-stu-id="cd241-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="cd241-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="cd241-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="cd241-118">datetime</span><span class="sxs-lookup"><span data-stu-id="cd241-118">datetime</span></span>  <br/> ||<span data-ttu-id="cd241-119">Última vez que o usuário fez o login.</span><span class="sxs-lookup"><span data-stu-id="cd241-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="cd241-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="cd241-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="cd241-121">datetime</span><span class="sxs-lookup"><span data-stu-id="cd241-121">datetime</span></span>  <br/> ||<span data-ttu-id="cd241-122">Última vez que o usuário organizou uma conferência.</span><span class="sxs-lookup"><span data-stu-id="cd241-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="cd241-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="cd241-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="cd241-124">datetime</span><span class="sxs-lookup"><span data-stu-id="cd241-124">datetime</span></span>  <br/> ||<span data-ttu-id="cd241-125">Última vez que o usuário enfrentou uma falha de ligação.</span><span class="sxs-lookup"><span data-stu-id="cd241-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="cd241-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="cd241-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="cd241-127">datetime</span><span class="sxs-lookup"><span data-stu-id="cd241-127">datetime</span></span>  <br/> ||<span data-ttu-id="cd241-128">Última vez que o usuário enfrentou uma falha de ligação como um organização da conferência.</span><span class="sxs-lookup"><span data-stu-id="cd241-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

