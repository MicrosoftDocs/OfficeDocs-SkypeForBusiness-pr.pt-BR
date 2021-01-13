---
title: Tabela User
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: A tabela de Usuário é uma tabela de suporte que armazena uma lista de vários usuários que participaram das sessões registradas no banco de dados. Cada registro da tabela representa um usuário.
ms.openlocfilehash: 5c84f0b947199fa497964cb1689dccc571a98d14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800071"
---
# <a name="user-table"></a><span data-ttu-id="dd624-104">Tabela User</span><span class="sxs-lookup"><span data-stu-id="dd624-104">User table</span></span>
 
<span data-ttu-id="dd624-p102">A tabela de Usuário é uma tabela de suporte que armazena uma lista de vários usuários que participaram das sessões registradas no banco de dados. Cada registro da tabela representa um usuário.</span><span class="sxs-lookup"><span data-stu-id="dd624-p102">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="dd624-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="dd624-107">**Column**</span></span>|<span data-ttu-id="dd624-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="dd624-108">**Data Type**</span></span>|<span data-ttu-id="dd624-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="dd624-109">**Key/Index**</span></span>|<span data-ttu-id="dd624-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="dd624-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dd624-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="dd624-111">**UserKey**</span></span> <br/> |<span data-ttu-id="dd624-112">int</span><span class="sxs-lookup"><span data-stu-id="dd624-112">int</span></span>  <br/> |<span data-ttu-id="dd624-113">Primário</span><span class="sxs-lookup"><span data-stu-id="dd624-113">Primary</span></span>  <br/> |<span data-ttu-id="dd624-114">Número exclusivo identificando este usuário.</span><span class="sxs-lookup"><span data-stu-id="dd624-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="dd624-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="dd624-115">**URI**</span></span> <br/> |<span data-ttu-id="dd624-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="dd624-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="dd624-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="dd624-117">Unique</span></span>  <br/> |<span data-ttu-id="dd624-118">Cadeia de caracteres URI.</span><span class="sxs-lookup"><span data-stu-id="dd624-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="dd624-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="dd624-119">**URIType**</span></span> <br/> |<span data-ttu-id="dd624-120">int</span><span class="sxs-lookup"><span data-stu-id="dd624-120">int</span></span>  <br/> ||<span data-ttu-id="dd624-121">1 é o tipo de URI desconhecido.</span><span class="sxs-lookup"><span data-stu-id="dd624-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="dd624-122">2 é o URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="dd624-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="dd624-123">4 é o URI de conferência.</span><span class="sxs-lookup"><span data-stu-id="dd624-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="dd624-124">8 é o URI do telefone.</span><span class="sxs-lookup"><span data-stu-id="dd624-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="dd624-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="dd624-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="dd624-126">int</span><span class="sxs-lookup"><span data-stu-id="dd624-126">int</span></span>  <br/> |<span data-ttu-id="dd624-127">Externo</span><span class="sxs-lookup"><span data-stu-id="dd624-127">Foreign</span></span>  <br/> |<span data-ttu-id="dd624-128">Locatário do usuário, referenciado da tabela do locatário.</span><span class="sxs-lookup"><span data-stu-id="dd624-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="dd624-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="dd624-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="dd624-130">datetime</span><span class="sxs-lookup"><span data-stu-id="dd624-130">datetime</span></span>  <br/> ||<span data-ttu-id="dd624-131">Carimbo de data e hora da última vez em que o usuário teve uma chamada de áudio ruim.</span><span class="sxs-lookup"><span data-stu-id="dd624-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="dd624-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="dd624-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="dd624-133">datetime</span><span class="sxs-lookup"><span data-stu-id="dd624-133">datetime</span></span>  <br/> ||<span data-ttu-id="dd624-134">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="dd624-134">For internal use only.</span></span>  <br/> |
   

