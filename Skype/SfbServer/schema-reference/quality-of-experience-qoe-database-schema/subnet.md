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
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: A tabela de sub-rede é uma tabela de suporte. Cada registro representa uma sub-rede definida na configuração de rede.
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294632"
---
# <a name="subnet-table"></a><span data-ttu-id="b2f5d-104">Tabela Subnet</span><span class="sxs-lookup"><span data-stu-id="b2f5d-104">Subnet table</span></span>
 
<span data-ttu-id="b2f5d-105">A tabela de sub-rede é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="b2f5d-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="b2f5d-106">Cada registro representa uma sub-rede definida na configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="b2f5d-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="b2f5d-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b2f5d-107">**Column**</span></span>|<span data-ttu-id="b2f5d-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b2f5d-108">**Data Type**</span></span>|<span data-ttu-id="b2f5d-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="b2f5d-109">**Key/Index**</span></span>|<span data-ttu-id="b2f5d-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="b2f5d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b2f5d-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="b2f5d-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="b2f5d-112">int</span><span class="sxs-lookup"><span data-stu-id="b2f5d-112">int</span></span>  <br/> |<span data-ttu-id="b2f5d-113">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="b2f5d-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b2f5d-114">Representação do inteiro para o IP da sub-rede.</span><span class="sxs-lookup"><span data-stu-id="b2f5d-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="b2f5d-115">**Máscara_de_Sub-rede**</span><span class="sxs-lookup"><span data-stu-id="b2f5d-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="b2f5d-116">int</span><span class="sxs-lookup"><span data-stu-id="b2f5d-116">int</span></span>  <br/> ||<span data-ttu-id="b2f5d-117">Máscara de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="b2f5d-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="b2f5d-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="b2f5d-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="b2f5d-119">int</span><span class="sxs-lookup"><span data-stu-id="b2f5d-119">int</span></span>  <br/> |<span data-ttu-id="b2f5d-120">Exterior</span><span class="sxs-lookup"><span data-stu-id="b2f5d-120">Foreign</span></span>  <br/> |<span data-ttu-id="b2f5d-121">Referenciado da [tabela usersite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="b2f5d-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="b2f5d-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="b2f5d-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="b2f5d-123">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="b2f5d-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="b2f5d-124">A descrição da sub-rede.</span><span class="sxs-lookup"><span data-stu-id="b2f5d-124">The description for the subnet.</span></span>  <br/> |
   

