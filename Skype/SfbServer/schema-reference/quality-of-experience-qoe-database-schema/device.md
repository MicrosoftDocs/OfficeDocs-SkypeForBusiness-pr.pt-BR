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
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: A tabela de dispositivos é uma tabela de suporte que armazena informações sobre os vários dispositivos de captura ou renderização. Cada registro na tabela representa um dispositivo.
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295003"
---
# <a name="device-table"></a><span data-ttu-id="28042-104">Tabela Device</span><span class="sxs-lookup"><span data-stu-id="28042-104">Device table</span></span>
 
<span data-ttu-id="28042-105">A tabela de dispositivos é uma tabela de suporte que armazena informações sobre os vários dispositivos de captura ou renderização.</span><span class="sxs-lookup"><span data-stu-id="28042-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="28042-106">Cada registro na tabela representa um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28042-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="28042-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="28042-107">**Column**</span></span>|<span data-ttu-id="28042-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="28042-108">**Data Type**</span></span>|<span data-ttu-id="28042-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="28042-109">**Key/Index**</span></span>|<span data-ttu-id="28042-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="28042-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="28042-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="28042-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="28042-112">int</span><span class="sxs-lookup"><span data-stu-id="28042-112">int</span></span>  <br/> |<span data-ttu-id="28042-113">Primária</span><span class="sxs-lookup"><span data-stu-id="28042-113">Primary</span></span>  <br/> |<span data-ttu-id="28042-114">Número exclusivo que identifica este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28042-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="28042-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="28042-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="28042-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="28042-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="28042-117">DeviceName + DeviceType é exclusivo</span><span class="sxs-lookup"><span data-stu-id="28042-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="28042-118">Nome do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28042-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="28042-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="28042-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="28042-120">bit</span><span class="sxs-lookup"><span data-stu-id="28042-120">bit</span></span>  <br/> |<span data-ttu-id="28042-121">DeviceName + DeviceType é exclusivo</span><span class="sxs-lookup"><span data-stu-id="28042-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="28042-122">Tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="28042-122">Device type.</span></span> <span data-ttu-id="28042-123">1 é um dispositivo de captura; 0 é um dispositivo de renderização.</span><span class="sxs-lookup"><span data-stu-id="28042-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

