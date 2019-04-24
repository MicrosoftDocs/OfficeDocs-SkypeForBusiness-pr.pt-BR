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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212064"
---
# <a name="useragent-view"></a><span data-ttu-id="b7dae-104">Exibir UserAgent</span><span class="sxs-lookup"><span data-stu-id="b7dae-104">UserAgent view</span></span>
 
<span data-ttu-id="b7dae-105">O modo de exibição UserAgent armazena informações sobre os agentes de usuário que participaram de sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b7dae-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="b7dae-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7dae-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b7dae-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b7dae-107">**Column**</span></span>|<span data-ttu-id="b7dae-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dae-108">**Data Type**</span></span>|<span data-ttu-id="b7dae-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="b7dae-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7dae-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="b7dae-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="b7dae-111">int</span><span class="sxs-lookup"><span data-stu-id="b7dae-111">int</span></span>  <br/> |<span data-ttu-id="b7dae-112">Número exclusivo que identifica esse agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="b7dae-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="b7dae-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="b7dae-113">UserAgent</span></span>  <br/> |<span data-ttu-id="b7dae-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b7dae-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b7dae-115">Cadeia de caracteres de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="b7dae-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="b7dae-116">UAType</span><span class="sxs-lookup"><span data-stu-id="b7dae-116">UAType</span></span>  <br/> |<span data-ttu-id="b7dae-117">smallint</span><span class="sxs-lookup"><span data-stu-id="b7dae-117">smallint</span></span>  <br/> |<span data-ttu-id="b7dae-118">Tipo de agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="b7dae-118">Type of user agent.</span></span> <span data-ttu-id="b7dae-119">Consulte a [tabela UserAgent](useragent.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="b7dae-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="b7dae-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="b7dae-120">UACategory</span></span>  <br/> |<span data-ttu-id="b7dae-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="b7dae-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="b7dae-122">Categoria à qual pertence o agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="b7dae-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="b7dae-123">Por exemplo, o agente do usuário Conferencing_Attendant_1.0 pertence o CAA UACategory.</span><span class="sxs-lookup"><span data-stu-id="b7dae-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

