---
title: Tabela de dispositivos no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: A tabela dispositivos é uma tabela de suporte. Cada registro armazena informações sobre um dispositivo (telefone de mesa).
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296375"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="45bec-104">Tabela de dispositivos no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="45bec-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="45bec-105">A tabela dispositivos é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="45bec-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="45bec-106">Cada registro armazena informações sobre um dispositivo (telefone de mesa).</span><span class="sxs-lookup"><span data-stu-id="45bec-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="45bec-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="45bec-107">**Column**</span></span>|<span data-ttu-id="45bec-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="45bec-108">**Data Type**</span></span>|<span data-ttu-id="45bec-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="45bec-109">**Key/Index**</span></span>|<span data-ttu-id="45bec-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="45bec-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="45bec-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="45bec-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="45bec-112">int</span><span class="sxs-lookup"><span data-stu-id="45bec-112">int</span></span>  <br/> |<span data-ttu-id="45bec-113">Primária</span><span class="sxs-lookup"><span data-stu-id="45bec-113">Primary</span></span>  <br/> |<span data-ttu-id="45bec-114">Número exclusivo que identifica esta versão de hardware.</span><span class="sxs-lookup"><span data-stu-id="45bec-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="45bec-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="45bec-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="45bec-116">int</span><span class="sxs-lookup"><span data-stu-id="45bec-116">int</span></span>  <br/> |<span data-ttu-id="45bec-117">Exterior</span><span class="sxs-lookup"><span data-stu-id="45bec-117">Foreign</span></span>  <br/> |<span data-ttu-id="45bec-118">Fabricante do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="45bec-118">Manufacturer of this device.</span></span> <span data-ttu-id="45bec-119">Consulte a [tabela fabricantes no Skype for Business Server 2015](manufacturers.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="45bec-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="45bec-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="45bec-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="45bec-121">int</span><span class="sxs-lookup"><span data-stu-id="45bec-121">int</span></span>  <br/> |<span data-ttu-id="45bec-122">Exterior</span><span class="sxs-lookup"><span data-stu-id="45bec-122">Foreign</span></span>  <br/> |<span data-ttu-id="45bec-123">Versão de hardware deste dispositivo.</span><span class="sxs-lookup"><span data-stu-id="45bec-123">Hardware version of this device.</span></span> <span data-ttu-id="45bec-124">Consulte a [tabela HardwareVersions no Skype for Business Server 2015](hardwareversions.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="45bec-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="45bec-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="45bec-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="45bec-126">bigint</span><span class="sxs-lookup"><span data-stu-id="45bec-126">bigint</span></span>  <br/> ||<span data-ttu-id="45bec-127">Endereço MAC</span><span class="sxs-lookup"><span data-stu-id="45bec-127">MAC Address</span></span>  <br/> |
   

