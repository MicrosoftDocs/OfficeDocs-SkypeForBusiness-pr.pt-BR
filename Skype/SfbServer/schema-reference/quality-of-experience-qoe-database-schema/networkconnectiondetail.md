---
title: Tabela NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: A tabela NetworkConnectionDetail mapeia tipos de conexão de rede para os identificadores de conexão de rede usados em outro lugar no banco de dados de qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: c13725e7df8a164766faa6847fc8097a24a9df53
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294814"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="cad7e-104">Tabela NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="cad7e-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="cad7e-105">A tabela NetworkConnectionDetail mapeia tipos de conexão de rede para os identificadores de conexão de rede usados em outro lugar no banco de dados de qualidade da experiência.</span><span class="sxs-lookup"><span data-stu-id="cad7e-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="cad7e-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cad7e-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cad7e-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cad7e-107">**Column**</span></span>|<span data-ttu-id="cad7e-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="cad7e-108">**Data Type**</span></span>|<span data-ttu-id="cad7e-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="cad7e-109">**Key/Index**</span></span>|<span data-ttu-id="cad7e-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="cad7e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cad7e-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="cad7e-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="cad7e-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="cad7e-112">tinyint</span></span>  <br/> |<span data-ttu-id="cad7e-113">Primária</span><span class="sxs-lookup"><span data-stu-id="cad7e-113">Primary</span></span>  <br/> |<span data-ttu-id="cad7e-114">Identificador exclusivo do tipo de conexão de rede.</span><span class="sxs-lookup"><span data-stu-id="cad7e-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="cad7e-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="cad7e-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="cad7e-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="cad7e-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="cad7e-117">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="cad7e-117">Unique</span></span>  <br/> |<span data-ttu-id="cad7e-118">Tipo de conexão de rede que corresponde ao NetworkConnectionDetailKey.</span><span class="sxs-lookup"><span data-stu-id="cad7e-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="cad7e-119">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="cad7e-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="cad7e-120">0--com fio</span><span class="sxs-lookup"><span data-stu-id="cad7e-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="cad7e-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="cad7e-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="cad7e-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="cad7e-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="cad7e-123">3--MobileBB</span><span class="sxs-lookup"><span data-stu-id="cad7e-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="cad7e-124">4--outros</span><span class="sxs-lookup"><span data-stu-id="cad7e-124">4 -- Other</span></span>  <br/> <span data-ttu-id="cad7e-125">5--Tunnel</span><span class="sxs-lookup"><span data-stu-id="cad7e-125">5 -- Tunnel</span></span>  <br/> |
   

