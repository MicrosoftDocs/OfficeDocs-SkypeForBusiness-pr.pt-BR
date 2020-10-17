---
title: 'Lync Server 2013: chamadas de saída'
description: 'Lync Server 2013: chamadas de saída.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e14f19dec35a6da47a2ddd62657d5d087a854f16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546847"
---
# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="81dd2-103">Chamadas de saída no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81dd2-103">Outgoing calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81dd2-104">_**Última modificação do tópico:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="81dd2-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="81dd2-105">O roteamento de chamadas de saída de usuários habilitados para roteamento Location-Based é afetado pelo local de rede do ponto de extremidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="81dd2-105">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="81dd2-106">A tabela a seguir ilustra como Location-Based roteamento afeta o roteamento de chamadas de saída, dependendo do local do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="81dd2-106">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="81dd2-107">Chamador colocando uma chamada de saída para o PSTN</span><span class="sxs-lookup"><span data-stu-id="81dd2-107">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="81dd2-108">Ponto de extremidade do usuário localizado em um site de rede habilitado para roteamento Location-Based</span><span class="sxs-lookup"><span data-stu-id="81dd2-108">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="81dd2-109">Ponto de extremidade do usuário localizado em um local de rede desconhecido ou não habilitado para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="81dd2-109">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81dd2-110">Autorização de chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="81dd2-110">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="81dd2-111">A chamada é autorizada com base na política de voz do usuário</span><span class="sxs-lookup"><span data-stu-id="81dd2-111">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="81dd2-112">A chamada é autorizada com base na política de voz do usuário</span><span class="sxs-lookup"><span data-stu-id="81dd2-112">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81dd2-113">Roteamento de chamada de saída</span><span class="sxs-lookup"><span data-stu-id="81dd2-113">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="81dd2-114">A chamada é roteada de acordo com a política de roteamento de voz do site da rede</span><span class="sxs-lookup"><span data-stu-id="81dd2-114">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="81dd2-115">A chamada é roteada de acordo com a política de voz do usuário e apenas por troncos não habilitados para roteamento de Location-Based (se disponível)</span><span class="sxs-lookup"><span data-stu-id="81dd2-115">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="81dd2-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="81dd2-116">See Also</span></span>


[<span data-ttu-id="81dd2-117">Cenários para Location-Based roteamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81dd2-117">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

