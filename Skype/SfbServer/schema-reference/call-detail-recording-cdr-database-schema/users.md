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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: A tabela usuários é uma tabela de suporte. Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que têm registros no banco de dados.
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814799"
---
# <a name="users-table"></a><span data-ttu-id="bafcb-104">Tabela Users</span><span class="sxs-lookup"><span data-stu-id="bafcb-104">Users table</span></span>
 
<span data-ttu-id="bafcb-105">A tabela usuários é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="bafcb-105">The Users table is a supporting table.</span></span> <span data-ttu-id="bafcb-106">Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bafcb-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="bafcb-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="bafcb-107">**Column**</span></span>|<span data-ttu-id="bafcb-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="bafcb-108">**Data Type**</span></span>|<span data-ttu-id="bafcb-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="bafcb-109">**Key/Index**</span></span>|<span data-ttu-id="bafcb-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="bafcb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bafcb-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="bafcb-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="bafcb-112">datetime</span><span class="sxs-lookup"><span data-stu-id="bafcb-112">datetime</span></span>  <br/> ||<span data-ttu-id="bafcb-113">Carimbo de data/hora para uso interno.</span><span class="sxs-lookup"><span data-stu-id="bafcb-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="bafcb-114">**ID**</span><span class="sxs-lookup"><span data-stu-id="bafcb-114">**UserId**</span></span> <br/> |<span data-ttu-id="bafcb-115">int</span><span class="sxs-lookup"><span data-stu-id="bafcb-115">int</span></span>  <br/> |<span data-ttu-id="bafcb-116">Primária</span><span class="sxs-lookup"><span data-stu-id="bafcb-116">Primary</span></span>  <br/> |<span data-ttu-id="bafcb-117">Número exclusivo que identifica esse usuário.</span><span class="sxs-lookup"><span data-stu-id="bafcb-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="bafcb-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="bafcb-118">**UserUri**</span></span> <br/> |<span data-ttu-id="bafcb-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="bafcb-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="bafcb-120">URI de usuário.</span><span class="sxs-lookup"><span data-stu-id="bafcb-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="bafcb-121">**Tenantid**</span><span class="sxs-lookup"><span data-stu-id="bafcb-121">**TenantId**</span></span> <br/> |<span data-ttu-id="bafcb-122">int</span><span class="sxs-lookup"><span data-stu-id="bafcb-122">int</span></span>  <br/> |<span data-ttu-id="bafcb-123">Exterior</span><span class="sxs-lookup"><span data-stu-id="bafcb-123">Foreign</span></span>  <br/> |<span data-ttu-id="bafcb-124">A ID de locatário deste usuário.</span><span class="sxs-lookup"><span data-stu-id="bafcb-124">This user's Tenant ID.</span></span> <span data-ttu-id="bafcb-125">Consulte a [tabela locatários](tenants.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bafcb-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="bafcb-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="bafcb-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="bafcb-127">int</span><span class="sxs-lookup"><span data-stu-id="bafcb-127">int</span></span>  <br/> |<span data-ttu-id="bafcb-128">Exterior</span><span class="sxs-lookup"><span data-stu-id="bafcb-128">Foreign</span></span>  <br/> |<span data-ttu-id="bafcb-129">O tipo de URI deste usuário.</span><span class="sxs-lookup"><span data-stu-id="bafcb-129">This user's URI type.</span></span> <span data-ttu-id="bafcb-130">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bafcb-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

