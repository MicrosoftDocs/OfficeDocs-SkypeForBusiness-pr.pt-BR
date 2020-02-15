---
title: 'Lync Server 2013: planejamento para roteamento baseado em local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Location-Based Routing
ms:assetid: bb035924-6b52-4f0f-8e05-b76864fb9ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994068(v=OCS.15)
ms:contentKeyID: 51803979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 307b4d696fdf4348649eb9363d252c7f1d0f8d12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="8bfe3-102">Planejamento de roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bfe3-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bfe3-103">_**Última modificação do tópico:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="8bfe3-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="8bfe3-104">As informações neste tópico pertencem às atualizações cumulativas do Lync Server 2013:2013 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="8bfe3-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="8bfe3-105">O roteamento baseado em local permite restringir o roteamento de chamadas entre pontos de extremidade VoIP e pontos de extremidade PSTN com base no local das partes na chamada.</span><span class="sxs-lookup"><span data-stu-id="8bfe3-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="8bfe3-106">O roteamento baseado em local é parte da infraestrutura do Lync Server 2013 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="8bfe3-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="8bfe3-107">O roteamento baseado em local é um recurso de gerenciamento de chamadas que controla como as chamadas são encaminhadas pelo Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="8bfe3-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="8bfe3-108">Ela impõe regras de autorização de chamadas em se as chamadas podem ser encaminhadas para pontos de extremidade PBX ou PSTN com base na localização geográfica do chamador do Lync.</span><span class="sxs-lookup"><span data-stu-id="8bfe3-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8bfe3-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="8bfe3-109">In This Section</span></span>

  - [<span data-ttu-id="8bfe3-110">Visão geral do roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bfe3-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="8bfe3-111">Orientação para roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bfe3-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="8bfe3-112">Cenários para roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bfe3-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="8bfe3-113">Considerações técnicas para roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bfe3-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="8bfe3-114">Suporte a cliente e servidor para roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bfe3-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="8bfe3-115">Recursos não suportados pelo roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bfe3-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="8bfe3-116">Processo de implantação para roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bfe3-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="8bfe3-117">Roteamento baseado em local para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bfe3-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8bfe3-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="8bfe3-118">See Also</span></span>


[<span data-ttu-id="8bfe3-119">Planejamento para o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bfe3-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

