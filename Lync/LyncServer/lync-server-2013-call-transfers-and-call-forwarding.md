---
title: 'Lync Server 2013: transferências de chamadas e encaminhamento de chamadas'
description: 'Lync Server 2013: transferências de chamadas e encaminhamento de chamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9359cb64b386d022eab33e4523dfaccf784075b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565247"
---
# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="bccd3-103">Transferências de chamadas e encaminhamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bccd3-103">Call transfers and call forwarding in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bccd3-104">_**Última modificação do tópico:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="bccd3-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="bccd3-105">Quando um ponto de extremidade PSTN está envolvido, Location-Based roteamento analisa o local do ponto de extremidade do Calle e o ponto de extremidade onde a chamada será transferida ou encaminhada (ou seja, transferência/destino de encaminhamento).</span><span class="sxs-lookup"><span data-stu-id="bccd3-105">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="bccd3-106">Location-Based roteamento determina se a chamada deve ser transferida ou encaminhada dependendo do local dos dois pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="bccd3-106">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="bccd3-107">A tabela a seguir ilustra o cenário de um usuário do Lync em uma chamada com um ponto de extremidade PSTN e o usuário do Lync transfere a chamada para outro usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="bccd3-107">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="bccd3-108">Dependendo do local do site de rede do ponto de extremidade do transportador, Location-Based roteamento afeta o roteamento da transferência de chamada ou encaminhar.</span><span class="sxs-lookup"><span data-stu-id="bccd3-108">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="bccd3-109">Iniciando transferência ou encaminhamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="bccd3-109">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bccd3-110">Usuário iniciando a transferência/encaminhamento de chamada</span><span class="sxs-lookup"><span data-stu-id="bccd3-110">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="bccd3-111">O ponto de extremidade de destino está no mesmo local de rede que o usuário que inicia a transferência de chamada ou encaminha</span><span class="sxs-lookup"><span data-stu-id="bccd3-111">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="bccd3-112">O ponto de extremidade de destino está em um local de rede diferente como usuário Iniciando transferência de chamada ou encaminhar</span><span class="sxs-lookup"><span data-stu-id="bccd3-112">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="bccd3-113">O ponto de extremidade de destino está em um site de rede desconhecido ou site de rede não habilitado para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="bccd3-113">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bccd3-114">Usuário do Lync</span><span class="sxs-lookup"><span data-stu-id="bccd3-114">Lync user</span></span></p></td>
<td><p><span data-ttu-id="bccd3-115">Encaminhamento ou transferência de chamada permitido</span><span class="sxs-lookup"><span data-stu-id="bccd3-115">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="bccd3-116">Encaminhamento ou transferência de chamada não permitido</span><span class="sxs-lookup"><span data-stu-id="bccd3-116">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="bccd3-117">Encaminhamento ou transferência de chamada não permitido</span><span class="sxs-lookup"><span data-stu-id="bccd3-117">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="bccd3-118">Por exemplo: um usuário do Lync em uma chamada com um ponto de extremidade PSTN transfere a chamada para outro usuário do Lync que esteja no mesmo local de rede.</span><span class="sxs-lookup"><span data-stu-id="bccd3-118">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="bccd3-119">Nesse caso, a transferência de chamada é permitida.</span><span class="sxs-lookup"><span data-stu-id="bccd3-119">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="bccd3-120">A tabela a seguir ilustra o cenário de um usuário do Lync em uma chamada com outro usuário do Lync e um dos usuários transfere a chamada para um ponto de extremidade PSTN.</span><span class="sxs-lookup"><span data-stu-id="bccd3-120">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="bccd3-121">Dependendo do local do usuário para o qual a chamada está sendo transferida, a tabela detalha como o roteamento de Location-Based afeta a chamada.</span><span class="sxs-lookup"><span data-stu-id="bccd3-121">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="bccd3-122">Transferência de chamada ou encaminhamento para ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="bccd3-122">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bccd3-123">Transferência de chamada/destino de ponto de extremidade de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="bccd3-123">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="bccd3-124">Usuários do Lync no mesmo local de rede</span><span class="sxs-lookup"><span data-stu-id="bccd3-124">Lync users in same network site</span></span></th>
<th><span data-ttu-id="bccd3-125">Usuários do Lync em diferentes locais de rede</span><span class="sxs-lookup"><span data-stu-id="bccd3-125">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="bccd3-126">Um ou ambos os usuários do Lync em um site de rede desconhecido ou site de rede não habilitados para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="bccd3-126">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bccd3-127">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="bccd3-127">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="bccd3-128">Encaminhamento ou transferência de chamada permitida pela política de roteamento de voz do site do usuário transferido</span><span class="sxs-lookup"><span data-stu-id="bccd3-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="bccd3-129">Encaminhamento ou transferência de chamada permitida pela política de roteamento de voz do site do usuário transferido</span><span class="sxs-lookup"><span data-stu-id="bccd3-129">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="bccd3-130">Encaminhamento ou transferência de chamada permitida pela política de voz do usuário transferido apenas por meio de troncos não habilitados para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="bccd3-130">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="bccd3-131">Por exemplo: um usuário do Lync em uma chamada com outro usuário do Lync que está no mesmo local de rede transfere a chamada para um ponto de extremidade PSTN e a transferência de chamada é permitida.</span><span class="sxs-lookup"><span data-stu-id="bccd3-131">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="bccd3-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="bccd3-132">See Also</span></span>


[<span data-ttu-id="bccd3-133">Cenários para Location-Based roteamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bccd3-133">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

