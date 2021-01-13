---
title: Tabela Devices no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: A tabela Devices é uma tabela de suporte. Cada registro armazena informações sobre um dispositivo (telefone de mesa).
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831811"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c3c1d-104">Tabela Devices no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c3c1d-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c3c1d-105">A tabela Devices é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="c3c1d-106">Cada registro armazena informações sobre um dispositivo (telefone de mesa).</span><span class="sxs-lookup"><span data-stu-id="c3c1d-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="c3c1d-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c3c1d-107">**Column**</span></span>|<span data-ttu-id="c3c1d-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c3c1d-108">**Data Type**</span></span>|<span data-ttu-id="c3c1d-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="c3c1d-109">**Key/Index**</span></span>|<span data-ttu-id="c3c1d-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="c3c1d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c3c1d-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="c3c1d-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="c3c1d-112">int</span><span class="sxs-lookup"><span data-stu-id="c3c1d-112">int</span></span>  <br/> |<span data-ttu-id="c3c1d-113">Primário</span><span class="sxs-lookup"><span data-stu-id="c3c1d-113">Primary</span></span>  <br/> |<span data-ttu-id="c3c1d-114">Número exclusivo que identifica esta versão de hardware.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="c3c1d-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="c3c1d-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="c3c1d-116">int</span><span class="sxs-lookup"><span data-stu-id="c3c1d-116">int</span></span>  <br/> |<span data-ttu-id="c3c1d-117">Externo</span><span class="sxs-lookup"><span data-stu-id="c3c1d-117">Foreign</span></span>  <br/> |<span data-ttu-id="c3c1d-118">Fabricante deste dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-118">Manufacturer of this device.</span></span> <span data-ttu-id="c3c1d-119">Consulte a [tabela Manufacturers no Skype for Business Server 2015](manufacturers.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c3c1d-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="c3c1d-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="c3c1d-121">int</span><span class="sxs-lookup"><span data-stu-id="c3c1d-121">int</span></span>  <br/> |<span data-ttu-id="c3c1d-122">Externo</span><span class="sxs-lookup"><span data-stu-id="c3c1d-122">Foreign</span></span>  <br/> |<span data-ttu-id="c3c1d-123">Versão de hardware deste dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-123">Hardware version of this device.</span></span> <span data-ttu-id="c3c1d-124">Consulte a [tabela HardwareVersions no Skype for Business Server 2015](hardwareversions.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c3c1d-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c3c1d-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="c3c1d-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="c3c1d-126">bigint</span><span class="sxs-lookup"><span data-stu-id="c3c1d-126">bigint</span></span>  <br/> ||<span data-ttu-id="c3c1d-127">Endereço MAC</span><span class="sxs-lookup"><span data-stu-id="c3c1d-127">MAC Address</span></span>  <br/> |
   

