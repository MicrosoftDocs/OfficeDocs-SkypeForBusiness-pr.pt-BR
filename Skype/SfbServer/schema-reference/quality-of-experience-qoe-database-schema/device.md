---
title: Tabela device
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
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: A tabela Device é uma tabela de suporte que armazena informações sobre os vários dispositivos de captura ou renderização. Cada registro na tabela representa um dispositivo.
ms.openlocfilehash: 818458e41c71398f3df11ac9a47eeee0841c6dca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814741"
---
# <a name="device-table"></a><span data-ttu-id="fad29-104">Tabela device</span><span class="sxs-lookup"><span data-stu-id="fad29-104">Device table</span></span>
 
<span data-ttu-id="fad29-p102">A tabela Device é uma tabela de suporte que armazena informações sobre os vários dispositivos de captura ou renderização. Cada registro na tabela representa um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fad29-p102">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="fad29-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="fad29-107">**Column**</span></span>|<span data-ttu-id="fad29-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="fad29-108">**Data Type**</span></span>|<span data-ttu-id="fad29-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="fad29-109">**Key/Index**</span></span>|<span data-ttu-id="fad29-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="fad29-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fad29-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="fad29-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="fad29-112">int</span><span class="sxs-lookup"><span data-stu-id="fad29-112">int</span></span>  <br/> |<span data-ttu-id="fad29-113">Primário</span><span class="sxs-lookup"><span data-stu-id="fad29-113">Primary</span></span>  <br/> |<span data-ttu-id="fad29-114">Número exclusivo que identifica este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fad29-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="fad29-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="fad29-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="fad29-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fad29-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fad29-117">DeviceName + DeviceType é exclusivo</span><span class="sxs-lookup"><span data-stu-id="fad29-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="fad29-118">Nome do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fad29-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="fad29-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="fad29-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="fad29-120">bit</span><span class="sxs-lookup"><span data-stu-id="fad29-120">bit</span></span>  <br/> |<span data-ttu-id="fad29-121">DeviceName + DeviceType é exclusivo</span><span class="sxs-lookup"><span data-stu-id="fad29-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="fad29-p103">Tipo de dispositivo. 1 é um dispositivo de captura, 0 é um dispositivo de processamento.</span><span class="sxs-lookup"><span data-stu-id="fad29-p103">Device type. 1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

