---
title: 'Lync Server 2013: local do usuário'
description: 'Lync Server 2013: local do usuário.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a92ec780809cdb3e1ee582ce6c348c884bbb5890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561207"
---
# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="79cdf-103">Local do usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79cdf-103">User's location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79cdf-104">_**Última modificação do tópico:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="79cdf-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="79cdf-105">Location-Based roteamento aproveita as mesmas regiões de rede, sites e sub-redes, conforme definido no Lync Server usado pelo E9-1-1, CAC e bypass de mídia para aplicar restrições de roteamento de chamadas para evitar o bypass de chamada PSTN.</span><span class="sxs-lookup"><span data-stu-id="79cdf-105">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="79cdf-106">O local de um usuário é determinado pela sub-rede IP dos pontos de extremidade do Lync do usuário estão conectados.</span><span class="sxs-lookup"><span data-stu-id="79cdf-106">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="79cdf-107">Cada sub-rede IP é associada a um site de rede, que é agregado às regiões de rede definidas pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="79cdf-107">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="79cdf-108">Location-Based roteamento é aplicado com base no site de rede do usuário.</span><span class="sxs-lookup"><span data-stu-id="79cdf-108">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="79cdf-109">Location-Based regras de roteamento são aplicadas por site de rede, o que significa que um determinado conjunto de regras será aplicado a todos os pontos de extremidade habilitados para Location-Based roteamento localizado dentro do mesmo local de rede.</span><span class="sxs-lookup"><span data-stu-id="79cdf-109">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="79cdf-110">Os administradores podem aplicar Location-Based roteamento a sites de rede que o exijam.</span><span class="sxs-lookup"><span data-stu-id="79cdf-110">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="79cdf-111">As políticas de roteamento de voz podem ser definidas por site de rede para definir um gateway PSTN específico que deve ser usado por todos os usuários localizados no site de rede para chamar números de telefone PSTN.</span><span class="sxs-lookup"><span data-stu-id="79cdf-111">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="79cdf-112">Essas políticas de roteamento de voz terão precedência sobre o roteamento definido pela política de voz do usuário quando o usuário estiver localizado em um site de rede habilitado para roteamento de Location-Based e impedirá o roteamento de chamadas por meio de outros gateways PSTN habilitados para roteamento Location-Based.</span><span class="sxs-lookup"><span data-stu-id="79cdf-112">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="79cdf-113">Quando um usuário do Lync coloca uma chamada PSTN, a política de voz do usuário determina se o usuário pode ser autorizado a fazer a chamada.</span><span class="sxs-lookup"><span data-stu-id="79cdf-113">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="79cdf-114">Se a política de voz do usuário permitir que o usuário faça a chamada, Location-Based roteamento determinará o gateway PSTN de saída da chamada.</span><span class="sxs-lookup"><span data-stu-id="79cdf-114">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="79cdf-115">Location-Based roteamento faz essa determinação com base no local do usuário.</span><span class="sxs-lookup"><span data-stu-id="79cdf-115">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="79cdf-116">Um local de usuário pode ser categorizado das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="79cdf-116">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="79cdf-117">O usuário está localizado em um site de rede conhecido habilitado para roteamento de Location-Based e seu número (discagem direta interna) termina em um gateway PSTN colocado no mesmo local de rede (ou seja, Office).</span><span class="sxs-lookup"><span data-stu-id="79cdf-117">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="79cdf-118">O roteamento de chamadas de saída será através da política de roteamento de voz do local de rede no qual o usuário está localizado.</span><span class="sxs-lookup"><span data-stu-id="79cdf-118">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="79cdf-119">As chamadas PSTN de entrada para o usuário são roteadas para pontos de extremidade localizados no mesmo local de rede que o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="79cdf-119">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="79cdf-120">O usuário está localizado em um site de rede conhecido que é diferente do local de rede onde o gateway PSTN está localizado.</span><span class="sxs-lookup"><span data-stu-id="79cdf-120">The user is located in a known network site that is in different from the network site where the PSTN gateway is located.</span></span> <span data-ttu-id="79cdf-121">(ou seja, o usuário viajau para outro escritório corporativo).</span><span class="sxs-lookup"><span data-stu-id="79cdf-121">(i.e. the user traveled to another corporate office).</span></span> <span data-ttu-id="79cdf-122">O roteamento de chamadas de saída usará a política de roteamento de voz do local de rede no qual o usuário está localizado.</span><span class="sxs-lookup"><span data-stu-id="79cdf-122">The routing of outbound calls will be using the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="79cdf-123">As chamadas PSTN de entrada para o usuário não serão encaminhadas para pontos de extremidade localizados em diferentes sites do que o gateway PSTN para impedir o bypass de chamada PSTN.</span><span class="sxs-lookup"><span data-stu-id="79cdf-123">Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="79cdf-124">Quando um usuário está localizado em um site de rede que é desconhecido para a implantação do Lync Server, o roteamento de chamadas de saída será baseado na política de voz atribuída ao usuário aos gateways PSTN não associados a Location-Based restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="79cdf-124">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="79cdf-125">As chamadas PSTN de entrada não serão encaminhadas para pontos de extremidade localizados em sites de rede desconhecidos para impedir o bypass de chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="79cdf-125">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="79cdf-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="79cdf-126">See Also</span></span>


[<span data-ttu-id="79cdf-127">Orientações para Location-Based roteamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79cdf-127">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

