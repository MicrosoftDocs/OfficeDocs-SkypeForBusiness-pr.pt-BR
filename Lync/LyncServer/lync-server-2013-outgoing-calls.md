---
title: 'Lync Server 2013: Chamadas de saída'
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
ms.openlocfilehash: 1a353cecbf1cdc1ff411c2cfe7c57edcd909c5c8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="09131-102">Chamadas de saída no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09131-102">Outgoing calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09131-103">_**Tópico da última modificação:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="09131-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="09131-104">O roteamento de chamadas de saída de usuários habilitados para roteamento baseado em local é afetado pelo local de rede do ponto de extremidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="09131-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="09131-105">A tabela a seguir ilustra como o roteamento baseado em localização afeta o roteamento de chamadas de saída, dependendo da localização do ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="09131-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="09131-106">Pessoa fazendo uma chamada de saída para o PSTN</span><span class="sxs-lookup"><span data-stu-id="09131-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="09131-107">Ponto de extremidade do usuário localizado em um local de rede habilitado para o Roteamento com Base no Local</span><span class="sxs-lookup"><span data-stu-id="09131-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="09131-108">Ponto de extremidade do usuário localizado em um local de rede desconhecido ou não habilitado para o Roteamento com Base no Local</span><span class="sxs-lookup"><span data-stu-id="09131-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09131-109">Autorização de chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="09131-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="09131-110">A chamada é autorizada com base na política de voz do usuário</span><span class="sxs-lookup"><span data-stu-id="09131-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="09131-111">A chamada é autorizada com base na política de voz do usuário</span><span class="sxs-lookup"><span data-stu-id="09131-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09131-112">Roteamento de chamada de saída</span><span class="sxs-lookup"><span data-stu-id="09131-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="09131-113">A chamada é roteada de acordo com a política de roteamento de voz do local de rede</span><span class="sxs-lookup"><span data-stu-id="09131-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="09131-114">A chamada é roteada de acordo com a política de voz do usuário e somente por meio de troncos não habilitados para o Roteamento com Base no Local (se disponível)</span><span class="sxs-lookup"><span data-stu-id="09131-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="09131-115">Confira também</span><span class="sxs-lookup"><span data-stu-id="09131-115">See Also</span></span>


[<span data-ttu-id="09131-116">Cenários para Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09131-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

