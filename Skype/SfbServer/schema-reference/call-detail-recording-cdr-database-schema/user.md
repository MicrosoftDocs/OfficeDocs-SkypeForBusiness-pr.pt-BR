---
title: Modo de exibição do usuário
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
ms.openlocfilehash: 014b773a60cc053c0ec258c7dd853e31a590319c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="user-view"></a><span data-ttu-id="4e74e-104">Modo de exibição do usuário</span><span class="sxs-lookup"><span data-stu-id="4e74e-104">User view</span></span>
 
<span data-ttu-id="4e74e-105">O modo de exibição do usuário armazena informações sobre os usuários que tiverem sido envolvidos em chamadas ou sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4e74e-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="4e74e-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e74e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4e74e-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4e74e-107">**Column**</span></span>|<span data-ttu-id="4e74e-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4e74e-108">**Data Type**</span></span>|<span data-ttu-id="4e74e-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="4e74e-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4e74e-110">UserId</span><span class="sxs-lookup"><span data-stu-id="4e74e-110">UserId</span></span>  <br/> |<span data-ttu-id="4e74e-111">int</span><span class="sxs-lookup"><span data-stu-id="4e74e-111">int</span></span>  <br/> |<span data-ttu-id="4e74e-112">Número exclusivo que identifica este usuário.</span><span class="sxs-lookup"><span data-stu-id="4e74e-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="4e74e-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="4e74e-113">UserUri</span></span>  <br/> |<span data-ttu-id="4e74e-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="4e74e-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="4e74e-115">URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="4e74e-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="4e74e-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="4e74e-116">TenantKey</span></span>  <br/> |<span data-ttu-id="4e74e-117">Identificador exclusivo</span><span class="sxs-lookup"><span data-stu-id="4e74e-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="4e74e-118">Locatário do usuário.</span><span class="sxs-lookup"><span data-stu-id="4e74e-118">Tenant of user.</span></span> <span data-ttu-id="4e74e-119">Consulte a [tabela de inquilinos](tenants.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4e74e-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="4e74e-120">UriType</span><span class="sxs-lookup"><span data-stu-id="4e74e-120">UriType</span></span>  <br/> |<span data-ttu-id="4e74e-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4e74e-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4e74e-122">Tipo de URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="4e74e-122">Type of user URI.</span></span> <span data-ttu-id="4e74e-123">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4e74e-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

