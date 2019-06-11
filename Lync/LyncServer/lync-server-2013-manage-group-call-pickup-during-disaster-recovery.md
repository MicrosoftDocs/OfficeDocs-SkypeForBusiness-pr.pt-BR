---
title: 'Lync Server 2013: gerenciar a coleta de chamadas em grupo durante a recuperação de desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bed21a672dfecab4c3cc8d828fd40f52bd82a363
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="a8cd8-102">Gerenciar a coleta de chamadas em grupo durante a recuperação de desastres no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8cd8-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8cd8-103">_**Tópico da última modificação:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="a8cd8-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="a8cd8-104">Quando um pool de front-end fica indisponível devido a um incidente não planejado, o serviço falha no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="a8cd8-105">Durante o failover para o pool de backup, os usuários são redirecionados para o pool de backup e estão no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="a8cd8-106">Enquanto estiver no modo de resiliência, os usuários não poderão atender as chamadas de outros usuários ou fazer com que as chamadas sejam selecionadas por outros usuários.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="a8cd8-107">Quando o failover for concluído, os usuários poderão usar novamente o recurso de recebimento de chamadas em grupo normalmente.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="a8cd8-108">Durante o failback para o pool primário, os usuários são redirecionados para o pool primário e são novamente no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="a8cd8-109">A funcionalidade de recebimento de chamada de grupo não estará disponível até que os usuários estejam fora do modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="a8cd8-110">Esta seção discute algumas considerações para o recebimento de chamadas em grupo durante a recuperação de desastres e também descreve a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="a8cd8-111">Considerações sobre o recebimento de chamadas em grupo durante a recuperação de desastres</span><span class="sxs-lookup"><span data-stu-id="a8cd8-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="a8cd8-112">Durante a recuperação de desastres, os usuários que foram redirecionados para o pool de backup como parte do processo de failover usam o aplicativo de estacionamento de chamada executado no pool de backup para os números de grupo de recebimento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="a8cd8-113">Portanto, o suporte para o recebimento de chamadas em grupo durante a recuperação de desastres requer que o aplicativo parque de chamadas seja implantado e habilitado no pool primário e no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="a8cd8-114">Os intervalos de números do recurso de chamada em grupo na tabela órbita do parque de chamadas devem ser redirecionados para o pool de backup após o término do processo de failover do pool de backup.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="a8cd8-115">Os intervalos de números devem ser redirecionados para o pool primário após a conclusão do processo de failback para o pool primário.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="a8cd8-116">Para redirecionar os intervalos de recebimento da chamada em grupo, use o cmdlet **set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="a8cd8-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="a8cd8-117">Se você implantar um novo pool com um nome de domínio totalmente qualificado (FQDN) diferente para substituir o pool primário, será necessário reatribuir todos os intervalos de número de retirada de chamada de grupo que foram associados ao pool primário ao FQDN do novo pool.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="a8cd8-118">Para reatribuir intervalos de números ao novo pool, você pode usar o cmdlet **set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="a8cd8-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="a8cd8-119">Para obter detalhes sobre o cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="a8cd8-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="a8cd8-120">Experiência de recebimento de chamadas em grupo durante falha de pool</span><span class="sxs-lookup"><span data-stu-id="a8cd8-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="a8cd8-121">A tabela a seguir resume a experiência de retirada de chamadas em grupo pelas fases da recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="a8cd8-122">Experiência do usuário durante a recuperação de desastres</span><span class="sxs-lookup"><span data-stu-id="a8cd8-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8cd8-123">Estado da chamada</span><span class="sxs-lookup"><span data-stu-id="a8cd8-123">Call state</span></span></th>
<th><span data-ttu-id="a8cd8-124">Failover para pool de backup</span><span class="sxs-lookup"><span data-stu-id="a8cd8-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="a8cd8-125">Failback para pool primário</span><span class="sxs-lookup"><span data-stu-id="a8cd8-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8cd8-126">Novas chamadas</span><span class="sxs-lookup"><span data-stu-id="a8cd8-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="a8cd8-127"><strong>Durante o processo de failover:</strong></span><span class="sxs-lookup"><span data-stu-id="a8cd8-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="a8cd8-128">Retirada de chamadas em grupo não disponível para usuários no modo de resiliência</span><span class="sxs-lookup"><span data-stu-id="a8cd8-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="a8cd8-129"><strong>Após a conclusão do failover:</strong></span><span class="sxs-lookup"><span data-stu-id="a8cd8-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="a8cd8-130">Retirada de chamadas em grupo disponível quando os usuários estiverem fora da resiliência e os intervalos de números de recebimento de chamadas em grupo forem redirecionados para o pool de backup</span><span class="sxs-lookup"><span data-stu-id="a8cd8-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a8cd8-131"><strong>Durante o processo de failback:</strong></span><span class="sxs-lookup"><span data-stu-id="a8cd8-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="a8cd8-132">Retirada de chamadas em grupo não disponível para usuários no modo de resiliência</span><span class="sxs-lookup"><span data-stu-id="a8cd8-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="a8cd8-133"><strong>Após concluir o failback:</strong></span><span class="sxs-lookup"><span data-stu-id="a8cd8-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="a8cd8-134">Retirada de chamadas em grupo disponível quando os usuários estiverem fora da resiliência e os intervalos de números de recebimento de chamadas em grupo forem redirecionados para o pool primário</span><span class="sxs-lookup"><span data-stu-id="a8cd8-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8cd8-135">Chamadas na fila de recebimento de chamadas em grupo</span><span class="sxs-lookup"><span data-stu-id="a8cd8-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="a8cd8-136"><strong>Durante o processo de failover:</strong></span><span class="sxs-lookup"><span data-stu-id="a8cd8-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="a8cd8-137">As chamadas na fila não podem ser atendidas por meio da retirada de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="a8cd8-138"><strong>Após a conclusão do failover:</strong></span><span class="sxs-lookup"><span data-stu-id="a8cd8-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="a8cd8-139">Nenhuma chamada neste estado</span><span class="sxs-lookup"><span data-stu-id="a8cd8-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a8cd8-140"><strong>Durante o processo de failback:</strong></span><span class="sxs-lookup"><span data-stu-id="a8cd8-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="a8cd8-141">As chamadas na fila não podem ser atendidas por meio da retirada de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="a8cd8-142"><strong>Após concluir o failback:</strong></span><span class="sxs-lookup"><span data-stu-id="a8cd8-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="a8cd8-143">As chamadas na fila não podem ser atendidas por meio da retirada de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="a8cd8-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8cd8-144">Chamada estabelecida</span><span class="sxs-lookup"><span data-stu-id="a8cd8-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="a8cd8-145"><strong>Durante o processo de failover:</strong></span><span class="sxs-lookup"><span data-stu-id="a8cd8-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="a8cd8-146">As chamadas permanecem conectadas</span><span class="sxs-lookup"><span data-stu-id="a8cd8-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="a8cd8-147"><strong>Após a conclusão do failover:</strong></span><span class="sxs-lookup"><span data-stu-id="a8cd8-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="a8cd8-148">As chamadas permanecem conectadas</span><span class="sxs-lookup"><span data-stu-id="a8cd8-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a8cd8-149"><strong>Durante o processo de failback:</strong></span><span class="sxs-lookup"><span data-stu-id="a8cd8-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="a8cd8-150">As chamadas permanecem conectadas</span><span class="sxs-lookup"><span data-stu-id="a8cd8-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="a8cd8-151"><strong>Após concluir o failback:</strong></span><span class="sxs-lookup"><span data-stu-id="a8cd8-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="a8cd8-152">As chamadas permanecem conectadas</span><span class="sxs-lookup"><span data-stu-id="a8cd8-152">Calls stay connected</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

