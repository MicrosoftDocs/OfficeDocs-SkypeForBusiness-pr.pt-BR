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
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: A exibição do UserAgent armazena informações sobre os agentes de usuário envolvidos em sessões que têm registros no banco de dados. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294604"
---
# <a name="useragent-view"></a><span data-ttu-id="04075-104">Exibição do UserAgent</span><span class="sxs-lookup"><span data-stu-id="04075-104">UserAgent view</span></span>
 
<span data-ttu-id="04075-105">A exibição do UserAgent armazena informações sobre os agentes de usuário envolvidos em sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="04075-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="04075-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="04075-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="04075-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="04075-107">**Column**</span></span>|<span data-ttu-id="04075-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="04075-108">**Data Type**</span></span>|<span data-ttu-id="04075-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="04075-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="04075-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="04075-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="04075-111">int</span><span class="sxs-lookup"><span data-stu-id="04075-111">int</span></span>  <br/> |<span data-ttu-id="04075-112">Número exclusivo que identifica esse agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="04075-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="04075-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="04075-113">UserAgent</span></span>  <br/> |<span data-ttu-id="04075-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="04075-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="04075-115">Cadeia de caracteres do agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="04075-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="04075-116">UAType</span><span class="sxs-lookup"><span data-stu-id="04075-116">UAType</span></span>  <br/> |<span data-ttu-id="04075-117">smallint</span><span class="sxs-lookup"><span data-stu-id="04075-117">smallint</span></span>  <br/> |<span data-ttu-id="04075-118">Tipo de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="04075-118">Type of user agent.</span></span> <span data-ttu-id="04075-119">Consulte a [tabela UserAgent](useragent.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="04075-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="04075-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="04075-120">UACategory</span></span>  <br/> |<span data-ttu-id="04075-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="04075-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="04075-122">Categoria à qual o agente do usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="04075-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="04075-123">Por exemplo, o agente de usuário Conferencing_Attendant_ 1.0 pertence ao UACategory CAA.</span><span class="sxs-lookup"><span data-stu-id="04075-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

