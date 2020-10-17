---
title: 'Lync Server 2013: toque simultâneo'
description: 'Lync Server 2013: toque simultâneo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 595c8c1d4ce105e2189002f18733ffae92cff8bf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555657"
---
# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="2d34c-103">Toque simultâneo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d34c-103">Simultaneous ringing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d34c-104">_**Última modificação do tópico:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="2d34c-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="2d34c-105">Quando a parte chamada tem o toque simultâneo habilitado, Location-Based roteamento analisa o local da parte de chamada e os pontos de extremidade das partes chamadas para determinar se a chamada deve ser encaminhada.</span><span class="sxs-lookup"><span data-stu-id="2d34c-105">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="2d34c-106">A tabela a seguir ilustra um usuário configurado com toque simultâneo, e o alvo de toque simultâneo é um usuário no mesmo local de rede, em um site de rede diferente ou em um site de rede desconhecido.</span><span class="sxs-lookup"><span data-stu-id="2d34c-106">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d34c-107">Chamada PSTN de entrada para</span><span class="sxs-lookup"><span data-stu-id="2d34c-107">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="2d34c-108">Localizado no mesmo local de rede que o receptor da chamada</span><span class="sxs-lookup"><span data-stu-id="2d34c-108">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="2d34c-109">Localizado em um local de rede diferente do chamado</span><span class="sxs-lookup"><span data-stu-id="2d34c-109">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="2d34c-110">Localizado no local de rede desconhecido ou não habilitado para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="2d34c-110">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d34c-111">Usuário do Lync</span><span class="sxs-lookup"><span data-stu-id="2d34c-111">Lync user</span></span></p></td>
<td><p><span data-ttu-id="2d34c-112">Anel simultâneo permitido</span><span class="sxs-lookup"><span data-stu-id="2d34c-112">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="2d34c-113">Toque simultâneo não permitido</span><span class="sxs-lookup"><span data-stu-id="2d34c-113">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="2d34c-114">Toque simultâneo não permitido</span><span class="sxs-lookup"><span data-stu-id="2d34c-114">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="2d34c-115">A tabela a seguir ilustra uma chamada de um usuário do Lync (ou seja, o chamador do Lync) no mesmo local de rede, em um site de rede diferente ou de um site de rede desconhecido.</span><span class="sxs-lookup"><span data-stu-id="2d34c-115">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="2d34c-116">O receptor tem um ponto de extremidade PSTN (i.e. celular) configurado como um alvo de anel simultâneo.</span><span class="sxs-lookup"><span data-stu-id="2d34c-116">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="2d34c-117">Neste cenário, Location-Based roteamento determinará se a chamada deve ser roteada para o alvo de anel simultâneo (ou seja, celular) do receptor ou não.</span><span class="sxs-lookup"><span data-stu-id="2d34c-117">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d34c-118">Alvo de anel simultâneo</span><span class="sxs-lookup"><span data-stu-id="2d34c-118">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="2d34c-119">Localizado no mesmo local de rede que o receptor da chamada</span><span class="sxs-lookup"><span data-stu-id="2d34c-119">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="2d34c-120">Localizado em um local de rede diferente do chamado</span><span class="sxs-lookup"><span data-stu-id="2d34c-120">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="2d34c-121">Localizado no local de rede desconhecido ou não habilitado para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="2d34c-121">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d34c-122">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="2d34c-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="2d34c-123">Toque simultâneo permitido por meio da política de roteamento de voz do site do chamador</span><span class="sxs-lookup"><span data-stu-id="2d34c-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="2d34c-124">Toque simultâneo permitido por meio da política de roteamento de voz do site do chamador</span><span class="sxs-lookup"><span data-stu-id="2d34c-124">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="2d34c-125">Toque simultâneo permitido por meio da política de voz do chamador para troncos não habilitados para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="2d34c-125">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="2d34c-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="2d34c-126">See Also</span></span>


[<span data-ttu-id="2d34c-127">Cenários para Location-Based roteamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d34c-127">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

