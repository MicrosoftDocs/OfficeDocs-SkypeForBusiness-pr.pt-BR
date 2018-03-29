---
title: Exibir UserAgent
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
ms.openlocfilehash: 8df1d45ed1272a886a440aded79a9c4e04c1bae8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="useragent-view"></a><span data-ttu-id="82cf1-104">Exibir UserAgent</span><span class="sxs-lookup"><span data-stu-id="82cf1-104">UserAgent view</span></span>
 
<span data-ttu-id="82cf1-105">O modo de exibição UserAgent armazena informações sobre os agentes de usuário que participaram de sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="82cf1-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="82cf1-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82cf1-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="82cf1-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="82cf1-107">**Column**</span></span>|<span data-ttu-id="82cf1-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="82cf1-108">**Data Type**</span></span>|<span data-ttu-id="82cf1-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="82cf1-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="82cf1-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="82cf1-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="82cf1-111">int</span><span class="sxs-lookup"><span data-stu-id="82cf1-111">int</span></span>  <br/> |<span data-ttu-id="82cf1-112">Número exclusivo que identifica esse agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="82cf1-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="82cf1-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="82cf1-113">UserAgent</span></span>  <br/> |<span data-ttu-id="82cf1-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="82cf1-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="82cf1-115">Cadeia de caracteres de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="82cf1-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="82cf1-116">UAType</span><span class="sxs-lookup"><span data-stu-id="82cf1-116">UAType</span></span>  <br/> |<span data-ttu-id="82cf1-117">smallint</span><span class="sxs-lookup"><span data-stu-id="82cf1-117">smallint</span></span>  <br/> |<span data-ttu-id="82cf1-118">Tipo de agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="82cf1-118">Type of user agent.</span></span> <span data-ttu-id="82cf1-119">Consulte a [tabela UserAgent](useragent.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="82cf1-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="82cf1-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="82cf1-120">UACategory</span></span>  <br/> |<span data-ttu-id="82cf1-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="82cf1-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="82cf1-122">Categoria à qual pertence o agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="82cf1-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="82cf1-123">Por exemplo, o agente do usuário Conferencing_Attendant_1.0 pertence o CAA UACategory.</span><span class="sxs-lookup"><span data-stu-id="82cf1-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

