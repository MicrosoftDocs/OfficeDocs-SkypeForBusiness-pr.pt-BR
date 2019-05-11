---
title: Tabela Users
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: A tabela de usuários é uma tabela de suporte. Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que têm registros no banco de dados.
ms.openlocfilehash: fbe3ff7d2570f78cdf3b3418629fb9fd6209d944
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929984"
---
# <a name="users-table"></a><span data-ttu-id="4cf3d-104">Tabela Users</span><span class="sxs-lookup"><span data-stu-id="4cf3d-104">Users table</span></span>
 
<span data-ttu-id="4cf3d-105">A tabela de usuários é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="4cf3d-105">The Users table is a supporting table.</span></span> <span data-ttu-id="4cf3d-106">Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4cf3d-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="4cf3d-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4cf3d-107">**Column**</span></span>|<span data-ttu-id="4cf3d-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4cf3d-108">**Data Type**</span></span>|<span data-ttu-id="4cf3d-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="4cf3d-109">**Key/Index**</span></span>|<span data-ttu-id="4cf3d-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="4cf3d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4cf3d-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="4cf3d-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="4cf3d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4cf3d-112">datetime</span></span>  <br/> ||<span data-ttu-id="4cf3d-113">Carimbo de hora para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4cf3d-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="4cf3d-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="4cf3d-114">**UserId**</span></span> <br/> |<span data-ttu-id="4cf3d-115">int</span><span class="sxs-lookup"><span data-stu-id="4cf3d-115">int</span></span>  <br/> |<span data-ttu-id="4cf3d-116">Primária</span><span class="sxs-lookup"><span data-stu-id="4cf3d-116">Primary</span></span>  <br/> |<span data-ttu-id="4cf3d-117">Número exclusivo que identifica este usuário.</span><span class="sxs-lookup"><span data-stu-id="4cf3d-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="4cf3d-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="4cf3d-118">**UserUri**</span></span> <br/> |<span data-ttu-id="4cf3d-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="4cf3d-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="4cf3d-120">URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="4cf3d-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="4cf3d-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="4cf3d-121">**TenantId**</span></span> <br/> |<span data-ttu-id="4cf3d-122">int</span><span class="sxs-lookup"><span data-stu-id="4cf3d-122">int</span></span>  <br/> |<span data-ttu-id="4cf3d-123">Externa</span><span class="sxs-lookup"><span data-stu-id="4cf3d-123">Foreign</span></span>  <br/> |<span data-ttu-id="4cf3d-124">ID do locatário. do usuário</span><span class="sxs-lookup"><span data-stu-id="4cf3d-124">This user's Tenant ID.</span></span> <span data-ttu-id="4cf3d-125">Consulte a [tabela de inquilinos](tenants.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4cf3d-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4cf3d-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="4cf3d-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="4cf3d-127">int</span><span class="sxs-lookup"><span data-stu-id="4cf3d-127">int</span></span>  <br/> |<span data-ttu-id="4cf3d-128">Externa</span><span class="sxs-lookup"><span data-stu-id="4cf3d-128">Foreign</span></span>  <br/> |<span data-ttu-id="4cf3d-129">Tipo de URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="4cf3d-129">This user's URI type.</span></span> <span data-ttu-id="4cf3d-130">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4cf3d-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

