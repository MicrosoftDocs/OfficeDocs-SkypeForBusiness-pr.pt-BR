---
title: Gerenciamento de recuperação de desastres do Lync Server, alta disponibilidade e serviço de backup
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cada393fca28895ee5f23a12fdd55eabd211128e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="457aa-102">Gerenciando recuperação de desastre, alta disponibilidade e Serviço de Backup do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="457aa-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="457aa-103">_**Tópico da última modificação:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="457aa-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="457aa-104">Esta seção contém procedimentos para operações de recuperação de desastres, bem como para manter o serviço de backup que sincroniza os dados em pools front-ends emparelhados.</span><span class="sxs-lookup"><span data-stu-id="457aa-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="457aa-105">Procedimentos de recuperação de desastre, failover e failback, são manuais.</span><span class="sxs-lookup"><span data-stu-id="457aa-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="457aa-106">Se houver um desastre, o administrador deve invocar manualmente os procedimentos de failover.</span><span class="sxs-lookup"><span data-stu-id="457aa-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="457aa-107">O mesmo se aplica a failback após o rereparo do pool.</span><span class="sxs-lookup"><span data-stu-id="457aa-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="457aa-108">Os procedimentos de recuperação de desastre no restante desta seção pressupõem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="457aa-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="457aa-109">Você tem uma implantação com pools front-end emparelhados, localizada em sites diferentes, conforme descrito em [planejamento para alta disponibilidade e recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="457aa-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="457aa-110">O serviço de backup está em execução nesses pools emparelhados para mantê-los sincronizados.</span><span class="sxs-lookup"><span data-stu-id="457aa-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="457aa-111">Se o repositório de gerenciamento central estiver hospedado em qualquer um dos pools, ele será instalado e executado em ambos os pools emparelhados, com um desses pools que hospeda o mestre ativo e o outro pool que hospeda o modo de espera.</span><span class="sxs-lookup"><span data-stu-id="457aa-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="457aa-112">Nos procedimentos a seguir, o parâmetro <EM>PoolFQDN</EM> refere-se ao FQDN do pool afetado pelo desastre, e não ao pool em que os usuários afetados estão sendo redirecionados.</span><span class="sxs-lookup"><span data-stu-id="457aa-112">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="457aa-113">Para o mesmo conjunto de usuários afetados, ele se refere ao mesmo pool em cmdlets de failover e failback (ou seja, o pool que primeiro hospeda os usuários antes do failover).</span><span class="sxs-lookup"><span data-stu-id="457aa-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="457aa-114">Por exemplo, suponha que um caso em que todos os usuários hospedados em um pool P1 tivessem falhado para o pool de backup, P2.</span><span class="sxs-lookup"><span data-stu-id="457aa-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="457aa-115">Se o administrador quiser mover todos os usuários atualmente atendidos pelo P2 a serem atendidos pelo P1, o administrador deve executar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="457aa-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="457aa-116">Faça o failback de todos os usuários originalmente hospedados no P1 do P2 para P1 usando o cmdlet failback.</span><span class="sxs-lookup"><span data-stu-id="457aa-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="457aa-117">Nesse caso, o <EM>PoolFQDN</EM> é P1's FQDN.</span><span class="sxs-lookup"><span data-stu-id="457aa-117">In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="457aa-118">Fazer failover de todos os usuários originalmente hospedados no P2 do P1 usando o cmdlet de failover.</span><span class="sxs-lookup"><span data-stu-id="457aa-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="457aa-119">Nesse caso, o <EM>PoolFQDN</EM> é P2's FQDN.</span><span class="sxs-lookup"><span data-stu-id="457aa-119">In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="457aa-120">Se o administrador mais tarde quiser fazer failback desses usuários de P2 de volta para P2, o <EM>PoolFQDN</EM> será P2's FQDN.</span><span class="sxs-lookup"><span data-stu-id="457aa-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="457aa-121">Observe que a etapa 1 acima deve ser realizada antes da etapa 2 para preservar a integridade do pool.</span><span class="sxs-lookup"><span data-stu-id="457aa-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="457aa-122">Se você tentar a etapa 2 antes da etapa 1, o cmdlet etapa 2 falhará.</span><span class="sxs-lookup"><span data-stu-id="457aa-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="457aa-123">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="457aa-123">In This Section</span></span>

  - [<span data-ttu-id="457aa-124">Configurando e monitorando o Serviço de Backup no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="457aa-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="457aa-125">Fazendo failover de um pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="457aa-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="457aa-126">Failback de pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="457aa-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="457aa-127">Failover de banco de dados espelhado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="457aa-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="457aa-128">Failover do pool de Borda usado para federação do Servidor Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="457aa-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="457aa-129">Failover do pool de Borda usado para federação de XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="457aa-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="457aa-130">Failback do pool de Borda usado para federação do Lync Server ou federação XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="457aa-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="457aa-131">Alterando o Pool de borda associado ao pool Front-End no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="457aa-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="457aa-132">Restaurando conteúdos de conferência usando o Serviço de Backup no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="457aa-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="457aa-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="457aa-133">See Also</span></span>


[<span data-ttu-id="457aa-134">Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="457aa-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

