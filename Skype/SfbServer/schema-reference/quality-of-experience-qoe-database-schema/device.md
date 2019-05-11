---
title: Tabela Device
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: A tabela de dispositivo é uma tabela de suporte que armazena informações sobre a captura de vários ou dispositivos de renderização. Cada registro na tabela representa um dispositivo.
ms.openlocfilehash: 0b3c27708cd8e9d1b02914e6f2cba414e353609c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920023"
---
# <a name="device-table"></a><span data-ttu-id="9e3a8-104">Tabela Device</span><span class="sxs-lookup"><span data-stu-id="9e3a8-104">Device table</span></span>
 
<span data-ttu-id="9e3a8-105">A tabela de dispositivo é uma tabela de suporte que armazena informações sobre a captura de vários ou dispositivos de renderização.</span><span class="sxs-lookup"><span data-stu-id="9e3a8-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="9e3a8-106">Cada registro na tabela representa um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9e3a8-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="9e3a8-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9e3a8-107">**Column**</span></span>|<span data-ttu-id="9e3a8-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9e3a8-108">**Data Type**</span></span>|<span data-ttu-id="9e3a8-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="9e3a8-109">**Key/Index**</span></span>|<span data-ttu-id="9e3a8-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="9e3a8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9e3a8-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="9e3a8-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="9e3a8-112">int</span><span class="sxs-lookup"><span data-stu-id="9e3a8-112">int</span></span>  <br/> |<span data-ttu-id="9e3a8-113">Primária</span><span class="sxs-lookup"><span data-stu-id="9e3a8-113">Primary</span></span>  <br/> |<span data-ttu-id="9e3a8-114">Número exclusivo que identifica este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9e3a8-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="9e3a8-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="9e3a8-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="9e3a8-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9e3a8-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9e3a8-117">DeviceName + DeviceType é exclusivo</span><span class="sxs-lookup"><span data-stu-id="9e3a8-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="9e3a8-118">Nome do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9e3a8-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="9e3a8-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="9e3a8-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="9e3a8-120">bit</span><span class="sxs-lookup"><span data-stu-id="9e3a8-120">bit</span></span>  <br/> |<span data-ttu-id="9e3a8-121">DeviceName + DeviceType é exclusivo</span><span class="sxs-lookup"><span data-stu-id="9e3a8-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="9e3a8-122">Tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9e3a8-122">Device type.</span></span> <span data-ttu-id="9e3a8-123">1 é um dispositivo de captura, 0 é um dispositivo de renderização.</span><span class="sxs-lookup"><span data-stu-id="9e3a8-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

