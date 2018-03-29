---
title: Tabela NetworkConnectionDetail
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: A tabela NetworkConnectionDetail mapeia os tipos de conexão de rede para os identificadores de conexão de rede usados em outros locais no banco de dados de qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: cc1eb91d3c633ed9455a0476b613430dfa8e3d6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="4096c-104">Tabela NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="4096c-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="4096c-105">A tabela NetworkConnectionDetail mapeia os tipos de conexão de rede para os identificadores de conexão de rede usados em outros locais no banco de dados de qualidade da experiência.</span><span class="sxs-lookup"><span data-stu-id="4096c-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="4096c-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4096c-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4096c-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4096c-107">**Column**</span></span>|<span data-ttu-id="4096c-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4096c-108">**Data Type**</span></span>|<span data-ttu-id="4096c-109">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="4096c-109">**Key/Index**</span></span>|<span data-ttu-id="4096c-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="4096c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4096c-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="4096c-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="4096c-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="4096c-112">tinyint</span></span>  <br/> |<span data-ttu-id="4096c-113">Primária</span><span class="sxs-lookup"><span data-stu-id="4096c-113">Primary</span></span>  <br/> |<span data-ttu-id="4096c-114">Identificador exclusivo para o tipo de conexão de rede.</span><span class="sxs-lookup"><span data-stu-id="4096c-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="4096c-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="4096c-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="4096c-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="4096c-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="4096c-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="4096c-117">Unique</span></span>  <br/> |<span data-ttu-id="4096c-118">Tipo de conexão de rede que corresponde ao NetworkConnectionDetailKey.</span><span class="sxs-lookup"><span data-stu-id="4096c-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="4096c-119">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="4096c-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="4096c-120">0--com fio</span><span class="sxs-lookup"><span data-stu-id="4096c-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="4096c-121">1-- WiFi</span><span class="sxs-lookup"><span data-stu-id="4096c-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="4096c-122">2-- Ethernet</span><span class="sxs-lookup"><span data-stu-id="4096c-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="4096c-123">3-- MobileBB</span><span class="sxs-lookup"><span data-stu-id="4096c-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="4096c-124">4 – outros</span><span class="sxs-lookup"><span data-stu-id="4096c-124">4 -- Other</span></span>  <br/> <span data-ttu-id="4096c-125">5 – túnel</span><span class="sxs-lookup"><span data-stu-id="4096c-125">5 -- Tunnel</span></span>  <br/> |
   

