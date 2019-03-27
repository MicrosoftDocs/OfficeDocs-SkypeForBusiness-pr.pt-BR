---
title: Modo de exibição do usuário
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: O modo de exibição do usuário armazena informações sobre os usuários que tiverem sido envolvidos em chamadas ou sessões que têm registros no banco de dados. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: 9e631c101660e8f14bca25f019f5d991a0d9aadd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877640"
---
# <a name="user-view"></a><span data-ttu-id="4db07-104">Modo de exibição do usuário</span><span class="sxs-lookup"><span data-stu-id="4db07-104">User view</span></span>
 
<span data-ttu-id="4db07-105">O modo de exibição do usuário armazena informações sobre os usuários que tiverem sido envolvidos em chamadas ou sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4db07-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="4db07-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4db07-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4db07-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4db07-107">**Column**</span></span>|<span data-ttu-id="4db07-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4db07-108">**Data Type**</span></span>|<span data-ttu-id="4db07-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="4db07-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4db07-110">UserId</span><span class="sxs-lookup"><span data-stu-id="4db07-110">UserId</span></span>  <br/> |<span data-ttu-id="4db07-111">int</span><span class="sxs-lookup"><span data-stu-id="4db07-111">int</span></span>  <br/> |<span data-ttu-id="4db07-112">Número exclusivo que identifica este usuário.</span><span class="sxs-lookup"><span data-stu-id="4db07-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="4db07-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="4db07-113">UserUri</span></span>  <br/> |<span data-ttu-id="4db07-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="4db07-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="4db07-115">URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="4db07-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="4db07-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="4db07-116">TenantKey</span></span>  <br/> |<span data-ttu-id="4db07-117">Identificador exclusivo</span><span class="sxs-lookup"><span data-stu-id="4db07-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="4db07-118">Locatário do usuário.</span><span class="sxs-lookup"><span data-stu-id="4db07-118">Tenant of user.</span></span> <span data-ttu-id="4db07-119">Consulte a [tabela de inquilinos](tenants.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4db07-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4db07-120">UriType</span><span class="sxs-lookup"><span data-stu-id="4db07-120">UriType</span></span>  <br/> |<span data-ttu-id="4db07-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4db07-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4db07-122">Tipo de URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="4db07-122">Type of user URI.</span></span> <span data-ttu-id="4db07-123">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4db07-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

