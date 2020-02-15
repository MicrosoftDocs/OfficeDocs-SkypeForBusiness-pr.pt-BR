---
title: Gerenciando recuperação de desastre, alta disponibilidade e serviço de backup do Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83e0446bbc0b39f553ac9a2bcba0af9ceacc421f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="5f102-102">Gerenciando recuperação de desastre, alta disponibilidade e serviço de backup do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f102-103">_**Última modificação do tópico:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="5f102-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="5f102-104">Esta seção contém os procedimentos para operações de recuperação de desastres, bem como para realizar a manutenção do Serviço de Backup, que sincroniza os dados de pools de Front Ends emparelhados.</span><span class="sxs-lookup"><span data-stu-id="5f102-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="5f102-p101">Os procedimentos de recuperação de desastres, o failover e o failback, são manuais. Se ocorrer um desastre, o administrador deve chamar manualmente os procedimentos de failover. O mesmo se aplica ao failback após a reparação do pool.</span><span class="sxs-lookup"><span data-stu-id="5f102-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="5f102-108">Os procedimentos de recuperação de desastres no restante dessa seção pressupõem que:</span><span class="sxs-lookup"><span data-stu-id="5f102-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="5f102-109">Você tem uma implantação com pools de front-ends emparelhados, localizados em diferentes sites, conforme descrito em [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="5f102-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="5f102-110">O Serviço de Backup é executado nestes pools emparelhados para mantê-los sincronizados.</span><span class="sxs-lookup"><span data-stu-id="5f102-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="5f102-111">Se o repositório de gerenciamento central estiver hospedado em um dos pools, ele será instalado e executado nos dois pools emparelhados, com um desses pools hospedando o mestre ativo e o outro pool que hospeda o modo de espera.</span><span class="sxs-lookup"><span data-stu-id="5f102-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="5f102-p103">Nos procedimentos a seguir, o parâmetro <EM>PoolFQDN</EM> se refere ao FQDN do pool afetado pelo desastre, e não o pool para o qual os usuários afetados foram redirecionados. Para o mesmo conjunto de usuários afetados, ele se refere ao mesmo pool em ambos os cmdlets de failover e failback (ou seja, o pool que primeiramente hospedou os usuários antes do failover).</span><span class="sxs-lookup"><span data-stu-id="5f102-p103">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="5f102-p104">Por exemplo, pressuponha um caso em que todos os usuários hospedados no pool P1 foram transferidos para o pool de backup, o P2. Se o administrador deseja mover todos os usuários que utilizam os serviços de P2 para utilizarem os serviços de P1, o administrador deve executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="5f102-p104">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2. If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="5f102-p105">Retorne do P2 para o P1 todos os usuários originalmente hospedados em P1 utilizando o cmdlet de failback. Nesse caso, <EM>PoolFQDN</EM> é o FQDN de P1.</span><span class="sxs-lookup"><span data-stu-id="5f102-p105">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet. In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="5f102-p106">Transfira todos os usuários originalmente hospedados em P2 para o P1 utilizando o cmdlet de failover. Nesse caso, a propriedade <EM>PoolFQDN</EM> é o FQDN de P2.</span><span class="sxs-lookup"><span data-stu-id="5f102-p106">Fail over all the users originally homed on P2 to P1 using the failover cmdlet. In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="5f102-120">Se o administrador desejar retornar posteriormente os usuários para o P2, o <EM>PoolFQDN</EM> é o FQDN do P2.</span><span class="sxs-lookup"><span data-stu-id="5f102-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="5f102-121">Observe que a etapa 1 acima deve ser realizada antes da etapa 2 para preservar a integridade do pool.</span><span class="sxs-lookup"><span data-stu-id="5f102-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="5f102-122">Se você executar a etapa 2 antes da etapa 1, o cmdlet da etapa 2 falhará.</span><span class="sxs-lookup"><span data-stu-id="5f102-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5f102-123">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5f102-123">In This Section</span></span>

  - [<span data-ttu-id="5f102-124">Configurando e monitorando o serviço de backup no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="5f102-125">Failover de um pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="5f102-126">Failback de um pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="5f102-127">Failover de um banco de dados espelhado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="5f102-128">Failover do pool de borda usado para Federação do Lync Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="5f102-129">Failover do pool de borda usado para Federação XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="5f102-130">Failback do pool de borda usado para Federação do Lync Server ou Federação XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="5f102-131">Alterar o pool de borda associado a um pool de front-ends no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="5f102-132">Restaurando o conteúdo da conferência usando o serviço de backup no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5f102-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="5f102-133">See Also</span></span>


[<span data-ttu-id="5f102-134">Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f102-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

