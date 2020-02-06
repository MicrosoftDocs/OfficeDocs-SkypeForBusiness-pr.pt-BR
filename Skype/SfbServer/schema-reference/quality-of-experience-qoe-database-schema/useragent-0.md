---
title: Exibição do UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: A exibição do UserAgent armazena informações sobre os agentes de usuário envolvidos em sessões que têm registros no banco de dados. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 76ac99b1fdadbeb6817b36483f4fe5762db47333
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805079"
---
# <a name="useragent-view"></a><span data-ttu-id="141dc-104">Exibição do UserAgent</span><span class="sxs-lookup"><span data-stu-id="141dc-104">UserAgent view</span></span>
 
<span data-ttu-id="141dc-105">A exibição do UserAgent armazena informações sobre os agentes de usuário envolvidos em sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="141dc-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="141dc-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="141dc-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="141dc-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="141dc-107">**Column**</span></span>|<span data-ttu-id="141dc-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="141dc-108">**Data Type**</span></span>|<span data-ttu-id="141dc-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="141dc-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="141dc-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="141dc-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="141dc-111">int</span><span class="sxs-lookup"><span data-stu-id="141dc-111">int</span></span>  <br/> |<span data-ttu-id="141dc-112">Número exclusivo que identifica esse agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="141dc-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="141dc-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="141dc-113">UserAgent</span></span>  <br/> |<span data-ttu-id="141dc-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="141dc-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="141dc-115">Cadeia de caracteres do agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="141dc-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="141dc-116">UAType</span><span class="sxs-lookup"><span data-stu-id="141dc-116">UAType</span></span>  <br/> |<span data-ttu-id="141dc-117">smallint</span><span class="sxs-lookup"><span data-stu-id="141dc-117">smallint</span></span>  <br/> |<span data-ttu-id="141dc-118">Tipo de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="141dc-118">Type of user agent.</span></span> <span data-ttu-id="141dc-119">Consulte a [tabela UserAgent](useragent.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="141dc-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="141dc-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="141dc-120">UACategory</span></span>  <br/> |<span data-ttu-id="141dc-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="141dc-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="141dc-122">Categoria à qual o agente do usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="141dc-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="141dc-123">Por exemplo, o agente do usuário Conferencing_Attendant_1 de 0 pertence à CAA UACategory.</span><span class="sxs-lookup"><span data-stu-id="141dc-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

