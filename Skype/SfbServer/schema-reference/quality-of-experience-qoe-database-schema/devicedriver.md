---
title: Tabela DeviceDriver
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: A tabela DeviceDriver é uma tabela de suporte. Cada registro representa um driver usado por um dispositivo de captura ou dispositivo de renderização.
ms.openlocfilehash: 1f83bfd014fa5fb49f4d0f900e01aeecfe2b5f46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823071"
---
# <a name="devicedriver-table"></a><span data-ttu-id="e2f74-104">Tabela DeviceDriver</span><span class="sxs-lookup"><span data-stu-id="e2f74-104">DeviceDriver table</span></span>
 
<span data-ttu-id="e2f74-105">A tabela DeviceDriver é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="e2f74-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="e2f74-106">Cada registro representa um driver usado por um dispositivo de captura ou dispositivo de renderização.</span><span class="sxs-lookup"><span data-stu-id="e2f74-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="e2f74-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e2f74-107">**Column**</span></span>|<span data-ttu-id="e2f74-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e2f74-108">**Data Type**</span></span>|<span data-ttu-id="e2f74-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="e2f74-109">**Key/Index**</span></span>|<span data-ttu-id="e2f74-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="e2f74-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e2f74-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="e2f74-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="e2f74-112">int</span><span class="sxs-lookup"><span data-stu-id="e2f74-112">int</span></span>  <br/> |<span data-ttu-id="e2f74-113">Primário</span><span class="sxs-lookup"><span data-stu-id="e2f74-113">Primary</span></span>  <br/> |<span data-ttu-id="e2f74-114">Número exclusivo que identifica esse registro de driver de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e2f74-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="e2f74-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="e2f74-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="e2f74-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="e2f74-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="e2f74-117">unique</span><span class="sxs-lookup"><span data-stu-id="e2f74-117">unique</span></span>  <br/> |<span data-ttu-id="e2f74-118">Nome do driver do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e2f74-118">Device driver name.</span></span>  <br/> |
   

