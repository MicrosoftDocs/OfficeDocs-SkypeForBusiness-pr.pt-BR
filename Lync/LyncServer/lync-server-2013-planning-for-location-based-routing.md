---
title: 'Lync Server 2013: planejamento para roteamento de Location-Based'
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
ms.openlocfilehash: 114f92d0963e8d61c4b0854862ff7ebd59a12b64
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522038"
---
# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="dec6e-102">Planejamento de roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dec6e-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dec6e-103">_**Última modificação do tópico:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="dec6e-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="dec6e-104">As informações neste tópico pertencem às atualizações cumulativas do Lync Server 2013:2013 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="dec6e-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="dec6e-105">Location-Based roteamento permite restringir o roteamento de chamadas entre pontos de extremidade VoIP e pontos de extremidade PSTN com base no local das partes na chamada.</span><span class="sxs-lookup"><span data-stu-id="dec6e-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="dec6e-106">Location-Based roteamento faz parte da infraestrutura do Lync Server 2013 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="dec6e-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="dec6e-107">Location-Based roteamento é um recurso de gerenciamento de chamadas que controla como as chamadas são encaminhadas pelo Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="dec6e-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="dec6e-108">Ela impõe regras de autorização de chamadas em se as chamadas podem ser encaminhadas para pontos de extremidade PBX ou PSTN com base na localização geográfica do chamador do Lync.</span><span class="sxs-lookup"><span data-stu-id="dec6e-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dec6e-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="dec6e-109">In This Section</span></span>

  - [<span data-ttu-id="dec6e-110">Visão geral do roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dec6e-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="dec6e-111">Orientações para Location-Based roteamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dec6e-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="dec6e-112">Cenários para Location-Based roteamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dec6e-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="dec6e-113">Considerações técnicas para roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dec6e-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="dec6e-114">Suporte a cliente e servidor para roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dec6e-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="dec6e-115">Recursos não suportados pelo roteamento Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dec6e-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="dec6e-116">Processo de implantação para roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dec6e-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="dec6e-117">Roteamento baseado em local para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dec6e-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dec6e-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="dec6e-118">See Also</span></span>


[<span data-ttu-id="dec6e-119">Planejamento para o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dec6e-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

