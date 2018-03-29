---
title: Tabela de dispositivos no Skype para Business Server 2015
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
ms.openlocfilehash: c7a5a5933d4fe2e465faf039a8ac2ed2a65fa563
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e8f86-104">Tabela de dispositivos no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e8f86-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e8f86-105">A tabela de dispositivos é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="e8f86-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="e8f86-106">Cada registro armazena informações sobre um dispositivo (telefone de mesa).</span><span class="sxs-lookup"><span data-stu-id="e8f86-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="e8f86-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e8f86-107">**Column**</span></span>|<span data-ttu-id="e8f86-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e8f86-108">**Data Type**</span></span>|<span data-ttu-id="e8f86-109">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="e8f86-109">**Key/Index**</span></span>|<span data-ttu-id="e8f86-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="e8f86-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e8f86-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="e8f86-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="e8f86-112">int</span><span class="sxs-lookup"><span data-stu-id="e8f86-112">int</span></span>  <br/> |<span data-ttu-id="e8f86-113">Primária</span><span class="sxs-lookup"><span data-stu-id="e8f86-113">Primary</span></span>  <br/> |<span data-ttu-id="e8f86-114">Número exclusivo identificando esta versão de hardware.</span><span class="sxs-lookup"><span data-stu-id="e8f86-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="e8f86-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="e8f86-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="e8f86-116">int</span><span class="sxs-lookup"><span data-stu-id="e8f86-116">int</span></span>  <br/> |<span data-ttu-id="e8f86-117">Externa</span><span class="sxs-lookup"><span data-stu-id="e8f86-117">Foreign</span></span>  <br/> |<span data-ttu-id="e8f86-118">Fabricante do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e8f86-118">Manufacturer of this device.</span></span> <span data-ttu-id="e8f86-119">Consulte a [tabela de fabricantes no Skype para Business Server 2015](manufacturers.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e8f86-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e8f86-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="e8f86-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="e8f86-121">int</span><span class="sxs-lookup"><span data-stu-id="e8f86-121">int</span></span>  <br/> |<span data-ttu-id="e8f86-122">Externa</span><span class="sxs-lookup"><span data-stu-id="e8f86-122">Foreign</span></span>  <br/> |<span data-ttu-id="e8f86-123">Versão de hardware do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e8f86-123">Hardware version of this device.</span></span> <span data-ttu-id="e8f86-124">Consulte a [tabela HardwareVersions no Skype para Business Server 2015](hardwareversions.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e8f86-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e8f86-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="e8f86-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="e8f86-126">bigint</span><span class="sxs-lookup"><span data-stu-id="e8f86-126">bigint</span></span>  <br/> ||<span data-ttu-id="e8f86-127">Endereço MAC</span><span class="sxs-lookup"><span data-stu-id="e8f86-127">MAC Address</span></span>  <br/> |
   

