---
title: Tabela UserSite
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: A tabela UserSite é uma tabela de suporte. Cada registro representa um site de usuário definido na definição de configuração de rede.
ms.openlocfilehash: effc2404a91bf122dc9be9ad371372e8355b230f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="usersite-table"></a><span data-ttu-id="4a27f-104">Tabela UserSite</span><span class="sxs-lookup"><span data-stu-id="4a27f-104">UserSite table</span></span>
 
<span data-ttu-id="4a27f-105">A tabela UserSite é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="4a27f-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="4a27f-106">Cada registro representa um site de usuário definido na definição de configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="4a27f-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="4a27f-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4a27f-107">**Column**</span></span>|<span data-ttu-id="4a27f-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4a27f-108">**Data Type**</span></span>|<span data-ttu-id="4a27f-109">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="4a27f-109">**Key/Index**</span></span>|<span data-ttu-id="4a27f-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="4a27f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4a27f-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="4a27f-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="4a27f-112">int</span><span class="sxs-lookup"><span data-stu-id="4a27f-112">int</span></span>  <br/> |<span data-ttu-id="4a27f-113">Primária</span><span class="sxs-lookup"><span data-stu-id="4a27f-113">Primary</span></span>  <br/> |<span data-ttu-id="4a27f-114">Número exclusivo que identifica o site de usuário.</span><span class="sxs-lookup"><span data-stu-id="4a27f-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="4a27f-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="4a27f-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="4a27f-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="4a27f-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="4a27f-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="4a27f-117">Unique</span></span>  <br/> |<span data-ttu-id="4a27f-118">Nome do site do usuário.</span><span class="sxs-lookup"><span data-stu-id="4a27f-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="4a27f-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="4a27f-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="4a27f-120">int</span><span class="sxs-lookup"><span data-stu-id="4a27f-120">int</span></span>  <br/> |<span data-ttu-id="4a27f-121">Externa</span><span class="sxs-lookup"><span data-stu-id="4a27f-121">Foreign</span></span>  <br/> |<span data-ttu-id="4a27f-122">Citada em [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="4a27f-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

