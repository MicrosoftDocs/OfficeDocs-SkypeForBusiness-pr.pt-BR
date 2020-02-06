---
title: Tabela Device
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: A tabela de dispositivos é uma tabela de suporte que armazena informações sobre os vários dispositivos de captura ou renderização. Cada registro na tabela representa um dispositivo.
ms.openlocfilehash: 93e6b2215fa1e20b930d678c45f10e26feffd351
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810149"
---
# <a name="device-table"></a><span data-ttu-id="96e0b-104">Tabela Device</span><span class="sxs-lookup"><span data-stu-id="96e0b-104">Device table</span></span>
 
<span data-ttu-id="96e0b-105">A tabela de dispositivos é uma tabela de suporte que armazena informações sobre os vários dispositivos de captura ou renderização.</span><span class="sxs-lookup"><span data-stu-id="96e0b-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="96e0b-106">Cada registro na tabela representa um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="96e0b-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="96e0b-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="96e0b-107">**Column**</span></span>|<span data-ttu-id="96e0b-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="96e0b-108">**Data Type**</span></span>|<span data-ttu-id="96e0b-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="96e0b-109">**Key/Index**</span></span>|<span data-ttu-id="96e0b-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="96e0b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="96e0b-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="96e0b-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="96e0b-112">int</span><span class="sxs-lookup"><span data-stu-id="96e0b-112">int</span></span>  <br/> |<span data-ttu-id="96e0b-113">Primária</span><span class="sxs-lookup"><span data-stu-id="96e0b-113">Primary</span></span>  <br/> |<span data-ttu-id="96e0b-114">Número exclusivo que identifica este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="96e0b-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="96e0b-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="96e0b-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="96e0b-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="96e0b-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="96e0b-117">DeviceName + DeviceType é exclusivo</span><span class="sxs-lookup"><span data-stu-id="96e0b-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="96e0b-118">Nome do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="96e0b-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="96e0b-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="96e0b-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="96e0b-120">bit</span><span class="sxs-lookup"><span data-stu-id="96e0b-120">bit</span></span>  <br/> |<span data-ttu-id="96e0b-121">DeviceName + DeviceType é exclusivo</span><span class="sxs-lookup"><span data-stu-id="96e0b-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="96e0b-122">Tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="96e0b-122">Device type.</span></span> <span data-ttu-id="96e0b-123">1 é um dispositivo de captura; 0 é um dispositivo de renderização.</span><span class="sxs-lookup"><span data-stu-id="96e0b-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

