---
title: Tabela DeviceDriver
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: A tabela DeviceDriver é uma tabela de suporte. Cada registro representa um driver usado por qualquer um dispositivo de captura ou dispositivo de renderização.
ms.openlocfilehash: d5882ba853bd4909863fc5da415c993d4b59ea4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="devicedriver-table"></a><span data-ttu-id="1ef78-104">Tabela DeviceDriver</span><span class="sxs-lookup"><span data-stu-id="1ef78-104">DeviceDriver table</span></span>
 
<span data-ttu-id="1ef78-105">A tabela DeviceDriver é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="1ef78-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="1ef78-106">Cada registro representa um driver usado por qualquer um dispositivo de captura ou dispositivo de renderização.</span><span class="sxs-lookup"><span data-stu-id="1ef78-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="1ef78-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="1ef78-107">**Column**</span></span>|<span data-ttu-id="1ef78-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="1ef78-108">**Data Type**</span></span>|<span data-ttu-id="1ef78-109">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="1ef78-109">**Key/Index**</span></span>|<span data-ttu-id="1ef78-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="1ef78-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1ef78-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="1ef78-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="1ef78-112">int</span><span class="sxs-lookup"><span data-stu-id="1ef78-112">int</span></span>  <br/> |<span data-ttu-id="1ef78-113">Primária</span><span class="sxs-lookup"><span data-stu-id="1ef78-113">Primary</span></span>  <br/> |<span data-ttu-id="1ef78-114">Número exclusivo que identifica este registro de driver de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1ef78-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="1ef78-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="1ef78-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="1ef78-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="1ef78-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="1ef78-117">exclusivo</span><span class="sxs-lookup"><span data-stu-id="1ef78-117">unique</span></span>  <br/> |<span data-ttu-id="1ef78-118">Nome do driver do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1ef78-118">Device driver name.</span></span>  <br/> |
   

