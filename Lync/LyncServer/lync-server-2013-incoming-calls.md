---
title: 'Lync Server 2013: chamadas de entrada'
description: 'Lync Server 2013: chamadas de entrada.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a72c7fc378240f9751eae8e6c24e9cc601b08d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547727"
---
# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="d1ac2-103">Chamadas de entrada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1ac2-103">Incoming calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1ac2-104">_**Última modificação do tópico:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="d1ac2-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="d1ac2-105">O roteamento de chamadas de entrada para usuários habilitados para roteamento Location-Based depende do local do ponto de extremidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="d1ac2-105">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="d1ac2-106">O roteamento de chamadas de entrada é afetado da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="d1ac2-106">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="d1ac2-107">Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um site de rede habilitado para roteamento Location-Based e o ponto de extremidade estiver localizado no mesmo local de rede que o gateway PSTN, a chamada será encaminhada.</span><span class="sxs-lookup"><span data-stu-id="d1ac2-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="d1ac2-108">Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um local de rede habilitado para roteamento Location-Based e o ponto de extremidade estiver localizado em um local de rede diferente do gateway PSTN, a chamada não será encaminhada.</span><span class="sxs-lookup"><span data-stu-id="d1ac2-108">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="d1ac2-109">Quando um usuário não tem pontos de extremidade localizados no mesmo local de rede que o gateway PSTN em que a chamada de entrada é originada, a chamada de entrada será roteada diretamente para a caixa postal do usuário e uma notificação de chamada não atendida será enviada à parte chamada.</span><span class="sxs-lookup"><span data-stu-id="d1ac2-109">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="d1ac2-110">As configurações de encaminhamento de chamadas de um usuário habilitado para roteamento de Location-Based continuarão a ser impostas, no entanto, as chamadas encaminhadas serão sujeitas às restrições de roteamento Location-Based do usuário.</span><span class="sxs-lookup"><span data-stu-id="d1ac2-110">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="d1ac2-111">A tabela a seguir ilustra como Location-Based roteamento afeta o roteamento de chamadas de entrada, dependendo do local do ponto de extremidade do destinatário da chamada.</span><span class="sxs-lookup"><span data-stu-id="d1ac2-111">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="d1ac2-112">O site de rede do gateway PSTN é habilitado para roteamento Location-Based e Location-Based roteamento permite o roteamento de chamadas PSTN para pontos de extremidade dentro do mesmo local de rede.</span><span class="sxs-lookup"><span data-stu-id="d1ac2-112">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="d1ac2-113">Receptor que recebe uma chamada de entrada da PSTN</span><span class="sxs-lookup"><span data-stu-id="d1ac2-113">Callee receiving an inbound call from the PSTN</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="d1ac2-114">Ponto de extremidade do receptor localizado no mesmo local de rede que o gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="d1ac2-114">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="d1ac2-115">Ponto de extremidade do receptor não localizado no mesmo local de rede que o gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="d1ac2-115">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="d1ac2-116">Ponto de extremidade do receptor localizado no local de rede desconhecido ou não habilitado para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="d1ac2-116">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1ac2-117">Roteamento de chamadas PSTN de entrada</span><span class="sxs-lookup"><span data-stu-id="d1ac2-117">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="d1ac2-118">A chamada de entrada é encaminhada para os pontos de extremidade do destinatário da chamada</span><span class="sxs-lookup"><span data-stu-id="d1ac2-118">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="d1ac2-119">A chamada de entrada não é encaminhada para os pontos de extremidade do destinatário da chamada</span><span class="sxs-lookup"><span data-stu-id="d1ac2-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="d1ac2-120">A chamada de entrada não é encaminhada para os pontos de extremidade do destinatário da chamada</span><span class="sxs-lookup"><span data-stu-id="d1ac2-120">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="d1ac2-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="d1ac2-121">See Also</span></span>


[<span data-ttu-id="d1ac2-122">Cenários para Location-Based roteamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1ac2-122">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

