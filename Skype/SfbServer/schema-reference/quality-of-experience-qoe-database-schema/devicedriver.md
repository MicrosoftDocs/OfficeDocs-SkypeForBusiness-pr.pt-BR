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
localization_priority: Normal
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: A tabela DeviceDriver é uma tabela de suporte. Cada registro representa um driver usado por um dispositivo de captura ou um dispositivo de renderização.
ms.openlocfilehash: 6a58bba9edcb0351c929c1406dcbc1ebaedec364
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294975"
---
# <a name="devicedriver-table"></a><span data-ttu-id="dc237-104">Tabela DeviceDriver</span><span class="sxs-lookup"><span data-stu-id="dc237-104">DeviceDriver table</span></span>
 
<span data-ttu-id="dc237-105">A tabela DeviceDriver é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="dc237-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="dc237-106">Cada registro representa um driver usado por um dispositivo de captura ou um dispositivo de renderização.</span><span class="sxs-lookup"><span data-stu-id="dc237-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="dc237-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="dc237-107">**Column**</span></span>|<span data-ttu-id="dc237-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="dc237-108">**Data Type**</span></span>|<span data-ttu-id="dc237-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="dc237-109">**Key/Index**</span></span>|<span data-ttu-id="dc237-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="dc237-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dc237-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="dc237-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="dc237-112">int</span><span class="sxs-lookup"><span data-stu-id="dc237-112">int</span></span>  <br/> |<span data-ttu-id="dc237-113">Primária</span><span class="sxs-lookup"><span data-stu-id="dc237-113">Primary</span></span>  <br/> |<span data-ttu-id="dc237-114">Número exclusivo que identifica este registro de driver de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc237-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="dc237-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="dc237-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="dc237-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="dc237-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="dc237-117">exclusividade</span><span class="sxs-lookup"><span data-stu-id="dc237-117">unique</span></span>  <br/> |<span data-ttu-id="dc237-118">Nome do driver do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc237-118">Device driver name.</span></span>  <br/> |
   

