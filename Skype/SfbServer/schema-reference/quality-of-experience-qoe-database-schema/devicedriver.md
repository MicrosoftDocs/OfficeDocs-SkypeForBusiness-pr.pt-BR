---
title: Tabela DeviceDriver
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: A tabela DeviceDriver é uma tabela de suporte. Cada registro representa um driver usado por um dispositivo de captura ou um dispositivo de renderização.
ms.openlocfilehash: 8a502a1fc07c3541522931554064f7708b3e6187
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809709"
---
# <a name="devicedriver-table"></a><span data-ttu-id="2195e-104">Tabela DeviceDriver</span><span class="sxs-lookup"><span data-stu-id="2195e-104">DeviceDriver table</span></span>
 
<span data-ttu-id="2195e-105">A tabela DeviceDriver é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="2195e-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="2195e-106">Cada registro representa um driver usado por um dispositivo de captura ou um dispositivo de renderização.</span><span class="sxs-lookup"><span data-stu-id="2195e-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="2195e-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2195e-107">**Column**</span></span>|<span data-ttu-id="2195e-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="2195e-108">**Data Type**</span></span>|<span data-ttu-id="2195e-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="2195e-109">**Key/Index**</span></span>|<span data-ttu-id="2195e-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="2195e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2195e-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="2195e-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="2195e-112">int</span><span class="sxs-lookup"><span data-stu-id="2195e-112">int</span></span>  <br/> |<span data-ttu-id="2195e-113">Primária</span><span class="sxs-lookup"><span data-stu-id="2195e-113">Primary</span></span>  <br/> |<span data-ttu-id="2195e-114">Número exclusivo que identifica este registro de driver de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2195e-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="2195e-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="2195e-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="2195e-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="2195e-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="2195e-117">exclusividade</span><span class="sxs-lookup"><span data-stu-id="2195e-117">unique</span></span>  <br/> |<span data-ttu-id="2195e-118">Nome do driver do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2195e-118">Device driver name.</span></span>  <br/> |
   

