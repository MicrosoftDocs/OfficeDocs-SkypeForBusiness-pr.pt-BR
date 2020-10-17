---
title: 'Lync Server 2013: experiência de estacionamento de chamadas durante falha do pool'
description: 'Lync Server 2013: experiência de estacionamento de chamadas durante falha do pool.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b97a0af13d378b0753979c32b6d5ffe7a525cf0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565267"
---
# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="f9033-103">Experiência de estacionamento de chamadas no Lync Server 2013 durante falha do pool</span><span class="sxs-lookup"><span data-stu-id="f9033-103">Call Park experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9033-104">_**Última modificação do tópico:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="f9033-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="f9033-105">Quando um pool de front-ends fica indisponível devido a um incidente não planejado, as chamadas que foram estacionadas, mas ainda não foram recuperadas, são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="f9033-105">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="f9033-106">Durante o failover para um pool de backup, os usuários são redirecionados ao pool de backup e estão no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="f9033-106">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="f9033-107">Enquanto estão no modo de resiliência, os usuários não podem estacionar chamadas, mas podem colocar chamadas em espera e transferi-las.</span><span class="sxs-lookup"><span data-stu-id="f9033-107">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="f9033-108">Quando o failover estiver concluído, as chamadas podem novamente ser estacionadas e recuperadas normalmente.</span><span class="sxs-lookup"><span data-stu-id="f9033-108">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="f9033-109">Durante o failback, os usuários não podem estacionar chamadas até saírem do modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="f9033-109">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="f9033-110">Durante a recuperação de desastres, os usuários que foram redirecionados para o pool de backup como parte do processo de failover usam o aplicativo de estacionamento de chamada implantado no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="f9033-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="f9033-111">Portanto, os usuários que são redirecionados para o pool de backup usam as configurações de estacionamento de chamadas configuradas para o aplicativo de estacionamento de chamada no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="f9033-111">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="f9033-112">A tabela a seguir resume a experiência de estacionamento de chamada através das fases de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="f9033-112">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="f9033-113">Experiência do usuário durante a recuperação de desastres</span><span class="sxs-lookup"><span data-stu-id="f9033-113">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9033-114">Estado da chamada</span><span class="sxs-lookup"><span data-stu-id="f9033-114">Call state</span></span></th>
<th><span data-ttu-id="f9033-115">Quando ocorre uma interrupção</span><span class="sxs-lookup"><span data-stu-id="f9033-115">When outage occurs</span></span></th>
<th><span data-ttu-id="f9033-116">Durante o failover</span><span class="sxs-lookup"><span data-stu-id="f9033-116">During failover</span></span></th>
<th><span data-ttu-id="f9033-117">Durante o failback</span><span class="sxs-lookup"><span data-stu-id="f9033-117">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9033-118">Chamada ainda não estacionada</span><span class="sxs-lookup"><span data-stu-id="f9033-118">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="f9033-119">A chamada permanece conectada, mas não pode ser estacionada.</span><span class="sxs-lookup"><span data-stu-id="f9033-119">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="f9033-120">Durante o failover, a chamada não pode ser estacionada enquanto os usuários estão no modo de resiliência, mas podem ser colocadas em espera e transferidas.</span><span class="sxs-lookup"><span data-stu-id="f9033-120">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="f9033-121">Quando o failover é concluído, a chamada pode ser estacionada e recuperada.</span><span class="sxs-lookup"><span data-stu-id="f9033-121">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="f9033-122">Durante o failback, a chamada não pode ser estacionada enquanto os usuários estão no modo de resiliência, mas podem ser colocadas em espera e transferidas.</span><span class="sxs-lookup"><span data-stu-id="f9033-122">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="f9033-123">Quando o failback é concluído, a chamada pode ser estacionada e recuperada.</span><span class="sxs-lookup"><span data-stu-id="f9033-123">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9033-124">Chamada estacionada, mas ainda não recuperada</span><span class="sxs-lookup"><span data-stu-id="f9033-124">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="f9033-125">A chamada é desconectada.</span><span class="sxs-lookup"><span data-stu-id="f9033-125">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="f9033-126">Nenhuma chamada neste estado.</span><span class="sxs-lookup"><span data-stu-id="f9033-126">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="f9033-127">A chamada é mantida estacionada.</span><span class="sxs-lookup"><span data-stu-id="f9033-127">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9033-128">Chamada estacionada já recuperada.</span><span class="sxs-lookup"><span data-stu-id="f9033-128">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="f9033-129">A chamada é mantida conectada.</span><span class="sxs-lookup"><span data-stu-id="f9033-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="f9033-130">A chamada é mantida conectada.</span><span class="sxs-lookup"><span data-stu-id="f9033-130">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="f9033-131">A chamada é mantida conectada.</span><span class="sxs-lookup"><span data-stu-id="f9033-131">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

