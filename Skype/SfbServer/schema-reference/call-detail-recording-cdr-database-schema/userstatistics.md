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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: A tabela userstatistics é uma tabela de suporte. Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 048c26279deb6f89e69784d754567dfde84d9983
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814789"
---
# <a name="userstatistics-table"></a><span data-ttu-id="e8ee2-105">Tabela userstatistics</span><span class="sxs-lookup"><span data-stu-id="e8ee2-105">UserStatistics table</span></span>
 
<span data-ttu-id="e8ee2-106">A tabela userstatistics é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="e8ee2-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="e8ee2-107">Cada registro na tabela armazena informações sobre o uso de um usuário individual do sistema.</span><span class="sxs-lookup"><span data-stu-id="e8ee2-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="e8ee2-108">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8ee2-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e8ee2-109">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e8ee2-109">**Column**</span></span>|<span data-ttu-id="e8ee2-110">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e8ee2-110">**Data Type**</span></span>|<span data-ttu-id="e8ee2-111">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="e8ee2-111">**Key/Index**</span></span>|<span data-ttu-id="e8ee2-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="e8ee2-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e8ee2-113">**ID**</span><span class="sxs-lookup"><span data-stu-id="e8ee2-113">**UserId**</span></span> <br/> |<span data-ttu-id="e8ee2-114">int</span><span class="sxs-lookup"><span data-stu-id="e8ee2-114">int</span></span>  <br/> |<span data-ttu-id="e8ee2-115">Primária</span><span class="sxs-lookup"><span data-stu-id="e8ee2-115">Primary</span></span>  <br/> |<span data-ttu-id="e8ee2-116">Número exclusivo que identifica esse usuário.</span><span class="sxs-lookup"><span data-stu-id="e8ee2-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="e8ee2-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="e8ee2-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="e8ee2-118">datetime</span><span class="sxs-lookup"><span data-stu-id="e8ee2-118">datetime</span></span>  <br/> ||<span data-ttu-id="e8ee2-119">Última vez em que o usuário se conectou.</span><span class="sxs-lookup"><span data-stu-id="e8ee2-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="e8ee2-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="e8ee2-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="e8ee2-121">datetime</span><span class="sxs-lookup"><span data-stu-id="e8ee2-121">datetime</span></span>  <br/> ||<span data-ttu-id="e8ee2-122">Última vez em que o usuário organizou uma conferência.</span><span class="sxs-lookup"><span data-stu-id="e8ee2-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="e8ee2-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="e8ee2-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="e8ee2-124">datetime</span><span class="sxs-lookup"><span data-stu-id="e8ee2-124">datetime</span></span>  <br/> ||<span data-ttu-id="e8ee2-125">Última vez que o usuário experimentou uma falha na chamada.</span><span class="sxs-lookup"><span data-stu-id="e8ee2-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="e8ee2-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="e8ee2-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="e8ee2-127">datetime</span><span class="sxs-lookup"><span data-stu-id="e8ee2-127">datetime</span></span>  <br/> ||<span data-ttu-id="e8ee2-128">Última vez que o usuário experimentou uma falha na chamada como um organizador de conferências.</span><span class="sxs-lookup"><span data-stu-id="e8ee2-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

