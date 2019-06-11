---
title: 'Lync Server 2013: Planejamento de Roteamento Baseado em Local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Location-Based Routing
ms:assetid: bb035924-6b52-4f0f-8e05-b76864fb9ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994068(v=OCS.15)
ms:contentKeyID: 51803979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3873e8710d6ab70212de7780ef5f34d1436df1d2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="35e49-102">Planejamento de Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35e49-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35e49-103">_**Tópico da última modificação:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="35e49-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="35e49-104">A informação neste tópico está relacionada às Atualizações Cumulativas para Lync Server 2013: Fevereiro de 2013.</span><span class="sxs-lookup"><span data-stu-id="35e49-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="35e49-105">O roteamento baseado em local torna possível restringir o roteamento de chamadas entre pontos de extremidade VoIP e pontos de extremidade PSTN com base no local das partes na chamada.</span><span class="sxs-lookup"><span data-stu-id="35e49-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="35e49-106">O roteamento baseado em local faz parte da infraestrutura do Lync Server 2013 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="35e49-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="35e49-107">Roteamento baseado em local é um recurso de gerenciamento de chamadas que controla como as chamadas são roteadas pelo Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="35e49-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="35e49-108">Ele impõe regras de autorização de chamadas se as chamadas podem ser roteadas para os pontos de extremidade PBX ou PSTN com base na localização geográfica do chamador do Lync.</span><span class="sxs-lookup"><span data-stu-id="35e49-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="35e49-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="35e49-109">In This Section</span></span>

  - [<span data-ttu-id="35e49-110">Visão geral do roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35e49-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="35e49-111">Orientação para Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35e49-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="35e49-112">Cenários para Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35e49-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="35e49-113">Considerações técnicas para Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35e49-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="35e49-114">Suporte a cliente e servidor para Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35e49-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="35e49-115">Recursos não suportados pelo Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35e49-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="35e49-116">Processo de implantação para Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35e49-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="35e49-117">Roteamento baseado em local para conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35e49-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35e49-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="35e49-118">See Also</span></span>


[<span data-ttu-id="35e49-119">Planejando para Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35e49-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

