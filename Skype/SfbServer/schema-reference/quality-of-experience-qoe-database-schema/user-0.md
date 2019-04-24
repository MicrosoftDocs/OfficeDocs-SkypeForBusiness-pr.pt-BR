---
title: Tabela User
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: A tabela de usuário é uma tabela de suporte que armazena uma lista dos diversos usuários que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa um usuário.
ms.openlocfilehash: fcdc8682b86432613af79d5e4d2abbdb248fef0f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212078"
---
# <a name="user-table"></a><span data-ttu-id="b39f2-104">Tabela User</span><span class="sxs-lookup"><span data-stu-id="b39f2-104">User table</span></span>
 
<span data-ttu-id="b39f2-105">A tabela de usuário é uma tabela de suporte que armazena uma lista dos diversos usuários que tenham participado em sessões gravadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b39f2-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="b39f2-106">Cada registro na tabela representa um usuário.</span><span class="sxs-lookup"><span data-stu-id="b39f2-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="b39f2-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b39f2-107">**Column**</span></span>|<span data-ttu-id="b39f2-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b39f2-108">**Data Type**</span></span>|<span data-ttu-id="b39f2-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="b39f2-109">**Key/Index**</span></span>|<span data-ttu-id="b39f2-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="b39f2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b39f2-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="b39f2-111">**UserKey**</span></span> <br/> |<span data-ttu-id="b39f2-112">int</span><span class="sxs-lookup"><span data-stu-id="b39f2-112">int</span></span>  <br/> |<span data-ttu-id="b39f2-113">Primária</span><span class="sxs-lookup"><span data-stu-id="b39f2-113">Primary</span></span>  <br/> |<span data-ttu-id="b39f2-114">Número exclusivo que identifica este usuário.</span><span class="sxs-lookup"><span data-stu-id="b39f2-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="b39f2-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="b39f2-115">**URI**</span></span> <br/> |<span data-ttu-id="b39f2-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="b39f2-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="b39f2-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="b39f2-117">Unique</span></span>  <br/> |<span data-ttu-id="b39f2-118">Cadeia de caracteres do URI.</span><span class="sxs-lookup"><span data-stu-id="b39f2-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="b39f2-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="b39f2-119">**URIType**</span></span> <br/> |<span data-ttu-id="b39f2-120">int</span><span class="sxs-lookup"><span data-stu-id="b39f2-120">int</span></span>  <br/> ||<span data-ttu-id="b39f2-121">1 é o tipo URI desconhecido.</span><span class="sxs-lookup"><span data-stu-id="b39f2-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="b39f2-122">2 é o URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="b39f2-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="b39f2-123">4 é o URI de conferência.</span><span class="sxs-lookup"><span data-stu-id="b39f2-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="b39f2-124">8 é o URI do telefone.</span><span class="sxs-lookup"><span data-stu-id="b39f2-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="b39f2-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="b39f2-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="b39f2-126">int</span><span class="sxs-lookup"><span data-stu-id="b39f2-126">int</span></span>  <br/> |<span data-ttu-id="b39f2-127">Externa</span><span class="sxs-lookup"><span data-stu-id="b39f2-127">Foreign</span></span>  <br/> |<span data-ttu-id="b39f2-128">Locatário do usuário, referenciado da tabela do locatário.</span><span class="sxs-lookup"><span data-stu-id="b39f2-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="b39f2-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="b39f2-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="b39f2-130">datetime</span><span class="sxs-lookup"><span data-stu-id="b39f2-130">datetime</span></span>  <br/> ||<span data-ttu-id="b39f2-131">Carimbo de hora mais recente que o usuário teve uma chamada de áudio ruim.</span><span class="sxs-lookup"><span data-stu-id="b39f2-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="b39f2-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="b39f2-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="b39f2-133">datetime</span><span class="sxs-lookup"><span data-stu-id="b39f2-133">datetime</span></span>  <br/> ||<span data-ttu-id="b39f2-134">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="b39f2-134">For internal use only.</span></span>  <br/> |
   

