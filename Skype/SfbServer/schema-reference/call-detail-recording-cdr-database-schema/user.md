---
title: Exibição do usuário
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: A exibição de Usuário armazena informações sobre usuários envolvidos em chamadas ou sessões com registros no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831691"
---
# <a name="user-view"></a><span data-ttu-id="b4bd1-104">Exibição do usuário</span><span class="sxs-lookup"><span data-stu-id="b4bd1-104">User view</span></span>
 
<span data-ttu-id="b4bd1-105">A exibição de Usuário armazena informações sobre usuários envolvidos em chamadas ou sessões com registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b4bd1-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="b4bd1-106">Essa exibição foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b4bd1-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b4bd1-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b4bd1-107">**Column**</span></span>|<span data-ttu-id="b4bd1-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b4bd1-108">**Data Type**</span></span>|<span data-ttu-id="b4bd1-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="b4bd1-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b4bd1-110">UserId</span><span class="sxs-lookup"><span data-stu-id="b4bd1-110">UserId</span></span>  <br/> |<span data-ttu-id="b4bd1-111">int</span><span class="sxs-lookup"><span data-stu-id="b4bd1-111">int</span></span>  <br/> |<span data-ttu-id="b4bd1-112">Número exclusivo que identifica este usuário.</span><span class="sxs-lookup"><span data-stu-id="b4bd1-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="b4bd1-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="b4bd1-113">UserUri</span></span>  <br/> |<span data-ttu-id="b4bd1-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="b4bd1-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="b4bd1-115">Uri do usuário.</span><span class="sxs-lookup"><span data-stu-id="b4bd1-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="b4bd1-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="b4bd1-116">TenantKey</span></span>  <br/> |<span data-ttu-id="b4bd1-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="b4bd1-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="b4bd1-118">Locatário do usuário.</span><span class="sxs-lookup"><span data-stu-id="b4bd1-118">Tenant of user.</span></span> <span data-ttu-id="b4bd1-119">Consulte a [tabela Tenants para](tenants.md) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b4bd1-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="b4bd1-120">UriType</span><span class="sxs-lookup"><span data-stu-id="b4bd1-120">UriType</span></span>  <br/> |<span data-ttu-id="b4bd1-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b4bd1-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b4bd1-122">Tipo de URI do usuário.</span><span class="sxs-lookup"><span data-stu-id="b4bd1-122">Type of user URI.</span></span> <span data-ttu-id="b4bd1-123">Consulte a [tabela UriTypes para](uritypes.md) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b4bd1-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

