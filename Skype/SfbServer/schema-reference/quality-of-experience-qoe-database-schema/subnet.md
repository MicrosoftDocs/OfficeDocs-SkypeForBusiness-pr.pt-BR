---
title: Tabela Subnet
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
ms.openlocfilehash: ed54341e66c3370086047eb9b073d2560172a261
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="subnet-table"></a><span data-ttu-id="e82ea-104">Tabela Subnet</span><span class="sxs-lookup"><span data-stu-id="e82ea-104">Subnet table</span></span>
 
<span data-ttu-id="e82ea-105">A tabela de sub-rede é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="e82ea-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="e82ea-106">Cada registro representa uma sub-rede definida na configuração de configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="e82ea-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="e82ea-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e82ea-107">**Column**</span></span>|<span data-ttu-id="e82ea-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e82ea-108">**Data Type**</span></span>|<span data-ttu-id="e82ea-109">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="e82ea-109">**Key/Index**</span></span>|<span data-ttu-id="e82ea-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="e82ea-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e82ea-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="e82ea-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="e82ea-112">int</span><span class="sxs-lookup"><span data-stu-id="e82ea-112">int</span></span>  <br/> |<span data-ttu-id="e82ea-113">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="e82ea-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e82ea-114">Representação de inteiro para o IP da sub-rede.</span><span class="sxs-lookup"><span data-stu-id="e82ea-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="e82ea-115">**Máscara de sub-rede**</span><span class="sxs-lookup"><span data-stu-id="e82ea-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="e82ea-116">int</span><span class="sxs-lookup"><span data-stu-id="e82ea-116">int</span></span>  <br/> ||<span data-ttu-id="e82ea-117">Máscara de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="e82ea-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="e82ea-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="e82ea-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="e82ea-119">int</span><span class="sxs-lookup"><span data-stu-id="e82ea-119">int</span></span>  <br/> |<span data-ttu-id="e82ea-120">Externa</span><span class="sxs-lookup"><span data-stu-id="e82ea-120">Foreign</span></span>  <br/> |<span data-ttu-id="e82ea-121">Referenciado de [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="e82ea-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="e82ea-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="e82ea-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="e82ea-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="e82ea-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="e82ea-124">A descrição para a sub-rede.</span><span class="sxs-lookup"><span data-stu-id="e82ea-124">The description for the subnet.</span></span>  <br/> |
   

