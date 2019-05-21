---
title: Tabela userstatistics
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: A tabela userstatistics é uma tabela de suporte. Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295689"
---
# <a name="userstatistics-table"></a><span data-ttu-id="6679e-105">Tabela userstatistics</span><span class="sxs-lookup"><span data-stu-id="6679e-105">UserStatistics table</span></span>
 
<span data-ttu-id="6679e-106">A tabela userstatistics é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="6679e-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="6679e-107">Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema.</span><span class="sxs-lookup"><span data-stu-id="6679e-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="6679e-108">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6679e-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="6679e-109">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6679e-109">**Column**</span></span>|<span data-ttu-id="6679e-110">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="6679e-110">**Data Type**</span></span>|<span data-ttu-id="6679e-111">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="6679e-111">**Key/Index**</span></span>|<span data-ttu-id="6679e-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="6679e-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6679e-113">**ID**</span><span class="sxs-lookup"><span data-stu-id="6679e-113">**UserId**</span></span> <br/> |<span data-ttu-id="6679e-114">int</span><span class="sxs-lookup"><span data-stu-id="6679e-114">int</span></span>  <br/> |<span data-ttu-id="6679e-115">Primária</span><span class="sxs-lookup"><span data-stu-id="6679e-115">Primary</span></span>  <br/> |<span data-ttu-id="6679e-116">Número exclusivo que identifica esse usuário.</span><span class="sxs-lookup"><span data-stu-id="6679e-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="6679e-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="6679e-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="6679e-118">datetime</span><span class="sxs-lookup"><span data-stu-id="6679e-118">datetime</span></span>  <br/> ||<span data-ttu-id="6679e-119">Última vez em que o usuário se conectou.</span><span class="sxs-lookup"><span data-stu-id="6679e-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="6679e-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="6679e-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="6679e-121">datetime</span><span class="sxs-lookup"><span data-stu-id="6679e-121">datetime</span></span>  <br/> ||<span data-ttu-id="6679e-122">Última vez em que o usuário organizou uma conferência.</span><span class="sxs-lookup"><span data-stu-id="6679e-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="6679e-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="6679e-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="6679e-124">datetime</span><span class="sxs-lookup"><span data-stu-id="6679e-124">datetime</span></span>  <br/> ||<span data-ttu-id="6679e-125">Última vez que o usuário experimentou uma falha na chamada.</span><span class="sxs-lookup"><span data-stu-id="6679e-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="6679e-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="6679e-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="6679e-127">datetime</span><span class="sxs-lookup"><span data-stu-id="6679e-127">datetime</span></span>  <br/> ||<span data-ttu-id="6679e-128">Última vez que o usuário experimentou uma falha na chamada como um organizador de conferências.</span><span class="sxs-lookup"><span data-stu-id="6679e-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

