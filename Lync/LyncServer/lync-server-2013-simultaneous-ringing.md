---
title: 'Lync Server 2013: Toque simultâneo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7303c1fc77d109bd08044c8acff56aaf538790d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="43457-102">Toque simultâneo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43457-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43457-103">_**Tópico da última modificação:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="43457-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="43457-104">Quando a parte chamada tem o toque simultâneo habilitado, o roteamento baseado em local analisa o local da parte de chamada e os pontos de extremidade das partes chamadas para determinar se a chamada deve ser roteada.</span><span class="sxs-lookup"><span data-stu-id="43457-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="43457-105">A tabela a seguir ilustra um usuário configurado com toque simultâneo, e o destino do toque simultâneo é um usuário no mesmo local de rede, em um local de rede diferente ou em um local de rede desconhecido.</span><span class="sxs-lookup"><span data-stu-id="43457-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43457-106">Chamadas de entrada do PSTN para</span><span class="sxs-lookup"><span data-stu-id="43457-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="43457-107">Localizado no mesmo local de rede do destinatário da chamada</span><span class="sxs-lookup"><span data-stu-id="43457-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="43457-108">Localizado em um local de rede diferente do chamador</span><span class="sxs-lookup"><span data-stu-id="43457-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="43457-109">Localizado no site desconhecido de rede ou não habilitado para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="43457-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43457-110">Usuário do Lync</span><span class="sxs-lookup"><span data-stu-id="43457-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="43457-111">Toque simultâneo permitido</span><span class="sxs-lookup"><span data-stu-id="43457-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="43457-112">Toque simultâneo não permitido</span><span class="sxs-lookup"><span data-stu-id="43457-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="43457-113">Toque simultâneo não permitido</span><span class="sxs-lookup"><span data-stu-id="43457-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="43457-114">A tabela a seguir ilustra uma chamada de um usuário do Lync (ou seja, o chamador do Lync) no mesmo site de rede, em um site de rede diferente ou em um site de rede desconhecido.</span><span class="sxs-lookup"><span data-stu-id="43457-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="43457-115">O destinatário da chamada tem um ponto de extremidade PSTN (ou seja, um telefone celular) configurado como um destino de toque simultâneo.</span><span class="sxs-lookup"><span data-stu-id="43457-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="43457-116">Nesse cenário, o roteamento baseado em localização determinará se a chamada deve ser roteada para o destino de toque simultâneo (isto é, o celular) do receptor ou não.</span><span class="sxs-lookup"><span data-stu-id="43457-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43457-117">Destino de toque simultâneo</span><span class="sxs-lookup"><span data-stu-id="43457-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="43457-118">Localizado no mesmo local de rede do destinatário da chamada</span><span class="sxs-lookup"><span data-stu-id="43457-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="43457-119">Localizado em um local de rede diferente do chamador</span><span class="sxs-lookup"><span data-stu-id="43457-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="43457-120">Localizado no site desconhecido de rede ou não habilitado para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="43457-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43457-121">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="43457-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="43457-122">Toque simultâneo permitido por meio da política de roteamento de voz do local do chamador</span><span class="sxs-lookup"><span data-stu-id="43457-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="43457-123">Toque simultâneo permitido por meio da política de roteamento de voz do local do chamador</span><span class="sxs-lookup"><span data-stu-id="43457-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="43457-124">Toque simultâneo permitido por meio da política de roteamento de voz do local do chamador para troncos não habilitados para o Roteamento com Base no Local</span><span class="sxs-lookup"><span data-stu-id="43457-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="43457-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="43457-125">See Also</span></span>


[<span data-ttu-id="43457-126">Cenários para Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43457-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

