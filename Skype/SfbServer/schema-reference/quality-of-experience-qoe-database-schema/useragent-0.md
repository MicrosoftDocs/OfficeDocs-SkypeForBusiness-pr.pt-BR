---
title: Exibir UserAgent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: O modo de exibição UserAgent armazena informações sobre os agentes de usuário que participaram de sessões que têm registros no banco de dados. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: c63873f219f5d741925339f52f949be55fc64411
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875001"
---
# <a name="useragent-view"></a><span data-ttu-id="484a6-104">Exibir UserAgent</span><span class="sxs-lookup"><span data-stu-id="484a6-104">UserAgent view</span></span>
 
<span data-ttu-id="484a6-105">O modo de exibição UserAgent armazena informações sobre os agentes de usuário que participaram de sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="484a6-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="484a6-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="484a6-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="484a6-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="484a6-107">**Column**</span></span>|<span data-ttu-id="484a6-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="484a6-108">**Data Type**</span></span>|<span data-ttu-id="484a6-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="484a6-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="484a6-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="484a6-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="484a6-111">int</span><span class="sxs-lookup"><span data-stu-id="484a6-111">int</span></span>  <br/> |<span data-ttu-id="484a6-112">Número exclusivo que identifica esse agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="484a6-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="484a6-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="484a6-113">UserAgent</span></span>  <br/> |<span data-ttu-id="484a6-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="484a6-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="484a6-115">Cadeia de caracteres de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="484a6-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="484a6-116">UAType</span><span class="sxs-lookup"><span data-stu-id="484a6-116">UAType</span></span>  <br/> |<span data-ttu-id="484a6-117">smallint</span><span class="sxs-lookup"><span data-stu-id="484a6-117">smallint</span></span>  <br/> |<span data-ttu-id="484a6-118">Tipo de agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="484a6-118">Type of user agent.</span></span> <span data-ttu-id="484a6-119">Consulte a [tabela UserAgent](useragent.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="484a6-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="484a6-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="484a6-120">UACategory</span></span>  <br/> |<span data-ttu-id="484a6-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="484a6-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="484a6-122">Categoria à qual pertence o agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="484a6-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="484a6-123">Por exemplo, o agente do usuário Conferencing_Attendant_1.0 pertence o CAA UACategory.</span><span class="sxs-lookup"><span data-stu-id="484a6-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

