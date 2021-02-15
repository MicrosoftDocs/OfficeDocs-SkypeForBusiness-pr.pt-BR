---
title: Tabela Users
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: A tabela Usuários é uma tabela de suporte. Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que tenham registros no banco de dados.
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831611"
---
# <a name="users-table"></a><span data-ttu-id="6eb75-104">Tabela Users</span><span class="sxs-lookup"><span data-stu-id="6eb75-104">Users table</span></span>
 
<span data-ttu-id="6eb75-105">A tabela Usuários é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="6eb75-105">The Users table is a supporting table.</span></span> <span data-ttu-id="6eb75-106">Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que tenham registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6eb75-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="6eb75-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6eb75-107">**Column**</span></span>|<span data-ttu-id="6eb75-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="6eb75-108">**Data Type**</span></span>|<span data-ttu-id="6eb75-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="6eb75-109">**Key/Index**</span></span>|<span data-ttu-id="6eb75-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="6eb75-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6eb75-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="6eb75-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="6eb75-112">datetime</span><span class="sxs-lookup"><span data-stu-id="6eb75-112">datetime</span></span>  <br/> ||<span data-ttu-id="6eb75-113">Carimbo de data/hora para uso interno.</span><span class="sxs-lookup"><span data-stu-id="6eb75-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="6eb75-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="6eb75-114">**UserId**</span></span> <br/> |<span data-ttu-id="6eb75-115">int</span><span class="sxs-lookup"><span data-stu-id="6eb75-115">int</span></span>  <br/> |<span data-ttu-id="6eb75-116">Primário</span><span class="sxs-lookup"><span data-stu-id="6eb75-116">Primary</span></span>  <br/> |<span data-ttu-id="6eb75-117">Número exclusivo identificando este usuário.</span><span class="sxs-lookup"><span data-stu-id="6eb75-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="6eb75-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="6eb75-118">**UserUri**</span></span> <br/> |<span data-ttu-id="6eb75-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6eb75-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="6eb75-120">URI do Usuário.</span><span class="sxs-lookup"><span data-stu-id="6eb75-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="6eb75-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="6eb75-121">**TenantId**</span></span> <br/> |<span data-ttu-id="6eb75-122">int</span><span class="sxs-lookup"><span data-stu-id="6eb75-122">int</span></span>  <br/> |<span data-ttu-id="6eb75-123">Externo</span><span class="sxs-lookup"><span data-stu-id="6eb75-123">Foreign</span></span>  <br/> |<span data-ttu-id="6eb75-124">A ID de locatário do usuário.</span><span class="sxs-lookup"><span data-stu-id="6eb75-124">This user's Tenant ID.</span></span> <span data-ttu-id="6eb75-125">Consulte a [tabela Tenants para](tenants.md) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6eb75-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6eb75-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="6eb75-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="6eb75-127">int</span><span class="sxs-lookup"><span data-stu-id="6eb75-127">int</span></span>  <br/> |<span data-ttu-id="6eb75-128">Externo</span><span class="sxs-lookup"><span data-stu-id="6eb75-128">Foreign</span></span>  <br/> |<span data-ttu-id="6eb75-129">Tipo de URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="6eb75-129">This user's URI type.</span></span> <span data-ttu-id="6eb75-130">Consulte a [tabela UriTypes para](uritypes.md) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6eb75-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

