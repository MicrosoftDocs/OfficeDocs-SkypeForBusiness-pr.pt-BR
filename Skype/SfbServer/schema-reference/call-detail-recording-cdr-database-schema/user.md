---
title: Exibição do usuário
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: A exibição do usuário armazena informações sobre os usuários que estiveram envolvidos em chamadas ou sessões que têm registros no banco de dados. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 2fe0ba4748a776a8f17065a3c5db21d34bd6340d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295738"
---
# <a name="user-view"></a><span data-ttu-id="78370-104">Exibição do usuário</span><span class="sxs-lookup"><span data-stu-id="78370-104">User view</span></span>
 
<span data-ttu-id="78370-105">A exibição do usuário armazena informações sobre os usuários que estiveram envolvidos em chamadas ou sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="78370-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="78370-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="78370-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="78370-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="78370-107">**Column**</span></span>|<span data-ttu-id="78370-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="78370-108">**Data Type**</span></span>|<span data-ttu-id="78370-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="78370-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="78370-110">ID</span><span class="sxs-lookup"><span data-stu-id="78370-110">UserId</span></span>  <br/> |<span data-ttu-id="78370-111">int</span><span class="sxs-lookup"><span data-stu-id="78370-111">int</span></span>  <br/> |<span data-ttu-id="78370-112">Número exclusivo que identifica esse usuário.</span><span class="sxs-lookup"><span data-stu-id="78370-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="78370-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="78370-113">UserUri</span></span>  <br/> |<span data-ttu-id="78370-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="78370-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="78370-115">URL do usuário.</span><span class="sxs-lookup"><span data-stu-id="78370-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="78370-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="78370-116">TenantKey</span></span>  <br/> |<span data-ttu-id="78370-117">identificador</span><span class="sxs-lookup"><span data-stu-id="78370-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="78370-118">Locatário do usuário.</span><span class="sxs-lookup"><span data-stu-id="78370-118">Tenant of user.</span></span> <span data-ttu-id="78370-119">Consulte a [tabela locatários](tenants.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="78370-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="78370-120">UriType</span><span class="sxs-lookup"><span data-stu-id="78370-120">UriType</span></span>  <br/> |<span data-ttu-id="78370-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="78370-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="78370-122">Tipo de URI de usuário.</span><span class="sxs-lookup"><span data-stu-id="78370-122">Type of user URI.</span></span> <span data-ttu-id="78370-123">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="78370-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

