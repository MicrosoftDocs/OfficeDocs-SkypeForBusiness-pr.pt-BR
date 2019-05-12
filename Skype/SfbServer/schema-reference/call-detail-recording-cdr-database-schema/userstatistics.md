---
title: Tabela UserStatistics
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: A tabela UserStatistics é uma tabela de suporte. Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: c2e0acffa7b75b3c54781e3e4e9a8b033be5e440
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929977"
---
# <a name="userstatistics-table"></a><span data-ttu-id="fbc3a-105">Tabela UserStatistics</span><span class="sxs-lookup"><span data-stu-id="fbc3a-105">UserStatistics table</span></span>
 
<span data-ttu-id="fbc3a-106">A tabela UserStatistics é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="fbc3a-107">Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="fbc3a-108">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="fbc3a-109">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="fbc3a-109">**Column**</span></span>|<span data-ttu-id="fbc3a-110">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="fbc3a-110">**Data Type**</span></span>|<span data-ttu-id="fbc3a-111">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="fbc3a-111">**Key/Index**</span></span>|<span data-ttu-id="fbc3a-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="fbc3a-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fbc3a-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="fbc3a-113">**UserId**</span></span> <br/> |<span data-ttu-id="fbc3a-114">int</span><span class="sxs-lookup"><span data-stu-id="fbc3a-114">int</span></span>  <br/> |<span data-ttu-id="fbc3a-115">Primária</span><span class="sxs-lookup"><span data-stu-id="fbc3a-115">Primary</span></span>  <br/> |<span data-ttu-id="fbc3a-116">Número exclusivo que identifica este usuário.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="fbc3a-117">**Hora do último login**</span><span class="sxs-lookup"><span data-stu-id="fbc3a-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="fbc3a-118">datetime</span><span class="sxs-lookup"><span data-stu-id="fbc3a-118">datetime</span></span>  <br/> ||<span data-ttu-id="fbc3a-119">Última vez em que o usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="fbc3a-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="fbc3a-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="fbc3a-121">datetime</span><span class="sxs-lookup"><span data-stu-id="fbc3a-121">datetime</span></span>  <br/> ||<span data-ttu-id="fbc3a-122">Última vez que o usuário organizou uma conferência.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="fbc3a-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="fbc3a-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="fbc3a-124">datetime</span><span class="sxs-lookup"><span data-stu-id="fbc3a-124">datetime</span></span>  <br/> ||<span data-ttu-id="fbc3a-125">Última vez em que o usuário enfrentou uma falha de ligação.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="fbc3a-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="fbc3a-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="fbc3a-127">datetime</span><span class="sxs-lookup"><span data-stu-id="fbc3a-127">datetime</span></span>  <br/> ||<span data-ttu-id="fbc3a-128">Última vez em que o usuário enfrentou uma falha de ligação como um organizador da conferência.</span><span class="sxs-lookup"><span data-stu-id="fbc3a-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

