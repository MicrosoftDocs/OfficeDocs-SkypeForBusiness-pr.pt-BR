---
title: 'Lync Server 2013: chamadas de entrada'
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
ms.openlocfilehash: c153af6e14c291189f714f7054f72301d6859a88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="f772d-102">Chamadas de entrada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f772d-102">Incoming calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f772d-103">_**Última modificação do tópico:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="f772d-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="f772d-104">O roteamento de chamadas de entrada para usuários habilitados para roteamento baseado em local depende do local do ponto de extremidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="f772d-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="f772d-105">O roteamento de chamadas de entrada é afetado da seguinte maneira.</span><span class="sxs-lookup"><span data-stu-id="f772d-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="f772d-106">Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um local de rede habilitado para roteamento baseado em local e o ponto de extremidade estiver localizado no mesmo local de rede que o gateway PSTN, a chamada será encaminhada.</span><span class="sxs-lookup"><span data-stu-id="f772d-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="f772d-107">Se um usuário tiver uma chamada de entrada para um ponto de extremidade localizado em um local de rede habilitado para roteamento baseado em local e o ponto de extremidade estiver localizado em um local de rede diferente do gateway PSTN, a chamada não será roteada.</span><span class="sxs-lookup"><span data-stu-id="f772d-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="f772d-108">Quando um usuário não tem pontos de extremidade localizados no mesmo local de rede que o gateway PSTN em que a chamada de entrada é originada, a chamada de entrada será roteada diretamente para a caixa postal do usuário e uma notificação de chamada não atendida será enviada à parte chamada.</span><span class="sxs-lookup"><span data-stu-id="f772d-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="f772d-109">As configurações de encaminhamento de chamadas de um usuário habilitado para roteamento baseado em local continuarão a ser impostas, no entanto, as chamadas encaminhadas serão sujeitas a restrições de roteamento com base no local do usuário.</span><span class="sxs-lookup"><span data-stu-id="f772d-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="f772d-110">A tabela a seguir ilustra como o roteamento baseado em local afeta o roteamento de chamadas de entrada, dependendo do local do ponto de extremidade do destinatário da chamada.</span><span class="sxs-lookup"><span data-stu-id="f772d-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="f772d-111">O site de rede do gateway PSTN está habilitado para roteamento baseado em local e o roteamento baseado em local permite o roteamento de chamadas PSTN para pontos de extremidade no mesmo local de rede.</span><span class="sxs-lookup"><span data-stu-id="f772d-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="f772d-112">Receptor que recebe uma chamada de entrada da PSTN</span><span class="sxs-lookup"><span data-stu-id="f772d-112">Callee receiving an inbound call from the PSTN</span></span>

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
<th><span data-ttu-id="f772d-113">Ponto de extremidade do receptor localizado no mesmo local de rede que o gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="f772d-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="f772d-114">Ponto de extremidade do receptor não localizado no mesmo local de rede que o gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="f772d-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="f772d-115">Ponto de extremidade do receptor localizado no local de rede desconhecido ou não habilitado para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="f772d-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f772d-116">Roteamento de chamadas PSTN de entrada</span><span class="sxs-lookup"><span data-stu-id="f772d-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="f772d-117">A chamada de entrada é encaminhada para os pontos de extremidade do destinatário da chamada</span><span class="sxs-lookup"><span data-stu-id="f772d-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="f772d-118">A chamada de entrada não é encaminhada para os pontos de extremidade do destinatário da chamada</span><span class="sxs-lookup"><span data-stu-id="f772d-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="f772d-119">A chamada de entrada não é encaminhada para os pontos de extremidade do destinatário da chamada</span><span class="sxs-lookup"><span data-stu-id="f772d-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="f772d-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="f772d-120">See Also</span></span>


[<span data-ttu-id="f772d-121">Cenários para roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f772d-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

