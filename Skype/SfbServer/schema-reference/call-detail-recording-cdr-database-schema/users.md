---
title: Tabela Users
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: A tabela usuários é uma tabela de suporte. Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que têm registros no banco de dados.
ms.openlocfilehash: 0dcc2fda73305be2bbe6a7a5c546dac0b05f8273
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295696"
---
# <a name="users-table"></a><span data-ttu-id="2acb6-104">Tabela Users</span><span class="sxs-lookup"><span data-stu-id="2acb6-104">Users table</span></span>
 
<span data-ttu-id="2acb6-105">A tabela usuários é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="2acb6-105">The Users table is a supporting table.</span></span> <span data-ttu-id="2acb6-106">Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2acb6-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="2acb6-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2acb6-107">**Column**</span></span>|<span data-ttu-id="2acb6-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="2acb6-108">**Data Type**</span></span>|<span data-ttu-id="2acb6-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="2acb6-109">**Key/Index**</span></span>|<span data-ttu-id="2acb6-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="2acb6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2acb6-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="2acb6-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="2acb6-112">datetime</span><span class="sxs-lookup"><span data-stu-id="2acb6-112">datetime</span></span>  <br/> ||<span data-ttu-id="2acb6-113">Carimbo de data/hora para uso interno.</span><span class="sxs-lookup"><span data-stu-id="2acb6-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="2acb6-114">**ID**</span><span class="sxs-lookup"><span data-stu-id="2acb6-114">**UserId**</span></span> <br/> |<span data-ttu-id="2acb6-115">int</span><span class="sxs-lookup"><span data-stu-id="2acb6-115">int</span></span>  <br/> |<span data-ttu-id="2acb6-116">Primária</span><span class="sxs-lookup"><span data-stu-id="2acb6-116">Primary</span></span>  <br/> |<span data-ttu-id="2acb6-117">Número exclusivo que identifica esse usuário.</span><span class="sxs-lookup"><span data-stu-id="2acb6-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="2acb6-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="2acb6-118">**UserUri**</span></span> <br/> |<span data-ttu-id="2acb6-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2acb6-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="2acb6-120">URI de usuário.</span><span class="sxs-lookup"><span data-stu-id="2acb6-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="2acb6-121">**Tenantid**</span><span class="sxs-lookup"><span data-stu-id="2acb6-121">**TenantId**</span></span> <br/> |<span data-ttu-id="2acb6-122">int</span><span class="sxs-lookup"><span data-stu-id="2acb6-122">int</span></span>  <br/> |<span data-ttu-id="2acb6-123">Exterior</span><span class="sxs-lookup"><span data-stu-id="2acb6-123">Foreign</span></span>  <br/> |<span data-ttu-id="2acb6-124">A ID de locatário deste usuário.</span><span class="sxs-lookup"><span data-stu-id="2acb6-124">This user's Tenant ID.</span></span> <span data-ttu-id="2acb6-125">Consulte a [tabela locatários](tenants.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2acb6-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2acb6-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="2acb6-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="2acb6-127">int</span><span class="sxs-lookup"><span data-stu-id="2acb6-127">int</span></span>  <br/> |<span data-ttu-id="2acb6-128">Exterior</span><span class="sxs-lookup"><span data-stu-id="2acb6-128">Foreign</span></span>  <br/> |<span data-ttu-id="2acb6-129">O tipo de URI deste usuário.</span><span class="sxs-lookup"><span data-stu-id="2acb6-129">This user's URI type.</span></span> <span data-ttu-id="2acb6-130">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2acb6-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

