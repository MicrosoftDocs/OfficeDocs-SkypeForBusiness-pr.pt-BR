---
title: 'Lync Server 2013: experiência de estacionamento de chamadas durante falha do pool'
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
ms.openlocfilehash: a89acc193f70ba5047a2f1c6362b957d182afdb5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="6959c-102">Experiência de estacionamento de chamadas no Lync Server 2013 durante falha do pool</span><span class="sxs-lookup"><span data-stu-id="6959c-102">Call Park experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6959c-103">_**Última modificação do tópico:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="6959c-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="6959c-104">Quando um pool de front-ends fica indisponível devido a um incidente não planejado, as chamadas que foram estacionadas, mas ainda não foram recuperadas, são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="6959c-104">When a Front End pool becomes unavailable due an unplanned incident, calls that have been parked but not yet retrieved are disconnected.</span></span> <span data-ttu-id="6959c-105">Durante o failover para um pool de backup, os usuários são redirecionados ao pool de backup e estão no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="6959c-105">During failover to a backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="6959c-106">Enquanto estão no modo de resiliência, os usuários não podem estacionar chamadas, mas podem colocar chamadas em espera e transferi-las.</span><span class="sxs-lookup"><span data-stu-id="6959c-106">While in resiliency mode, users cannot park calls, but they can place calls on hold and transfer them.</span></span> <span data-ttu-id="6959c-107">Quando o failover estiver concluído, as chamadas podem novamente ser estacionadas e recuperadas normalmente.</span><span class="sxs-lookup"><span data-stu-id="6959c-107">When failover is complete, calls can again be parked and retrieved as usual.</span></span> <span data-ttu-id="6959c-108">Durante o failback, os usuários não podem estacionar chamadas até saírem do modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="6959c-108">During failback, users cannot park calls until they are out of resiliency mode.</span></span>

<span data-ttu-id="6959c-109">Durante a recuperação de desastres, os usuários que foram redirecionados para o pool de backup como parte do processo de failover usam o aplicativo de estacionamento de chamada implantado no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="6959c-109">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application that is deployed in the backup pool.</span></span> <span data-ttu-id="6959c-110">Portanto, os usuários que são redirecionados para o pool de backup usam as configurações de estacionamento de chamadas configuradas para o aplicativo de estacionamento de chamada no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="6959c-110">Therefore, users who are redirected to the backup pool use the call park settings that are configured for the Call Park application in the backup pool.</span></span>

<span data-ttu-id="6959c-111">A tabela a seguir resume a experiência de estacionamento de chamada através das fases de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="6959c-111">The following table summarizes the Call Park experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="6959c-112">Experiência do usuário durante a recuperação de desastres</span><span class="sxs-lookup"><span data-stu-id="6959c-112">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6959c-113">Estado da chamada</span><span class="sxs-lookup"><span data-stu-id="6959c-113">Call state</span></span></th>
<th><span data-ttu-id="6959c-114">Quando ocorre uma interrupção</span><span class="sxs-lookup"><span data-stu-id="6959c-114">When outage occurs</span></span></th>
<th><span data-ttu-id="6959c-115">Durante o failover</span><span class="sxs-lookup"><span data-stu-id="6959c-115">During failover</span></span></th>
<th><span data-ttu-id="6959c-116">Durante o failback</span><span class="sxs-lookup"><span data-stu-id="6959c-116">During failback</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6959c-117">Chamada ainda não estacionada</span><span class="sxs-lookup"><span data-stu-id="6959c-117">Call not yet parked</span></span></p></td>
<td><p><span data-ttu-id="6959c-118">A chamada permanece conectada, mas não pode ser estacionada.</span><span class="sxs-lookup"><span data-stu-id="6959c-118">Call remains connected, but cannot be parked.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6959c-119">Durante o failover, a chamada não pode ser estacionada enquanto os usuários estão no modo de resiliência, mas podem ser colocadas em espera e transferidas.</span><span class="sxs-lookup"><span data-stu-id="6959c-119">During failover, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="6959c-120">Quando o failover é concluído, a chamada pode ser estacionada e recuperada.</span><span class="sxs-lookup"><span data-stu-id="6959c-120">When failover completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="6959c-121">Durante o failback, a chamada não pode ser estacionada enquanto os usuários estão no modo de resiliência, mas podem ser colocadas em espera e transferidas.</span><span class="sxs-lookup"><span data-stu-id="6959c-121">During failback, call cannot be parked while users are in resiliency mode, but can be put on hold and transferred.</span></span></p></li>
<li><p><span data-ttu-id="6959c-122">Quando o failback é concluído, a chamada pode ser estacionada e recuperada.</span><span class="sxs-lookup"><span data-stu-id="6959c-122">When failback completes, call can be parked and retrieved.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6959c-123">Chamada estacionada, mas ainda não recuperada</span><span class="sxs-lookup"><span data-stu-id="6959c-123">Call parked, but not yet retrieved</span></span></p></td>
<td><p><span data-ttu-id="6959c-124">A chamada é desconectada.</span><span class="sxs-lookup"><span data-stu-id="6959c-124">Call is disconnected.</span></span></p></td>
<td><p><span data-ttu-id="6959c-125">Nenhuma chamada neste estado.</span><span class="sxs-lookup"><span data-stu-id="6959c-125">No calls in this state.</span></span></p></td>
<td><p><span data-ttu-id="6959c-126">A chamada é mantida estacionada.</span><span class="sxs-lookup"><span data-stu-id="6959c-126">Call remains parked.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6959c-127">Chamada estacionada já recuperada.</span><span class="sxs-lookup"><span data-stu-id="6959c-127">Parked call already retrieved</span></span></p></td>
<td><p><span data-ttu-id="6959c-128">A chamada é mantida conectada.</span><span class="sxs-lookup"><span data-stu-id="6959c-128">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="6959c-129">A chamada é mantida conectada.</span><span class="sxs-lookup"><span data-stu-id="6959c-129">Call remains connected.</span></span></p></td>
<td><p><span data-ttu-id="6959c-130">A chamada é mantida conectada.</span><span class="sxs-lookup"><span data-stu-id="6959c-130">Call remains connected.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

