---
title: Tabela Tenants
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: A tabela locatários é uma tabela de suporte que armazena uma lista de vários locatários. Cada registro na tabela representa um locatário.
ms.openlocfilehash: ecc83a429cb2e95426b289216f69d3a14e1826d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814849"
---
# <a name="tenants-table"></a><span data-ttu-id="60457-104">Tabela Tenants</span><span class="sxs-lookup"><span data-stu-id="60457-104">Tenants table</span></span>
 
<span data-ttu-id="60457-105">A tabela locatários é uma tabela de suporte que armazena uma lista de vários locatários.</span><span class="sxs-lookup"><span data-stu-id="60457-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="60457-106">Cada registro na tabela representa um locatário.</span><span class="sxs-lookup"><span data-stu-id="60457-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="60457-107">Na implantação local, o CDR usa a ID de locatário de compilação para indicar um tipo de autenticação diferente, como conectividade de mensagem de chat pública, federada e anônima.</span><span class="sxs-lookup"><span data-stu-id="60457-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="60457-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="60457-108">**Column**</span></span>|<span data-ttu-id="60457-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="60457-109">**Data Type**</span></span>|<span data-ttu-id="60457-110">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="60457-110">**Key/Index**</span></span>|<span data-ttu-id="60457-111">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="60457-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="60457-112">**Tenantid**</span><span class="sxs-lookup"><span data-stu-id="60457-112">**TenantId**</span></span> <br/> |<span data-ttu-id="60457-113">int</span><span class="sxs-lookup"><span data-stu-id="60457-113">int</span></span>  <br/> |<span data-ttu-id="60457-114">Primária</span><span class="sxs-lookup"><span data-stu-id="60457-114">Primary</span></span>  <br/> |<span data-ttu-id="60457-115">Número exclusivo que identifica esta ID de locatário.</span><span class="sxs-lookup"><span data-stu-id="60457-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="60457-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="60457-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="60457-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="60457-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="60457-118">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="60457-118">Allowed values:</span></span> <br/>  <span data-ttu-id="60457-119">00000000-0000-0000-0000-000000000000-empresa</span><span class="sxs-lookup"><span data-stu-id="60457-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="60457-120">00000000-0000-0000-0000-000000000001-federado</span><span class="sxs-lookup"><span data-stu-id="60457-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="60457-121">00000000-0000-0000-0000-000000000002-anônimo</span><span class="sxs-lookup"><span data-stu-id="60457-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="60457-122">00000000-0000-0000-0000-000000000003-conectividade de IM pública</span><span class="sxs-lookup"><span data-stu-id="60457-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

