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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213176"
---
# <a name="user-view"></a><span data-ttu-id="afa8a-104">Modo de exibição do usuário</span><span class="sxs-lookup"><span data-stu-id="afa8a-104">User view</span></span>
 
<span data-ttu-id="afa8a-105">O modo de exibição do usuário armazena informações sobre os usuários que tiverem sido envolvidos em chamadas ou sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afa8a-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="afa8a-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afa8a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="afa8a-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="afa8a-107">**Column**</span></span>|<span data-ttu-id="afa8a-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="afa8a-108">**Data Type**</span></span>|<span data-ttu-id="afa8a-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="afa8a-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="afa8a-110">UserId</span><span class="sxs-lookup"><span data-stu-id="afa8a-110">UserId</span></span>  <br/> |<span data-ttu-id="afa8a-111">int</span><span class="sxs-lookup"><span data-stu-id="afa8a-111">int</span></span>  <br/> |<span data-ttu-id="afa8a-112">Número exclusivo que identifica este usuário.</span><span class="sxs-lookup"><span data-stu-id="afa8a-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="afa8a-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="afa8a-113">UserUri</span></span>  <br/> |<span data-ttu-id="afa8a-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="afa8a-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="afa8a-115">URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="afa8a-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="afa8a-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="afa8a-116">TenantKey</span></span>  <br/> |<span data-ttu-id="afa8a-117">Identificador exclusivo</span><span class="sxs-lookup"><span data-stu-id="afa8a-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="afa8a-118">Locatário do usuário.</span><span class="sxs-lookup"><span data-stu-id="afa8a-118">Tenant of user.</span></span> <span data-ttu-id="afa8a-119">Consulte a [tabela de inquilinos](tenants.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="afa8a-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="afa8a-120">UriType</span><span class="sxs-lookup"><span data-stu-id="afa8a-120">UriType</span></span>  <br/> |<span data-ttu-id="afa8a-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="afa8a-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="afa8a-122">Tipo de URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="afa8a-122">Type of user URI.</span></span> <span data-ttu-id="afa8a-123">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="afa8a-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

