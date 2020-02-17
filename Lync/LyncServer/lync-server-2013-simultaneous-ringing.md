---
title: 'Lync Server 2013: toque simultâneo'
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
ms.openlocfilehash: 4e3104da5e7d351bda26698087e97106cafbdff4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="20add-102">Toque simultâneo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20add-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20add-103">_**Última modificação do tópico:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="20add-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="20add-104">Quando a parte chamada tem o toque simultâneo habilitado, o roteamento baseado em local analisa o local da parte de chamadas e os pontos de extremidade das partes chamadas para determinar se a chamada deve ser encaminhada.</span><span class="sxs-lookup"><span data-stu-id="20add-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="20add-105">A tabela a seguir ilustra um usuário configurado com toque simultâneo, e o alvo de toque simultâneo é um usuário no mesmo local de rede, em um site de rede diferente ou em um site de rede desconhecido.</span><span class="sxs-lookup"><span data-stu-id="20add-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20add-106">Chamada PSTN de entrada para</span><span class="sxs-lookup"><span data-stu-id="20add-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="20add-107">Localizado no mesmo local de rede que o receptor da chamada</span><span class="sxs-lookup"><span data-stu-id="20add-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="20add-108">Localizado em um local de rede diferente do chamado</span><span class="sxs-lookup"><span data-stu-id="20add-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="20add-109">Localizado no local de rede desconhecido ou não habilitado para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="20add-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20add-110">Usuário do Lync</span><span class="sxs-lookup"><span data-stu-id="20add-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="20add-111">Anel simultâneo permitido</span><span class="sxs-lookup"><span data-stu-id="20add-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="20add-112">Toque simultâneo não permitido</span><span class="sxs-lookup"><span data-stu-id="20add-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="20add-113">Toque simultâneo não permitido</span><span class="sxs-lookup"><span data-stu-id="20add-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="20add-114">A tabela a seguir ilustra uma chamada de um usuário do Lync (ou seja, o chamador do Lync) no mesmo local de rede, em um site de rede diferente ou de um site de rede desconhecido.</span><span class="sxs-lookup"><span data-stu-id="20add-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="20add-115">O receptor tem um ponto de extremidade PSTN (i.e. celular) configurado como um alvo de anel simultâneo.</span><span class="sxs-lookup"><span data-stu-id="20add-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="20add-116">Neste cenário, o roteamento baseado em local determinará se a chamada deve ser roteada para o alvo de anel simultâneo (ou seja, celular) do receptor ou não.</span><span class="sxs-lookup"><span data-stu-id="20add-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20add-117">Alvo de anel simultâneo</span><span class="sxs-lookup"><span data-stu-id="20add-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="20add-118">Localizado no mesmo local de rede que o receptor da chamada</span><span class="sxs-lookup"><span data-stu-id="20add-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="20add-119">Localizado em um local de rede diferente do chamado</span><span class="sxs-lookup"><span data-stu-id="20add-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="20add-120">Localizado no local de rede desconhecido ou não habilitado para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="20add-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20add-121">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="20add-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="20add-122">Toque simultâneo permitido por meio da política de roteamento de voz do site do chamador</span><span class="sxs-lookup"><span data-stu-id="20add-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="20add-123">Toque simultâneo permitido por meio da política de roteamento de voz do site do chamador</span><span class="sxs-lookup"><span data-stu-id="20add-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="20add-124">Toque simultâneo permitido por meio da política de voz do chamador para troncos não habilitados para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="20add-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="20add-125">Confira Também</span><span class="sxs-lookup"><span data-stu-id="20add-125">See Also</span></span>


[<span data-ttu-id="20add-126">Cenários para roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20add-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

