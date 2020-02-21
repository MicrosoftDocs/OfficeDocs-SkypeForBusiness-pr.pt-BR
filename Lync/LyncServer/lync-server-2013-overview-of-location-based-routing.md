---
title: 'Lync Server 2013: visão geral do roteamento baseado em local'
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
ms.openlocfilehash: 85d24aeb94a0c16e93d885c5b6db20385cdf0f26
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="dff18-102">Visão geral do roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dff18-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dff18-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="dff18-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="dff18-104">O roteamento baseado em local introduz um novo conjunto de regras que modifica o roteamento de chamadas PSTN nacionais e internacionais para evitar o desvio de chamada.</span><span class="sxs-lookup"><span data-stu-id="dff18-104">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="dff18-105">O roteamento baseado em local oferece a flexibilidade para definir o escopo dessas regras para regiões específicas, gateways específicos ou apenas para o conjunto específico de usuários.</span><span class="sxs-lookup"><span data-stu-id="dff18-105">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="dff18-106">Os cenários a seguir ilustram os principais tipos de restrições que o roteamento baseado em local pode impor:</span><span class="sxs-lookup"><span data-stu-id="dff18-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="dff18-107">Chamadas de egresso – o roteamento baseado em local pode impor chamadas de saída para saída de um gateway PSTN localizado na mesma região em que o chamador deve impedir o bypass de interrupções PSTN, o que impede chamadas de saída de um gateway PSTN localizado em uma região diferente como pelas.</span><span class="sxs-lookup"><span data-stu-id="dff18-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="dff18-108">Chamadas de ingresso – o roteamento baseado em local pode impedir chamadas PSTN de entrada para apontar pontos de extremidade do Lync, se o gateway PSTN que estiver encaminhando a chamada de entrada não estiver localizado na mesma região do usuário chamado Lync.</span><span class="sxs-lookup"><span data-stu-id="dff18-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="dff18-109">Regiões desconhecidas – o roteamento baseado em local restringe as chamadas PSTN de entrada e saída para e de usuários localizados em locais indeterminados (ou seja, usuários remotos que se conectam a partir da Internet ou localizados em regiões desconhecidas).</span><span class="sxs-lookup"><span data-stu-id="dff18-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="dff18-110">Regiões internacionais – o roteamento baseado em local impõe o roteamento de chamadas de saída por meio de gateways PSTN internacionais se não for possível encontrar um gateway local para o local do usuário.</span><span class="sxs-lookup"><span data-stu-id="dff18-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="dff18-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="dff18-111">See Also</span></span>


[<span data-ttu-id="dff18-112">Planejamento de roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dff18-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

