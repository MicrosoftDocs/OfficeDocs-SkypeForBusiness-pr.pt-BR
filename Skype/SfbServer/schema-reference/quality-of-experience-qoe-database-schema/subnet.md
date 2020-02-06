---
title: Tabela Subnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: A tabela de sub-rede é uma tabela de suporte. Cada registro representa uma sub-rede definida na configuração de rede.
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805199"
---
# <a name="subnet-table"></a><span data-ttu-id="8505f-104">Tabela Subnet</span><span class="sxs-lookup"><span data-stu-id="8505f-104">Subnet table</span></span>
 
<span data-ttu-id="8505f-105">A tabela de sub-rede é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="8505f-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="8505f-106">Cada registro representa uma sub-rede definida na configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="8505f-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="8505f-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="8505f-107">**Column**</span></span>|<span data-ttu-id="8505f-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="8505f-108">**Data Type**</span></span>|<span data-ttu-id="8505f-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="8505f-109">**Key/Index**</span></span>|<span data-ttu-id="8505f-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="8505f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8505f-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="8505f-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="8505f-112">int</span><span class="sxs-lookup"><span data-stu-id="8505f-112">int</span></span>  <br/> |<span data-ttu-id="8505f-113">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="8505f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="8505f-114">Representação do inteiro para o IP da sub-rede.</span><span class="sxs-lookup"><span data-stu-id="8505f-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="8505f-115">**Máscara_de_Sub-rede**</span><span class="sxs-lookup"><span data-stu-id="8505f-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="8505f-116">int</span><span class="sxs-lookup"><span data-stu-id="8505f-116">int</span></span>  <br/> ||<span data-ttu-id="8505f-117">Máscara de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="8505f-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="8505f-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="8505f-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="8505f-119">int</span><span class="sxs-lookup"><span data-stu-id="8505f-119">int</span></span>  <br/> |<span data-ttu-id="8505f-120">Exterior</span><span class="sxs-lookup"><span data-stu-id="8505f-120">Foreign</span></span>  <br/> |<span data-ttu-id="8505f-121">Referenciado da [tabela usersite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="8505f-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="8505f-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="8505f-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="8505f-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="8505f-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="8505f-124">A descrição da sub-rede.</span><span class="sxs-lookup"><span data-stu-id="8505f-124">The description for the subnet.</span></span>  <br/> |
   

