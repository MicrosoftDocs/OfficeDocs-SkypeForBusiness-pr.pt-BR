---
title: Tabela de dispositivos no Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: A tabela de dispositivos é uma tabela de suporte. Cada registro armazena informações sobre um dispositivo (telefone de mesa).
ms.openlocfilehash: f770f19fb94bf25bdb4c13e74dc41e05f6674788
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881699"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="33bea-104">Tabela de dispositivos no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="33bea-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="33bea-105">A tabela de dispositivos é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="33bea-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="33bea-106">Cada registro armazena informações sobre um dispositivo (telefone de mesa).</span><span class="sxs-lookup"><span data-stu-id="33bea-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="33bea-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="33bea-107">**Column**</span></span>|<span data-ttu-id="33bea-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="33bea-108">**Data Type**</span></span>|<span data-ttu-id="33bea-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="33bea-109">**Key/Index**</span></span>|<span data-ttu-id="33bea-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="33bea-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="33bea-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="33bea-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="33bea-112">int</span><span class="sxs-lookup"><span data-stu-id="33bea-112">int</span></span>  <br/> |<span data-ttu-id="33bea-113">Primária</span><span class="sxs-lookup"><span data-stu-id="33bea-113">Primary</span></span>  <br/> |<span data-ttu-id="33bea-114">Número exclusivo identificando esta versão de hardware.</span><span class="sxs-lookup"><span data-stu-id="33bea-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="33bea-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="33bea-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="33bea-116">int</span><span class="sxs-lookup"><span data-stu-id="33bea-116">int</span></span>  <br/> |<span data-ttu-id="33bea-117">Externa</span><span class="sxs-lookup"><span data-stu-id="33bea-117">Foreign</span></span>  <br/> |<span data-ttu-id="33bea-118">Fabricante do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33bea-118">Manufacturer of this device.</span></span> <span data-ttu-id="33bea-119">Consulte a [tabela de fabricantes no Skype para Business Server 2015](manufacturers.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="33bea-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="33bea-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="33bea-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="33bea-121">int</span><span class="sxs-lookup"><span data-stu-id="33bea-121">int</span></span>  <br/> |<span data-ttu-id="33bea-122">Externa</span><span class="sxs-lookup"><span data-stu-id="33bea-122">Foreign</span></span>  <br/> |<span data-ttu-id="33bea-123">Versão de hardware do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33bea-123">Hardware version of this device.</span></span> <span data-ttu-id="33bea-124">Consulte a [tabela HardwareVersions no Skype para Business Server 2015](hardwareversions.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="33bea-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="33bea-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="33bea-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="33bea-126">bigint</span><span class="sxs-lookup"><span data-stu-id="33bea-126">bigint</span></span>  <br/> ||<span data-ttu-id="33bea-127">Endereço MAC</span><span class="sxs-lookup"><span data-stu-id="33bea-127">MAC Address</span></span>  <br/> |
   

