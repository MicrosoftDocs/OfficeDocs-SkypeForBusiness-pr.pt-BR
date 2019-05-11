---
title: Tabela Subnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: A tabela de sub-rede é uma tabela de suporte. Cada registro representa uma sub-rede definida na configuração de configuração de rede.
ms.openlocfilehash: f659d73bbdd654365697a9f853fbb48162e1bba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907063"
---
# <a name="subnet-table"></a><span data-ttu-id="3ba7f-104">Tabela Subnet</span><span class="sxs-lookup"><span data-stu-id="3ba7f-104">Subnet table</span></span>
 
<span data-ttu-id="3ba7f-105">A tabela de sub-rede é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="3ba7f-106">Cada registro representa uma sub-rede definida na configuração de configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="3ba7f-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3ba7f-107">**Column**</span></span>|<span data-ttu-id="3ba7f-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="3ba7f-108">**Data Type**</span></span>|<span data-ttu-id="3ba7f-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="3ba7f-109">**Key/Index**</span></span>|<span data-ttu-id="3ba7f-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="3ba7f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3ba7f-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="3ba7f-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="3ba7f-112">int</span><span class="sxs-lookup"><span data-stu-id="3ba7f-112">int</span></span>  <br/> |<span data-ttu-id="3ba7f-113">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="3ba7f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3ba7f-114">Representação de inteiro para o IP da sub-rede.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="3ba7f-115">**Máscara de sub-rede**</span><span class="sxs-lookup"><span data-stu-id="3ba7f-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="3ba7f-116">int</span><span class="sxs-lookup"><span data-stu-id="3ba7f-116">int</span></span>  <br/> ||<span data-ttu-id="3ba7f-117">Máscara de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="3ba7f-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="3ba7f-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="3ba7f-119">int</span><span class="sxs-lookup"><span data-stu-id="3ba7f-119">int</span></span>  <br/> |<span data-ttu-id="3ba7f-120">Externa</span><span class="sxs-lookup"><span data-stu-id="3ba7f-120">Foreign</span></span>  <br/> |<span data-ttu-id="3ba7f-121">Referenciado de [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="3ba7f-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="3ba7f-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="3ba7f-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="3ba7f-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="3ba7f-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="3ba7f-124">A descrição para a sub-rede.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-124">The description for the subnet.</span></span>  <br/> |
   

