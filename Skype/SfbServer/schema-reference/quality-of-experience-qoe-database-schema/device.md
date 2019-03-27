---
title: Tabela Device
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: A tabela de dispositivo é uma tabela de suporte que armazena informações sobre a captura de vários ou dispositivos de renderização. Cada registro na tabela representa um dispositivo.
ms.openlocfilehash: 09af6ee11ebc821d123e847fbad812479d9d7bb0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885509"
---
# <a name="device-table"></a><span data-ttu-id="daf80-104">Tabela Device</span><span class="sxs-lookup"><span data-stu-id="daf80-104">Device table</span></span>
 
<span data-ttu-id="daf80-105">A tabela de dispositivo é uma tabela de suporte que armazena informações sobre a captura de vários ou dispositivos de renderização.</span><span class="sxs-lookup"><span data-stu-id="daf80-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="daf80-106">Cada registro na tabela representa um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="daf80-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="daf80-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="daf80-107">**Column**</span></span>|<span data-ttu-id="daf80-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="daf80-108">**Data Type**</span></span>|<span data-ttu-id="daf80-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="daf80-109">**Key/Index**</span></span>|<span data-ttu-id="daf80-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="daf80-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="daf80-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="daf80-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="daf80-112">int</span><span class="sxs-lookup"><span data-stu-id="daf80-112">int</span></span>  <br/> |<span data-ttu-id="daf80-113">Primária</span><span class="sxs-lookup"><span data-stu-id="daf80-113">Primary</span></span>  <br/> |<span data-ttu-id="daf80-114">Número exclusivo que identifica este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="daf80-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="daf80-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="daf80-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="daf80-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="daf80-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="daf80-117">DeviceName + DeviceType é exclusivo</span><span class="sxs-lookup"><span data-stu-id="daf80-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="daf80-118">Nome do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="daf80-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="daf80-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="daf80-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="daf80-120">bit</span><span class="sxs-lookup"><span data-stu-id="daf80-120">bit</span></span>  <br/> |<span data-ttu-id="daf80-121">DeviceName + DeviceType é exclusivo</span><span class="sxs-lookup"><span data-stu-id="daf80-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="daf80-122">Tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="daf80-122">Device type.</span></span> <span data-ttu-id="daf80-123">1 é um dispositivo de captura, 0 é um dispositivo de renderização.</span><span class="sxs-lookup"><span data-stu-id="daf80-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

