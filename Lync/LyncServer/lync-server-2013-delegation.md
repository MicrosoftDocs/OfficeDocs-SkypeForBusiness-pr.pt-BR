---
title: 'Lync Server 2013: Delegação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegation
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994045(v=OCS.15)
ms:contentKeyID: 51803956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 360223733f003c30d63ef0145fa04c51503d510d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delegation-in-lync-server-2013"></a><span data-ttu-id="4374e-102">Delegação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4374e-102">Delegation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4374e-103">_**Última modificação do tópico:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="4374e-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="4374e-104">Os recursos de delegação no Lync são afetados pelo roteamento baseado em local da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4374e-104">The delegation capabilities in Lync are affected by Location-Based Routing in the following manner:</span></span>

  - <span data-ttu-id="4374e-105">Quando um representante habilitado para roteamento baseado em local coloca uma chamada em nome de um gerente, a política de voz do representante é usada para autorizar a chamada e a política de roteamento de voz do site do representante será usada para encaminhar a chamada</span><span class="sxs-lookup"><span data-stu-id="4374e-105">When a delegate enabled for Location-Based Routing places a call on behalf of a manager, the delegate’s voice policy is used to authorize the call and the delegate’s site voice routing policy will be used to route the call</span></span>

  - <span data-ttu-id="4374e-106">Para chamadas PSTN de entrada para um gerente, as mesmas regras aplicáveis ao encaminhamento de chamadas ou ao toque simultâneo serão aplicadas conforme descrito nos tópicos de transferências de chamada e de encaminhamento e toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="4374e-106">For incoming PSTN calls to a manager, the same rules applicable for call forwarding or simultaneously ringing will apply as described in the Call transfers and forwarding and Simultaneous ringing topics.</span></span>

  - <span data-ttu-id="4374e-107">Quando um representante define um ponto de extremidade PSTN como um alvo de anel simultâneo, para uma chamada de entrada para o gerente, a política de roteamento de voz do site que está associado ao tronco de entrada será usada para rotear a chamada para o ponto de extremidade PSTN do representante.</span><span class="sxs-lookup"><span data-stu-id="4374e-107">When a delegate sets a PSTN endpoint as a simultaneous ring target, for an incoming call to the manager, the voice routing policy of the site that is associated to the incoming trunk will be used to route the call to the delegate’s PSTN endpoint.</span></span>

  - <span data-ttu-id="4374e-108">Para delegação, é recomendável que o gerente e seus representantes associados estejam geralmente localizados no mesmo local de rede.</span><span class="sxs-lookup"><span data-stu-id="4374e-108">For delegation, it’s recommended that the manager and his associated delegates to be usually located in the same network site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4374e-109">Confira também</span><span class="sxs-lookup"><span data-stu-id="4374e-109">See Also</span></span>


[<span data-ttu-id="4374e-110">Cenários para roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4374e-110">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

