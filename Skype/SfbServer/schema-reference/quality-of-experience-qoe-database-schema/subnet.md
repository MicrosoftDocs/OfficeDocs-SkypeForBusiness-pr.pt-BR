---
title: Tabela Subnet
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: A tabela de sub-rede é uma tabela de suporte. Cada registro representa uma sub-rede definida na configuração de configuração de rede.
ms.openlocfilehash: aa91202bfb46a96f86ea3a631be3b964a17a6058
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880473"
---
# <a name="subnet-table"></a><span data-ttu-id="2ecc3-104">Tabela Subnet</span><span class="sxs-lookup"><span data-stu-id="2ecc3-104">Subnet table</span></span>
 
<span data-ttu-id="2ecc3-105">A tabela de sub-rede é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="2ecc3-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="2ecc3-106">Cada registro representa uma sub-rede definida na configuração de configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="2ecc3-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="2ecc3-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2ecc3-107">**Column**</span></span>|<span data-ttu-id="2ecc3-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="2ecc3-108">**Data Type**</span></span>|<span data-ttu-id="2ecc3-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="2ecc3-109">**Key/Index**</span></span>|<span data-ttu-id="2ecc3-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="2ecc3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2ecc3-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="2ecc3-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="2ecc3-112">int</span><span class="sxs-lookup"><span data-stu-id="2ecc3-112">int</span></span>  <br/> |<span data-ttu-id="2ecc3-113">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="2ecc3-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2ecc3-114">Representação de inteiro para o IP da sub-rede.</span><span class="sxs-lookup"><span data-stu-id="2ecc3-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="2ecc3-115">**Máscara de sub-rede**</span><span class="sxs-lookup"><span data-stu-id="2ecc3-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="2ecc3-116">int</span><span class="sxs-lookup"><span data-stu-id="2ecc3-116">int</span></span>  <br/> ||<span data-ttu-id="2ecc3-117">Máscara de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="2ecc3-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="2ecc3-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="2ecc3-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="2ecc3-119">int</span><span class="sxs-lookup"><span data-stu-id="2ecc3-119">int</span></span>  <br/> |<span data-ttu-id="2ecc3-120">Externa</span><span class="sxs-lookup"><span data-stu-id="2ecc3-120">Foreign</span></span>  <br/> |<span data-ttu-id="2ecc3-121">Referenciado de [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="2ecc3-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="2ecc3-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="2ecc3-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="2ecc3-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="2ecc3-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="2ecc3-124">A descrição para a sub-rede.</span><span class="sxs-lookup"><span data-stu-id="2ecc3-124">The description for the subnet.</span></span>  <br/> |
   

