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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: A tabela dispositivos é uma tabela de suporte. Cada registro armazena informações sobre um dispositivo (telefone de mesa).
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815279"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="91cbd-104">Tabela de dispositivos no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="91cbd-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="91cbd-105">A tabela dispositivos é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="91cbd-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="91cbd-106">Cada registro armazena informações sobre um dispositivo (telefone de mesa).</span><span class="sxs-lookup"><span data-stu-id="91cbd-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="91cbd-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="91cbd-107">**Column**</span></span>|<span data-ttu-id="91cbd-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="91cbd-108">**Data Type**</span></span>|<span data-ttu-id="91cbd-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="91cbd-109">**Key/Index**</span></span>|<span data-ttu-id="91cbd-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="91cbd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="91cbd-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="91cbd-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="91cbd-112">int</span><span class="sxs-lookup"><span data-stu-id="91cbd-112">int</span></span>  <br/> |<span data-ttu-id="91cbd-113">Primária</span><span class="sxs-lookup"><span data-stu-id="91cbd-113">Primary</span></span>  <br/> |<span data-ttu-id="91cbd-114">Número exclusivo que identifica esta versão de hardware.</span><span class="sxs-lookup"><span data-stu-id="91cbd-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="91cbd-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="91cbd-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="91cbd-116">int</span><span class="sxs-lookup"><span data-stu-id="91cbd-116">int</span></span>  <br/> |<span data-ttu-id="91cbd-117">Exterior</span><span class="sxs-lookup"><span data-stu-id="91cbd-117">Foreign</span></span>  <br/> |<span data-ttu-id="91cbd-118">Fabricante do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91cbd-118">Manufacturer of this device.</span></span> <span data-ttu-id="91cbd-119">Consulte a [tabela fabricantes no Skype for Business Server 2015](manufacturers.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="91cbd-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="91cbd-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="91cbd-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="91cbd-121">int</span><span class="sxs-lookup"><span data-stu-id="91cbd-121">int</span></span>  <br/> |<span data-ttu-id="91cbd-122">Exterior</span><span class="sxs-lookup"><span data-stu-id="91cbd-122">Foreign</span></span>  <br/> |<span data-ttu-id="91cbd-123">Versão de hardware deste dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91cbd-123">Hardware version of this device.</span></span> <span data-ttu-id="91cbd-124">Consulte a [tabela HardwareVersions no Skype for Business Server 2015](hardwareversions.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="91cbd-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="91cbd-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="91cbd-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="91cbd-126">bigint</span><span class="sxs-lookup"><span data-stu-id="91cbd-126">bigint</span></span>  <br/> ||<span data-ttu-id="91cbd-127">Endereço MAC</span><span class="sxs-lookup"><span data-stu-id="91cbd-127">MAC Address</span></span>  <br/> |
   

