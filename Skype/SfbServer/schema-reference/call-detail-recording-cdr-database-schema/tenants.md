---
title: Tabela Tenants
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: A tabela de Inquilinos é uma tabela de suporte que armazena uma lista dos vários locatários. Cada registro na tabela representa um inquilino.
ms.openlocfilehash: cf7d0271c9cacfd76079a80a7e5db63d669a8dfb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873987"
---
# <a name="tenants-table"></a><span data-ttu-id="73708-104">Tabela Tenants</span><span class="sxs-lookup"><span data-stu-id="73708-104">Tenants table</span></span>
 
<span data-ttu-id="73708-105">A tabela de Inquilinos é uma tabela de suporte que armazena uma lista dos vários locatários.</span><span class="sxs-lookup"><span data-stu-id="73708-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="73708-106">Cada registro na tabela representa um inquilino.</span><span class="sxs-lookup"><span data-stu-id="73708-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="73708-107">Na implantação no local, o CDR usa a ID do inquilino integrado para indicar o tipo de autenticação diferente, como conectividade de IM pública, federada e anônima.</span><span class="sxs-lookup"><span data-stu-id="73708-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="73708-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="73708-108">**Column**</span></span>|<span data-ttu-id="73708-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="73708-109">**Data Type**</span></span>|<span data-ttu-id="73708-110">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="73708-110">**Key/Index**</span></span>|<span data-ttu-id="73708-111">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="73708-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="73708-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="73708-112">**TenantId**</span></span> <br/> |<span data-ttu-id="73708-113">int</span><span class="sxs-lookup"><span data-stu-id="73708-113">int</span></span>  <br/> |<span data-ttu-id="73708-114">Primária</span><span class="sxs-lookup"><span data-stu-id="73708-114">Primary</span></span>  <br/> |<span data-ttu-id="73708-115">Número exclusivo que identifica o ID desse inquilino.</span><span class="sxs-lookup"><span data-stu-id="73708-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="73708-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="73708-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="73708-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="73708-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="73708-118">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="73708-118">Allowed values:</span></span> <br/>  <span data-ttu-id="73708-119">00000000-0000-0000-0000-000000000000-Enterprise</span><span class="sxs-lookup"><span data-stu-id="73708-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="73708-120">00000000-0000-0000-0000-000000000001-federado</span><span class="sxs-lookup"><span data-stu-id="73708-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="73708-121">00000000-0000-0000-0000-000000000002 - anônima</span><span class="sxs-lookup"><span data-stu-id="73708-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="73708-122">00000000-0000-0000-0000-000000000003-conectividade de IM pública</span><span class="sxs-lookup"><span data-stu-id="73708-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   

