---
title: Tabela NetworkConnectionDetail
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: A tabela NetworkConnectionDetail mapeia os tipos de conexão de rede em identificadores de conexão de rede usados em outro lugar no banco de dados de Qualidade da Experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806301"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="d51a6-104">Tabela NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="d51a6-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="d51a6-105">A tabela NetworkConnectionDetail mapeia os tipos de conexão de rede em identificadores de conexão de rede usados em outro lugar no banco de dados de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="d51a6-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="d51a6-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d51a6-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d51a6-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d51a6-107">**Column**</span></span>|<span data-ttu-id="d51a6-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d51a6-108">**Data Type**</span></span>|<span data-ttu-id="d51a6-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="d51a6-109">**Key/Index**</span></span>|<span data-ttu-id="d51a6-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="d51a6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d51a6-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="d51a6-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="d51a6-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="d51a6-112">tinyint</span></span>  <br/> |<span data-ttu-id="d51a6-113">Primário</span><span class="sxs-lookup"><span data-stu-id="d51a6-113">Primary</span></span>  <br/> |<span data-ttu-id="d51a6-114">Identificador exclusivo do tipo de conexão de rede.</span><span class="sxs-lookup"><span data-stu-id="d51a6-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="d51a6-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="d51a6-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="d51a6-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="d51a6-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="d51a6-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="d51a6-117">Unique</span></span>  <br/> |<span data-ttu-id="d51a6-p103">Tipo de conexão de rede que corresponde a NetworkConnectionDetailKey. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="d51a6-p103">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span>  <br/> <span data-ttu-id="d51a6-120">0 -- Com fio</span><span class="sxs-lookup"><span data-stu-id="d51a6-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="d51a6-121">1 -- Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="d51a6-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="d51a6-122">2 -- Ethernet</span><span class="sxs-lookup"><span data-stu-id="d51a6-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="d51a6-123">3 -- MobileBB</span><span class="sxs-lookup"><span data-stu-id="d51a6-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="d51a6-124">4 -- Outro</span><span class="sxs-lookup"><span data-stu-id="d51a6-124">4 -- Other</span></span>  <br/> <span data-ttu-id="d51a6-125">5 -- Túnel</span><span class="sxs-lookup"><span data-stu-id="d51a6-125">5 -- Tunnel</span></span>  <br/> |
   

