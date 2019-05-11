---
title: Tabela Tenants
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: A tabela de Inquilinos é uma tabela de suporte que armazena uma lista dos vários locatários. Cada registro na tabela representa um inquilino.
ms.openlocfilehash: 68050ce76cc41d3fd66931fbdc0b0d3168786bc8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930203"
---
# <a name="tenants-table"></a><span data-ttu-id="fe01b-104">Tabela Tenants</span><span class="sxs-lookup"><span data-stu-id="fe01b-104">Tenants table</span></span>
 
<span data-ttu-id="fe01b-105">A tabela de Inquilinos é uma tabela de suporte que armazena uma lista dos vários locatários.</span><span class="sxs-lookup"><span data-stu-id="fe01b-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="fe01b-106">Cada registro na tabela representa um inquilino.</span><span class="sxs-lookup"><span data-stu-id="fe01b-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fe01b-107">Na implantação no local, o CDR usa a ID do inquilino integrado para indicar o tipo de autenticação diferente, como conectividade de IM pública, federada e anônima.</span><span class="sxs-lookup"><span data-stu-id="fe01b-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="fe01b-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="fe01b-108">**Column**</span></span>|<span data-ttu-id="fe01b-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="fe01b-109">**Data Type**</span></span>|<span data-ttu-id="fe01b-110">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="fe01b-110">**Key/Index**</span></span>|<span data-ttu-id="fe01b-111">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="fe01b-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fe01b-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="fe01b-112">**TenantId**</span></span> <br/> |<span data-ttu-id="fe01b-113">int</span><span class="sxs-lookup"><span data-stu-id="fe01b-113">int</span></span>  <br/> |<span data-ttu-id="fe01b-114">Primária</span><span class="sxs-lookup"><span data-stu-id="fe01b-114">Primary</span></span>  <br/> |<span data-ttu-id="fe01b-115">Número exclusivo que identifica o ID desse inquilino.</span><span class="sxs-lookup"><span data-stu-id="fe01b-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="fe01b-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="fe01b-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="fe01b-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fe01b-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="fe01b-118">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="fe01b-118">Allowed values:</span></span> <br/>  <span data-ttu-id="fe01b-119">00000000-0000-0000-0000-000000000000-Enterprise</span><span class="sxs-lookup"><span data-stu-id="fe01b-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="fe01b-120">00000000-0000-0000-0000-000000000001-federado</span><span class="sxs-lookup"><span data-stu-id="fe01b-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="fe01b-121">00000000-0000-0000-0000-000000000002 - anônima</span><span class="sxs-lookup"><span data-stu-id="fe01b-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="fe01b-122">00000000-0000-0000-0000-000000000003-conectividade de IM pública</span><span class="sxs-lookup"><span data-stu-id="fe01b-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

