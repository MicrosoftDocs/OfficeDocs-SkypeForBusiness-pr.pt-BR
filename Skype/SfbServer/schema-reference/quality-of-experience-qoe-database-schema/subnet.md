---
title: Tabela Sub-rede
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: A tabela Subnet é uma tabela de suporte. Cada registro representa uma subrede definida em uma configuração de rede.
ms.openlocfilehash: b4683c654d5d188d2f5096dd7ec9da124001f68b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831331"
---
# <a name="subnet-table"></a><span data-ttu-id="a038b-104">Tabela Sub-rede</span><span class="sxs-lookup"><span data-stu-id="a038b-104">Subnet table</span></span>
 
<span data-ttu-id="a038b-p102">A tabela Subnet é uma tabela de suporte. Cada registro representa uma subrede definida em uma configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="a038b-p102">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="a038b-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a038b-107">**Column**</span></span>|<span data-ttu-id="a038b-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a038b-108">**Data Type**</span></span>|<span data-ttu-id="a038b-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="a038b-109">**Key/Index**</span></span>|<span data-ttu-id="a038b-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a038b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a038b-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="a038b-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="a038b-112">int</span><span class="sxs-lookup"><span data-stu-id="a038b-112">int</span></span>  <br/> |<span data-ttu-id="a038b-113">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="a038b-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="a038b-114">Representação de inteiro para o IP da sub-rede.</span><span class="sxs-lookup"><span data-stu-id="a038b-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="a038b-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="a038b-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="a038b-116">int</span><span class="sxs-lookup"><span data-stu-id="a038b-116">int</span></span>  <br/> ||<span data-ttu-id="a038b-117">Máscara de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="a038b-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="a038b-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="a038b-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="a038b-119">int</span><span class="sxs-lookup"><span data-stu-id="a038b-119">int</span></span>  <br/> |<span data-ttu-id="a038b-120">Externo</span><span class="sxs-lookup"><span data-stu-id="a038b-120">Foreign</span></span>  <br/> |<span data-ttu-id="a038b-121">Referenciado na tabela [UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="a038b-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="a038b-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="a038b-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="a038b-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="a038b-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="a038b-124">A descrição para a sub-rede.</span><span class="sxs-lookup"><span data-stu-id="a038b-124">The description for the subnet.</span></span>  <br/> |
   

