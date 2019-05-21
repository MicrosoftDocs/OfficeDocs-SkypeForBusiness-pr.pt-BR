---
title: Tabela User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: A tabela do usuário é uma tabela de suporte que armazena uma lista de vários usuários que participaram de sessões registradas no banco de dados. Cada registro na tabela representa um usuário.
ms.openlocfilehash: a9f72793d3b287406b1b3b7e1ad360e7f5abc598
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294611"
---
# <a name="user-table"></a><span data-ttu-id="aadc8-104">Tabela User</span><span class="sxs-lookup"><span data-stu-id="aadc8-104">User table</span></span>
 
<span data-ttu-id="aadc8-105">A tabela do usuário é uma tabela de suporte que armazena uma lista de vários usuários que participaram de sessões registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aadc8-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="aadc8-106">Cada registro na tabela representa um usuário.</span><span class="sxs-lookup"><span data-stu-id="aadc8-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="aadc8-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="aadc8-107">**Column**</span></span>|<span data-ttu-id="aadc8-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="aadc8-108">**Data Type**</span></span>|<span data-ttu-id="aadc8-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="aadc8-109">**Key/Index**</span></span>|<span data-ttu-id="aadc8-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="aadc8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aadc8-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="aadc8-111">**UserKey**</span></span> <br/> |<span data-ttu-id="aadc8-112">int</span><span class="sxs-lookup"><span data-stu-id="aadc8-112">int</span></span>  <br/> |<span data-ttu-id="aadc8-113">Primária</span><span class="sxs-lookup"><span data-stu-id="aadc8-113">Primary</span></span>  <br/> |<span data-ttu-id="aadc8-114">Número exclusivo que identifica esse usuário.</span><span class="sxs-lookup"><span data-stu-id="aadc8-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="aadc8-115">**SOLICITAÇÃO**</span><span class="sxs-lookup"><span data-stu-id="aadc8-115">**URI**</span></span> <br/> |<span data-ttu-id="aadc8-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="aadc8-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="aadc8-117">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="aadc8-117">Unique</span></span>  <br/> |<span data-ttu-id="aadc8-118">Cadeia de caracteres de URI.</span><span class="sxs-lookup"><span data-stu-id="aadc8-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="aadc8-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="aadc8-119">**URIType**</span></span> <br/> |<span data-ttu-id="aadc8-120">int</span><span class="sxs-lookup"><span data-stu-id="aadc8-120">int</span></span>  <br/> ||<span data-ttu-id="aadc8-121">1 é um tipo de URI desconhecido.</span><span class="sxs-lookup"><span data-stu-id="aadc8-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="aadc8-122">2 é o URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="aadc8-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="aadc8-123">4 é o URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="aadc8-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="aadc8-124">8 é o URI do telefone.</span><span class="sxs-lookup"><span data-stu-id="aadc8-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="aadc8-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="aadc8-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="aadc8-126">int</span><span class="sxs-lookup"><span data-stu-id="aadc8-126">int</span></span>  <br/> |<span data-ttu-id="aadc8-127">Exterior</span><span class="sxs-lookup"><span data-stu-id="aadc8-127">Foreign</span></span>  <br/> |<span data-ttu-id="aadc8-128">Locatário do usuário, referenciado da tabela de locatários.</span><span class="sxs-lookup"><span data-stu-id="aadc8-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="aadc8-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="aadc8-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="aadc8-130">datetime</span><span class="sxs-lookup"><span data-stu-id="aadc8-130">datetime</span></span>  <br/> ||<span data-ttu-id="aadc8-131">Carimbo de data/hora mais recente quando o usuário tiver uma chamada de áudio ruim.</span><span class="sxs-lookup"><span data-stu-id="aadc8-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="aadc8-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="aadc8-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="aadc8-133">datetime</span><span class="sxs-lookup"><span data-stu-id="aadc8-133">datetime</span></span>  <br/> ||<span data-ttu-id="aadc8-134">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="aadc8-134">For internal use only.</span></span>  <br/> |
   

