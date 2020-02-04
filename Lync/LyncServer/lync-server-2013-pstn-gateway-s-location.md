---
title: 'Lync Server 2013: Local do gateway PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5d15589f37b18015f91e3717e19415d5ade6b6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="559fb-102">Local do gateway PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="559fb-102">PSTN gateway's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="559fb-103">_**Tópico da última modificação:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="559fb-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="559fb-104">Chamadas roteadas por meio de gateways PSTN e PBXs podem exigir restrições de roteamento baseado em localização, dependendo do local de tais sistemas.</span><span class="sxs-lookup"><span data-stu-id="559fb-104">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="559fb-105">O roteamento baseado em localização pode ser habilitado na granularidade com base em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="559fb-105">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="559fb-106">O roteamento baseado em local introduz o seguinte conjunto de regras quando habilitado em um tronco:</span><span class="sxs-lookup"><span data-stu-id="559fb-106">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="559fb-107">Quando o roteamento baseado em localização estiver habilitado em uma base por tronco, as regras definidas nesse tronco serão aplicadas somente a chamadas roteadas por meio desse tronco.</span><span class="sxs-lookup"><span data-stu-id="559fb-107">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="559fb-108">Para evitar que as tarifas PSTNs ignorem onde as chamadas são originadas de um site de rede diferente que o site de rede onde o gateway PSTN está localizado, o roteamento baseado em local introduz a associação de um site de rede a um determinado tronco.</span><span class="sxs-lookup"><span data-stu-id="559fb-108">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="559fb-109">Isso definirá o local de rede que permite o encaminhamento de chamadas para um tronco específico.</span><span class="sxs-lookup"><span data-stu-id="559fb-109">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="559fb-110">Os troncos podem ser habilitados para roteamento baseado em local de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="559fb-110">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="559fb-p103">O tronco é definido para um gateway PSTN que egressa chamadas para a PSTN. As chamadas de entrada encaminhadas por um tronco desse tipo serão encaminhadas apenas para os pontos de extremidade localizados dentro do mesmo local de rede do tronco.</span><span class="sxs-lookup"><span data-stu-id="559fb-p103">The trunk is defined for a PSTN gateway that egresses calls to the PSTN. Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="559fb-113">O tronco é definido para um peer do servidor de mediação que não faz chamadas para os usuários de serviços PSTN e PSTN com telefones herdados em locais estáticos (por exemplo, telefones PBX).</span><span class="sxs-lookup"><span data-stu-id="559fb-113">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="559fb-114">Para essa configuração específica, todas as chamadas de entrada encaminhadas por um tronco desse tipo serão consideradas como originadas do mesmo local de rede do tronco.</span><span class="sxs-lookup"><span data-stu-id="559fb-114">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="559fb-115">As chamadas de usuários do PBX terão a mesma imposição de roteamento com base no local que os usuários do Lync que estão localizados no mesmo local de rede que o tronco.</span><span class="sxs-lookup"><span data-stu-id="559fb-115">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="559fb-116">Se dois sistemas PBX localizados em sites de rede separados estiverem conectados por meio do Lync Server, o roteamento baseado em local permitirá o roteamento de um ponto de extremidade de PBX em um site de rede para outro ponto de extremidade de PBX no outro site de rede.</span><span class="sxs-lookup"><span data-stu-id="559fb-116">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="559fb-117">Esse cenário não será bloqueado pelo roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="559fb-117">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="559fb-118">Além desse cenário e, de forma semelhante, como um usuário do Lync no mesmo local, os pontos de extremidade conectados a um servidor de mediação de servidor com essa configuração poderão fazer ou receber chamadas para e de outros pontos do servidor de mediação que não roteiam chamadas para o PSTN (i. e. um ponto de extremidade conectado a um PBX diferente) independentemente do site de rede ao qual o servidor de mediação está associado.</span><span class="sxs-lookup"><span data-stu-id="559fb-118">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="559fb-119">Todas as chamadas recebidas, chamadas de saída, transferências de chamadas e encaminhamentos de chamadas que envolvem pontos de extremidade PSTN estarão sujeitas ao roteamento baseado em localização para usar somente gateways PSTN definidos como locais para o peer do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="559fb-119">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="559fb-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="559fb-120">See Also</span></span>


[<span data-ttu-id="559fb-121">Orientação para Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="559fb-121">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

