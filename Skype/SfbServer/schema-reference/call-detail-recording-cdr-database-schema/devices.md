---
title: Tabela de dispositivos no Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: A tabela de dispositivos é uma tabela de suporte. Cada registro armazena informações sobre um dispositivo (telefone de mesa).
ms.openlocfilehash: efd0894a36e02948a3a8cd9f3465dcdbd30f3e2d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901091"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="47acf-104">Tabela de dispositivos no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="47acf-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="47acf-105">A tabela de dispositivos é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="47acf-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="47acf-106">Cada registro armazena informações sobre um dispositivo (telefone de mesa).</span><span class="sxs-lookup"><span data-stu-id="47acf-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="47acf-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="47acf-107">**Column**</span></span>|<span data-ttu-id="47acf-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="47acf-108">**Data Type**</span></span>|<span data-ttu-id="47acf-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="47acf-109">**Key/Index**</span></span>|<span data-ttu-id="47acf-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="47acf-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="47acf-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="47acf-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="47acf-112">int</span><span class="sxs-lookup"><span data-stu-id="47acf-112">int</span></span>  <br/> |<span data-ttu-id="47acf-113">Primária</span><span class="sxs-lookup"><span data-stu-id="47acf-113">Primary</span></span>  <br/> |<span data-ttu-id="47acf-114">Número exclusivo identificando esta versão de hardware.</span><span class="sxs-lookup"><span data-stu-id="47acf-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="47acf-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="47acf-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="47acf-116">int</span><span class="sxs-lookup"><span data-stu-id="47acf-116">int</span></span>  <br/> |<span data-ttu-id="47acf-117">Externa</span><span class="sxs-lookup"><span data-stu-id="47acf-117">Foreign</span></span>  <br/> |<span data-ttu-id="47acf-118">Fabricante do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="47acf-118">Manufacturer of this device.</span></span> <span data-ttu-id="47acf-119">Consulte a [tabela de fabricantes no Skype para Business Server 2015](manufacturers.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="47acf-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="47acf-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="47acf-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="47acf-121">int</span><span class="sxs-lookup"><span data-stu-id="47acf-121">int</span></span>  <br/> |<span data-ttu-id="47acf-122">Externa</span><span class="sxs-lookup"><span data-stu-id="47acf-122">Foreign</span></span>  <br/> |<span data-ttu-id="47acf-123">Versão de hardware do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="47acf-123">Hardware version of this device.</span></span> <span data-ttu-id="47acf-124">Consulte a [tabela HardwareVersions no Skype para Business Server 2015](hardwareversions.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="47acf-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="47acf-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="47acf-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="47acf-126">bigint</span><span class="sxs-lookup"><span data-stu-id="47acf-126">bigint</span></span>  <br/> ||<span data-ttu-id="47acf-127">Endereço MAC</span><span class="sxs-lookup"><span data-stu-id="47acf-127">MAC Address</span></span>  <br/> |
   

