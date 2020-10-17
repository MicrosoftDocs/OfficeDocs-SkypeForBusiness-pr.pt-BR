---
title: 'Lync Server 2013: visão geral do roteamento de Location-Based'
description: 'Lync Server 2013: visão geral do roteamento de Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b1e026791a8562629231b91b58d7e7eff569ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562807"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="42404-103">Visão geral do roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42404-103">Overview of Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42404-104">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="42404-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="42404-105">O roteamento de Location-Based introduz um novo conjunto de regras que modifica o roteamento de chamadas PSTN nacionais e internacionais para impedir o desvio de chamada.</span><span class="sxs-lookup"><span data-stu-id="42404-105">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="42404-106">Location-Based roteamento fornece a flexibilidade para definir o escopo dessas regras para regiões específicas, gateways específicos ou apenas para o conjunto específico de usuários.</span><span class="sxs-lookup"><span data-stu-id="42404-106">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="42404-107">Os cenários a seguir ilustram os principais tipos de restrições Location-Based o roteamento pode impor:</span><span class="sxs-lookup"><span data-stu-id="42404-107">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="42404-108">Chamadas de egresso – o roteamento Location-Based pode impor chamadas de saída para saída de um gateway PSTN localizado na mesma região em que o chamador deve impedir o bypass de chamada PSTN, o que impede chamadas de saída de um gateway PSTN localizado em uma região diferente como o chamador.</span><span class="sxs-lookup"><span data-stu-id="42404-108">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="42404-109">Chamadas de ingresso – Location-Based roteamento pode impedir chamadas PSTN de entrada para apontar pontos de extremidade do Lync se o gateway PSTN que está encaminhando a chamada de entrada não está localizado na mesma região que o usuário chamado do Lync.</span><span class="sxs-lookup"><span data-stu-id="42404-109">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="42404-110">Regiões desconhecidas – Location-Based roteamento restringe as chamadas PSTN de entrada e saída para e de usuários localizados em locais indeterminados (ou seja, usuários remotos que se conectam a partir da Internet ou localizados em regiões desconhecidas).</span><span class="sxs-lookup"><span data-stu-id="42404-110">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="42404-111">Regiões internacionais – Location-Based roteamento aplica o roteamento de chamadas de saída por meio de gateways PSTN internacionais se não for possível encontrar um gateway local para o local do usuário.</span><span class="sxs-lookup"><span data-stu-id="42404-111">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="42404-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="42404-112">See Also</span></span>


[<span data-ttu-id="42404-113">Planejamento de roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42404-113">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

