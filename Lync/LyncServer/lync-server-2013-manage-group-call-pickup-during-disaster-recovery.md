---
title: 'Lync Server 2013: gerenciar o recebimento de chamadas em grupo durante a recuperação de desastre'
description: 'Lync Server 2013: gerenciar o recebimento de chamadas de grupo durante a recuperação de desastres.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04d85bc83cfe35571c2b0f47f707c9dcd8037d80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555277"
---
# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="483bf-103">Gerenciar o recebimento de chamadas em grupo durante a recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="483bf-103">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="483bf-104">_**Última modificação do tópico:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="483bf-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="483bf-105">Quando um pool de front-ends fica indisponível devido a um incidente não planejado, o serviço falha no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="483bf-105">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="483bf-106">Durante o failover para o pool de backup, os usuários são redirecionados para o pool de backup e estão no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="483bf-106">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="483bf-107">No modo de resiliência, os usuários não podem selecionar as chamadas de outros usuários ou fazer com que suas chamadas sejam escolhidas por outros usuários.</span><span class="sxs-lookup"><span data-stu-id="483bf-107">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="483bf-108">Quando o failover é concluído, os usuários podem usar novamente o recebimento de chamadas em grupo como de costume.</span><span class="sxs-lookup"><span data-stu-id="483bf-108">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="483bf-109">Durante o failback para o pool primário, os usuários são redirecionados para o pool primário e estão novamente no modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="483bf-109">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="483bf-110">A funcionalidade de recebimento de chamadas de grupo não está disponível até que os usuários estejam fora do modo de resiliência.</span><span class="sxs-lookup"><span data-stu-id="483bf-110">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="483bf-111">Esta seção discute algumas considerações para o recebimento de chamadas em grupo durante a recuperação de desastres e também descreve a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="483bf-111">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="483bf-112">Considerações sobre o recebimento de chamadas em grupo durante a recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="483bf-112">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="483bf-113">Durante a recuperação de desastres, os usuários que foram redirecionados para o pool de backup como parte do processo de failover usam o aplicativo de estacionamento de chamada em execução no pool de backup para os números do grupo de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="483bf-113">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="483bf-114">Portanto, o suporte para o recebimento de chamadas em grupo durante a recuperação de desastres exige que o aplicativo de estacionamento de chamada seja implantado e habilitado no pool primário e no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="483bf-114">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="483bf-115">Os intervalos de números de recebimento de chamadas de grupo na tabela de órbita de estacionamento de chamada devem ser redirecionados para o pool de backup após a conclusão do processo de failover para o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="483bf-115">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="483bf-116">Os intervalos de números devem ser redirecionados de volta para o pool primário após a conclusão do processo de failback para o pool primário.</span><span class="sxs-lookup"><span data-stu-id="483bf-116">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="483bf-117">Para redirecionar os intervalos de recebimento de chamadas de grupo, use o cmdlet **set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="483bf-117">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="483bf-118">Se você implantar um novo pool com um FQDN (nome de domínio totalmente qualificado) diferente para substituir o pool primário, será necessário reatribuir todos os intervalos de número de recebimento de chamadas de grupo associados ao pool primário ao FQDN do novo pool.</span><span class="sxs-lookup"><span data-stu-id="483bf-118">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="483bf-119">Para reatribuir intervalos de números ao novo pool, você pode usar o cmdlet **set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="483bf-119">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="483bf-120">Para obter detalhes sobre o cmdlet **set-CsCallParkOrbit** , consulte [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="483bf-120">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="483bf-121">Experiência de recebimento de chamadas de grupo durante falha do pool</span><span class="sxs-lookup"><span data-stu-id="483bf-121">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="483bf-122">A tabela a seguir resume a experiência de recebimento de chamadas de grupo por meio das fases de recuperação de desastres.</span><span class="sxs-lookup"><span data-stu-id="483bf-122">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="483bf-123">Experiência do usuário durante a recuperação de desastres</span><span class="sxs-lookup"><span data-stu-id="483bf-123">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="483bf-124">Estado da chamada</span><span class="sxs-lookup"><span data-stu-id="483bf-124">Call state</span></span></th>
<th><span data-ttu-id="483bf-125">Failover para pool de backup</span><span class="sxs-lookup"><span data-stu-id="483bf-125">Failover to backup pool</span></span></th>
<th><span data-ttu-id="483bf-126">Failback para pool primário</span><span class="sxs-lookup"><span data-stu-id="483bf-126">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="483bf-127">Novas chamadas</span><span class="sxs-lookup"><span data-stu-id="483bf-127">New calls</span></span></p></td>
<td><p><span data-ttu-id="483bf-128"><strong>Durante o processo de failover:</strong></span><span class="sxs-lookup"><span data-stu-id="483bf-128"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="483bf-129">Retirada de chamada em grupo não disponível para usuários no modo de resiliência</span><span class="sxs-lookup"><span data-stu-id="483bf-129">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="483bf-130"><strong>Após a conclusão do failover:</strong></span><span class="sxs-lookup"><span data-stu-id="483bf-130"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="483bf-131">Retirada de chamada em grupo disponível quando os usuários são redirecionados para o pool de backup de resiliência e de chamada de grupo</span><span class="sxs-lookup"><span data-stu-id="483bf-131">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="483bf-132"><strong>Durante o processo de failback:</strong></span><span class="sxs-lookup"><span data-stu-id="483bf-132"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="483bf-133">Retirada de chamada em grupo não disponível para usuários no modo de resiliência</span><span class="sxs-lookup"><span data-stu-id="483bf-133">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="483bf-134"><strong>Após a conclusão do failback:</strong></span><span class="sxs-lookup"><span data-stu-id="483bf-134"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="483bf-135">Retirada de chamada em grupo disponível quando os usuários fora da resiliência e os intervalos de números de recebimento de chamadas de grupo são redirecionados de volta para o pool principal</span><span class="sxs-lookup"><span data-stu-id="483bf-135">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="483bf-136">Chamadas na fila de recebimento de chamadas em grupo</span><span class="sxs-lookup"><span data-stu-id="483bf-136">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="483bf-137"><strong>Durante o processo de failover:</strong></span><span class="sxs-lookup"><span data-stu-id="483bf-137"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="483bf-138">As chamadas na fila não podem ser atendidas por recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="483bf-138">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="483bf-139"><strong>Após a conclusão do failover:</strong></span><span class="sxs-lookup"><span data-stu-id="483bf-139"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="483bf-140">Nenhuma chamada neste estado</span><span class="sxs-lookup"><span data-stu-id="483bf-140">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="483bf-141"><strong>Durante o processo de failback:</strong></span><span class="sxs-lookup"><span data-stu-id="483bf-141"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="483bf-142">As chamadas na fila não podem ser atendidas por recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="483bf-142">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="483bf-143"><strong>Após a conclusão do failback:</strong></span><span class="sxs-lookup"><span data-stu-id="483bf-143"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="483bf-144">As chamadas na fila não podem ser atendidas por recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="483bf-144">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="483bf-145">Chamada estabelecida</span><span class="sxs-lookup"><span data-stu-id="483bf-145">Established call</span></span></p></td>
<td><p><span data-ttu-id="483bf-146"><strong>Durante o processo de failover:</strong></span><span class="sxs-lookup"><span data-stu-id="483bf-146"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="483bf-147">Chamadas permanecem conectadas</span><span class="sxs-lookup"><span data-stu-id="483bf-147">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="483bf-148"><strong>Após a conclusão do failover:</strong></span><span class="sxs-lookup"><span data-stu-id="483bf-148"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="483bf-149">Chamadas permanecem conectadas</span><span class="sxs-lookup"><span data-stu-id="483bf-149">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="483bf-150"><strong>Durante o processo de failback:</strong></span><span class="sxs-lookup"><span data-stu-id="483bf-150"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="483bf-151">Chamadas permanecem conectadas</span><span class="sxs-lookup"><span data-stu-id="483bf-151">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="483bf-152"><strong>Após a conclusão do failback:</strong></span><span class="sxs-lookup"><span data-stu-id="483bf-152"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="483bf-153">Chamadas permanecem conectadas</span><span class="sxs-lookup"><span data-stu-id="483bf-153">Calls stay connected</span></span></p></li>
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

