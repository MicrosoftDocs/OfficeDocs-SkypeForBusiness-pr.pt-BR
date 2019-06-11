---
title: 'Lync Server 2013: Transferência e encaminhamento de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5b0661cfaaef2e514f070260f44abc4ea00572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="b03bc-102">Transferência e encaminhamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b03bc-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b03bc-103">_**Tópico da última modificação:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="b03bc-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="b03bc-104">Quando um ponto de extremidade PSTN está envolvido, o roteamento baseado em localização analisa o local do ponto de extremidade do Calle e o ponto de extremidade onde a chamada será transferida ou encaminhada (ou seja, transferência/destino para encaminhamento).</span><span class="sxs-lookup"><span data-stu-id="b03bc-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="b03bc-105">O roteamento baseado em local determina se a chamada deve ser transferida ou encaminhada, dependendo da localização dos dois pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="b03bc-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="b03bc-106">A tabela a seguir ilustra o cenário de um usuário do Lync em uma chamada com um ponto de extremidade PSTN, e o usuário do Lync transfere a chamada para outro usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="b03bc-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="b03bc-107">Dependendo do local do site de rede do ponto de extremidade do transportador, o roteamento baseado em local afeta o roteamento da transferência ou encaminhamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b03bc-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="b03bc-108">Iniciando a transferência ou o encaminhamento de chamada</span><span class="sxs-lookup"><span data-stu-id="b03bc-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b03bc-109">Usuário que inicia a transferência/encaminhamento da chamada</span><span class="sxs-lookup"><span data-stu-id="b03bc-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="b03bc-110">O ponto de extremidade de destino está no mesmo local de rede do usuário que inicia a transferência ou o encaminhamento da chamada</span><span class="sxs-lookup"><span data-stu-id="b03bc-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="b03bc-111">O ponto de extremidade de destino está em um local de rede diferente do que o do usuário que inicia a transferência ou o encaminhamento da chamada</span><span class="sxs-lookup"><span data-stu-id="b03bc-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="b03bc-112">O ponto de extremidade de destino está em um site de rede desconhecido ou site de rede não habilitado para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="b03bc-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b03bc-113">Usuário do Lync</span><span class="sxs-lookup"><span data-stu-id="b03bc-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="b03bc-114">Encaminhamento ou transferência de chamada permitido</span><span class="sxs-lookup"><span data-stu-id="b03bc-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="b03bc-115">Encaminhamento ou transferência de chamada não permitido</span><span class="sxs-lookup"><span data-stu-id="b03bc-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="b03bc-116">Encaminhamento ou transferência de chamada não permitido</span><span class="sxs-lookup"><span data-stu-id="b03bc-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="b03bc-117">Por exemplo: um usuário do Lync em uma chamada com um ponto de extremidade PSTN transfere a chamada para outro usuário do Lync que esteja no mesmo site de rede.</span><span class="sxs-lookup"><span data-stu-id="b03bc-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="b03bc-118">Nesse caso, a transferência de chamada é permitida.</span><span class="sxs-lookup"><span data-stu-id="b03bc-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="b03bc-119">A tabela a seguir ilustra o cenário de um usuário do Lync em uma chamada com outro usuário do Lync, e um dos usuários transfere a chamada para um ponto de extremidade PSTN.</span><span class="sxs-lookup"><span data-stu-id="b03bc-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="b03bc-120">Dependendo do local do usuário para o qual a chamada está sendo transferida, a tabela detalhará como o Roteamento Baseado na Localização afeta a chamada.</span><span class="sxs-lookup"><span data-stu-id="b03bc-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="b03bc-121">Transferência ou encaminhamento de chamada para um ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="b03bc-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b03bc-122">Destino do ponto de extremidade da transferência/encaminhamento de chamada</span><span class="sxs-lookup"><span data-stu-id="b03bc-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="b03bc-123">Usuários do Lync no mesmo local de rede</span><span class="sxs-lookup"><span data-stu-id="b03bc-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="b03bc-124">Usuários do Lync em diferentes sites de rede</span><span class="sxs-lookup"><span data-stu-id="b03bc-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="b03bc-125">Um ou ambos os usuários do Lync em um site de rede desconhecido ou site de rede não estão habilitados para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="b03bc-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b03bc-126">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="b03bc-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="b03bc-127">O encaminhamento ou a transferência de chamada é permitida pela política de roteamento de voz do local do usuário transferido</span><span class="sxs-lookup"><span data-stu-id="b03bc-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="b03bc-128">O encaminhamento ou a transferência de chamada é permitida pela política de roteamento de voz do local do usuário transferido</span><span class="sxs-lookup"><span data-stu-id="b03bc-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="b03bc-129">O encaminhamento ou a transferência da chamada é permitida pela política de voz do destinatário da transferência somente pelos troncos não habilitados para o Roteamento com Base no Local</span><span class="sxs-lookup"><span data-stu-id="b03bc-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="b03bc-130">Por exemplo: um usuário do Lync em uma chamada com outro usuário do Lync que esteja no mesmo local de rede transfere a chamada para um ponto de extremidade PSTN e a transferência de chamada é permitida.</span><span class="sxs-lookup"><span data-stu-id="b03bc-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b03bc-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="b03bc-131">See Also</span></span>


[<span data-ttu-id="b03bc-132">Cenários para Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b03bc-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

