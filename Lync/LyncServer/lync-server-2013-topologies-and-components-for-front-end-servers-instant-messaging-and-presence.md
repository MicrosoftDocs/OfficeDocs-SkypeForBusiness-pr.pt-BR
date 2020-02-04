---
title: 'Lync Server 2013: Topologias e componentes para Servidores Front-End, serviço de mensagens instantâneas e presença'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 181ae682ec5ee1352c5d4f4280b4164fbbcd91f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="4adab-102">Topologias e componentes para Servidores Front-End, serviço de mensagens instantâneas e presença no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4adab-102">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4adab-103">_**Tópico da última modificação:** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="4adab-103">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="4adab-104">Os únicos componentes necessários para mensagem instantânea (IM) e presença são:</span><span class="sxs-lookup"><span data-stu-id="4adab-104">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="4adab-105">Servidores front-end da sua organização ou servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4adab-105">Your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="4adab-106">As capacidades de IM e presença estão sempre habilitadas nesses servidores.</span><span class="sxs-lookup"><span data-stu-id="4adab-106">IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="4adab-107">Um balanceador de carga, se você tiver um pool de Front-Ends do Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="4adab-107">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="4adab-108">Para obter mais informações, consulte [requisitos de balanceamento de carga do Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4adab-108">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="4adab-109">Planejando a implantação de pools de front-end</span><span class="sxs-lookup"><span data-stu-id="4adab-109">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="4adab-110">No Lync Server 2013, a arquitetura de pool de front-end mudou e essas alterações afetam como você deve planejar e manter seus pools de front-end.</span><span class="sxs-lookup"><span data-stu-id="4adab-110">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="4adab-111">Recomendamos que todos os seus pools do front-end da Enterprise Edition incluam pelo menos três servidores front end.</span><span class="sxs-lookup"><span data-stu-id="4adab-111">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="4adab-112">No Lync Server, a arquitetura dos pools front-ends usa um modelo de sistema distribuído, com os dados de cada usuário mantidos em três servidores front-end no pool.</span><span class="sxs-lookup"><span data-stu-id="4adab-112">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="4adab-113">Para obter mais informações sobre essa nova arquitetura, consulte [alterações de topologia no Lync Server 2013](lync-server-2013-topology-changes.md).</span><span class="sxs-lookup"><span data-stu-id="4adab-113">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="4adab-114">Se você não quiser implantar três servidores de front-end do Enterprise Edition e quiser a recuperação de desastres, recomendamos usar o Lync Server Standard Edition e criar dois pools com uma relação de backup emparelhada.</span><span class="sxs-lookup"><span data-stu-id="4adab-114">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="4adab-115">Isso permitirá uma solução de recuperação de desastres com apenas dois servidores.</span><span class="sxs-lookup"><span data-stu-id="4adab-115">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="4adab-116">Para obter mais informações, em topologias e recursos de alta disponibilidade e recuperação de desastres, consulte [planejando a alta disponibilidade e a recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="4adab-116">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="4adab-117">Planejamento para o gerenciamento de pools front-end</span><span class="sxs-lookup"><span data-stu-id="4adab-117">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="4adab-118">Para os pools front-end, siga as diretrizes desta seção.</span><span class="sxs-lookup"><span data-stu-id="4adab-118">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="4adab-119">Garantindo que os pools sejam funcionais</span><span class="sxs-lookup"><span data-stu-id="4adab-119">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="4adab-120">Com o novo modelo distribuído para grupos de front-end, determinados números de servidores de um pool devem estar em execução para que o pool funcione.</span><span class="sxs-lookup"><span data-stu-id="4adab-120">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="4adab-121">Há dois modos de perda para um pool</span><span class="sxs-lookup"><span data-stu-id="4adab-121">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="4adab-122">Perda de quórum no nível do grupo de roteamento, causada por servidores de réplica insuficientes para um grupo de roteamento em particular.</span><span class="sxs-lookup"><span data-stu-id="4adab-122">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="4adab-123">Um grupo de roteamento é uma agregação de um conjunto de usuários hospedados no pool.</span><span class="sxs-lookup"><span data-stu-id="4adab-123">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="4adab-124">Cada grupo de roteamento tem três réplicas no pool: uma primária e duas secundárias.</span><span class="sxs-lookup"><span data-stu-id="4adab-124">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="4adab-125">Perda de quórum no nível do pool, causada quando um número insuficiente de servidores de propagação está em execução no pool.</span><span class="sxs-lookup"><span data-stu-id="4adab-125">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="4adab-126">Perda de quórum no nível do grupo de roteamento</span><span class="sxs-lookup"><span data-stu-id="4adab-126">Routing Group Level quorum loss</span></span>

<span data-ttu-id="4adab-p107">A primeira vez que você iniciar um novo Pool de Front-Ends, é essencial que 85% dos servidores estejam em execução, conforme exibido na tabela a seguir. Se menos servidores estiverem em execução, os serviços poderão ficar parados no estado inicial e o pool pode não iniciar.</span><span class="sxs-lookup"><span data-stu-id="4adab-p107">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table. If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4adab-129">Número total de servidores no pool</span><span class="sxs-lookup"><span data-stu-id="4adab-129">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="4adab-130">Número de servidores que devem estar em execução para que o pool seja iniciado na primeira vez</span><span class="sxs-lookup"><span data-stu-id="4adab-130">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4adab-131">2</span><span class="sxs-lookup"><span data-stu-id="4adab-131">2</span></span></p></td>
<td><p><span data-ttu-id="4adab-132">1</span><span class="sxs-lookup"><span data-stu-id="4adab-132">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4adab-133">3</span><span class="sxs-lookup"><span data-stu-id="4adab-133">3</span></span></p></td>
<td><p><span data-ttu-id="4adab-134">3</span><span class="sxs-lookup"><span data-stu-id="4adab-134">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4adab-135">4</span><span class="sxs-lookup"><span data-stu-id="4adab-135">4</span></span></p></td>
<td><p><span data-ttu-id="4adab-136">3</span><span class="sxs-lookup"><span data-stu-id="4adab-136">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4adab-137">5</span><span class="sxs-lookup"><span data-stu-id="4adab-137">5</span></span></p></td>
<td><p><span data-ttu-id="4adab-138">4</span><span class="sxs-lookup"><span data-stu-id="4adab-138">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4adab-139">6</span><span class="sxs-lookup"><span data-stu-id="4adab-139">6</span></span></p></td>
<td><p><span data-ttu-id="4adab-140">5</span><span class="sxs-lookup"><span data-stu-id="4adab-140">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4adab-141">7</span><span class="sxs-lookup"><span data-stu-id="4adab-141">7</span></span></p></td>
<td><p><span data-ttu-id="4adab-142">5</span><span class="sxs-lookup"><span data-stu-id="4adab-142">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4adab-143">8</span><span class="sxs-lookup"><span data-stu-id="4adab-143">8</span></span></p></td>
<td><p><span data-ttu-id="4adab-144">6</span><span class="sxs-lookup"><span data-stu-id="4adab-144">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4adab-145">9</span><span class="sxs-lookup"><span data-stu-id="4adab-145">9</span></span></p></td>
<td><p><span data-ttu-id="4adab-146">7</span><span class="sxs-lookup"><span data-stu-id="4adab-146">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4adab-147">254</span><span class="sxs-lookup"><span data-stu-id="4adab-147">10</span></span></p></td>
<td><p><span data-ttu-id="4adab-148">8</span><span class="sxs-lookup"><span data-stu-id="4adab-148">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4adab-149">11:00</span><span class="sxs-lookup"><span data-stu-id="4adab-149">11</span></span></p></td>
<td><p><span data-ttu-id="4adab-150">9</span><span class="sxs-lookup"><span data-stu-id="4adab-150">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4adab-151">12</span><span class="sxs-lookup"><span data-stu-id="4adab-151">12</span></span></p></td>
<td><p><span data-ttu-id="4adab-152">254</span><span class="sxs-lookup"><span data-stu-id="4adab-152">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4adab-153">Cada vez subsequente que o pool for iniciado, 85% dos servidores devem ser iniciados (conforme exibido na tabela anterior).</span><span class="sxs-lookup"><span data-stu-id="4adab-153">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="4adab-154">Caso não seja possível iniciar esse número de servidores (mas servidores suficientes podem ser iniciados para que não haja perda de quórum no nível do pool), é possível usar o cmdlet **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** para permitir que o pool se recupere dessa perda de quórum no nível do grupo de roteamento e faça progresso.</span><span class="sxs-lookup"><span data-stu-id="4adab-154">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="4adab-155">Para obter mais informações sobre como usar esse cmdlet, consulte [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span><span class="sxs-lookup"><span data-stu-id="4adab-155">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4adab-156">Como o Lync Server usa o banco de dados SQL principal como testemunha, se você desligar o banco de dados principal e alternar para a cópia espelhada e desligar servidores de front-end suficientes para que não sejam executados de acordo com a tabela anterior, todo o pool será desativado.</span><span class="sxs-lookup"><span data-stu-id="4adab-156">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="4adab-157">Para obter mais informações, consulte <A href="http://go.microsoft.com/fwlink/?linkid=393672">testemunha de espelhamento de banco de dados</A>.</span><span class="sxs-lookup"><span data-stu-id="4adab-157">For more information, see <A href="http://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="4adab-158">Perda de quórum no nível do pool</span><span class="sxs-lookup"><span data-stu-id="4adab-158">Pool-level quorum loss</span></span>

<span data-ttu-id="4adab-159">Para que um pool de front-end funcione, ele não pode estar em perda de quorum no nível do pool.</span><span class="sxs-lookup"><span data-stu-id="4adab-159">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="4adab-160">Se o número de servidores em execução ficar abaixo do nível funcional, conforme mostrado na tabela a seguir, os servidores restantes do pool pararão todos os serviços do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4adab-160">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="4adab-161">Observe que os números na tabela a seguir pressupõem que os servidores back-end do pool estejam em execução.</span><span class="sxs-lookup"><span data-stu-id="4adab-161">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4adab-162">Número total de servidores front-end no pool</span><span class="sxs-lookup"><span data-stu-id="4adab-162">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="4adab-163">Número de servidores que devem estar em execução para o pool ser funcional</span><span class="sxs-lookup"><span data-stu-id="4adab-163">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4adab-164">2</span><span class="sxs-lookup"><span data-stu-id="4adab-164">2</span></span></p></td>
<td><p><span data-ttu-id="4adab-165">1</span><span class="sxs-lookup"><span data-stu-id="4adab-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4adab-166">3-4</span><span class="sxs-lookup"><span data-stu-id="4adab-166">3-4</span></span></p></td>
<td><p><span data-ttu-id="4adab-167">Qualquer um dos 2</span><span class="sxs-lookup"><span data-stu-id="4adab-167">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4adab-168">5-6</span><span class="sxs-lookup"><span data-stu-id="4adab-168">5-6</span></span></p></td>
<td><p><span data-ttu-id="4adab-169">Qualquer um dos 3</span><span class="sxs-lookup"><span data-stu-id="4adab-169">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4adab-170">7</span><span class="sxs-lookup"><span data-stu-id="4adab-170">7</span></span></p></td>
<td><p><span data-ttu-id="4adab-171">Qualquer um dos 4</span><span class="sxs-lookup"><span data-stu-id="4adab-171">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4adab-172">8-9</span><span class="sxs-lookup"><span data-stu-id="4adab-172">8-9</span></span></p></td>
<td><p><span data-ttu-id="4adab-173">Qualquer um dos 4 dos 7 primeiros servidores</span><span class="sxs-lookup"><span data-stu-id="4adab-173">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4adab-174">10-12</span><span class="sxs-lookup"><span data-stu-id="4adab-174">10-12</span></span></p></td>
<td><p><span data-ttu-id="4adab-175">Qualquer um dos 5 dos 9 primeiros servidores</span><span class="sxs-lookup"><span data-stu-id="4adab-175">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4adab-176">Na tabela anterior, os “primeiros servidores” são aqueles criados primeiro, cronologicamente, quando o pool foi iniciado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="4adab-176">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="4adab-177">Para determinar esses servidores, você pode usar o cmdlet **Get-CsComputer** com a opção **– PoolFqdn** .</span><span class="sxs-lookup"><span data-stu-id="4adab-177">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="4adab-178">Esse cmdlet exibirá os servidores na ordem em que aparecem na topologia, e aqueles que aparecem no topo da lista são os primeiros servidores.</span><span class="sxs-lookup"><span data-stu-id="4adab-178">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="4adab-179">Pools de front-end com dois servidores front end</span><span class="sxs-lookup"><span data-stu-id="4adab-179">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="4adab-180">Não recomendamos implantar um pool de front-end que contenha apenas dois servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="4adab-180">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="4adab-181">Se você precisar implantar tal pool, siga estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="4adab-181">If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="4adab-182">Se um dos dois servidores front-ends ficar inativo, tente trazer o servidor com falha para o backup assim que possível.</span><span class="sxs-lookup"><span data-stu-id="4adab-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="4adab-183">Da mesma forma, se você precisar atualizar um dos dois servidores, ative-o assim que a atualização terminar.</span><span class="sxs-lookup"><span data-stu-id="4adab-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="4adab-184">Se por alguma razão você precisar desativar ambos os servidores ao mesmo tempo, realize o seguinte procedimento quando o tempo de inatividade do pool for concluído:</span><span class="sxs-lookup"><span data-stu-id="4adab-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="4adab-185">A prática recomendada é reiniciar os dois servidores front-end ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="4adab-185">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="4adab-186">Se os dois servidores não podem ser reiniciados ao mesmo tempo, você deve ativá-los na ordem contrária em que foram desativados.</span><span class="sxs-lookup"><span data-stu-id="4adab-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="4adab-187">Se não for possível recolocá-los nesse pedido, use o cmdlet a seguir antes de trazer o pool para o backup:.</span><span class="sxs-lookup"><span data-stu-id="4adab-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="4adab-188">Etapas adicionais para garantir que os pools sejam funcionais</span><span class="sxs-lookup"><span data-stu-id="4adab-188">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="4adab-189">Observe alguns outros fatores para garantir que seus Pools de Front-Ends permaneçam funcionais.</span><span class="sxs-lookup"><span data-stu-id="4adab-189">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="4adab-190">Quando você mover usuários para o pool pela primeira vez, certifique-se de que pelo menos três dos servidores front-end estejam em execução.</span><span class="sxs-lookup"><span data-stu-id="4adab-190">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="4adab-191">Se você estabelecer uma relação de emparelhamento entre este pool e outro pool para fins de recuperação de desastre, depois de estabelecer essa relação, você deve ter certeza de que esse pool tem três servidores front-ends sendo executados simultaneamente em algum momento para sincronizar corretamente dados com o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="4adab-191">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="4adab-192">Para obter mais informações sobre emparelhamento de pool e recursos de recuperação de desastre, consulte [planejando alta disponibilidade e recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="4adab-192">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="4adab-193">Melhorar a confiabilidade de atualizações de pool</span><span class="sxs-lookup"><span data-stu-id="4adab-193">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="4adab-194">Quando precisar atualizar ou corrigir os servidores em um pool Front-end, siga o fluxo de trabalho exibido em [atualizar ou atualizar servidores front-end no Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)e as seguintes diretrizes:</span><span class="sxs-lookup"><span data-stu-id="4adab-194">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="4adab-195">Quando você passa de um domínio de atualização para outro para obter atualizações (seguindo o fluxo de trabalho em [atualizar ou atualizar servidores front-end no Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), você usará o cmdlet **Get-CsPoolUpgradeReadinessState** e verificará o estado pronto.</span><span class="sxs-lookup"><span data-stu-id="4adab-195">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="4adab-196">Adicionar uma espera de 20 minutos entre cada domínio de atualização depois que ele atinge "pronto" torna as atualizações mais confiáveis.</span><span class="sxs-lookup"><span data-stu-id="4adab-196">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="4adab-197">Se ele **não estiver pronto** durante estes 20 minutos, reinicie o temporizador de 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="4adab-197">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="4adab-198">Além disso, você pode executar o cmdlet **Get-CsPoolFabricState** antes e depois de iniciar o intervalo de 20 minutos e verificar se não há alterações nas primrias e nos secundários dos grupos de roteamento.</span><span class="sxs-lookup"><span data-stu-id="4adab-198">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="4adab-199">Não vá para o próximo domínio de atualização se algum dos servidores no último domínio de atualização corrigido estiver preso ou não for reiniciado.</span><span class="sxs-lookup"><span data-stu-id="4adab-199">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="4adab-200">Isso também se aplica se não for possível iniciar qualquer um dos servidores de uma atualização.</span><span class="sxs-lookup"><span data-stu-id="4adab-200">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="4adab-201">Execute **Get-CsPoolFabricState** para garantir que todos os grupos de roteamento tenham um principal e pelo menos um secundário; Isso irá confirmar se todos os usuários têm serviço.</span><span class="sxs-lookup"><span data-stu-id="4adab-201">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="4adab-202">Se alguns usuários tiverem serviços e outros não, execute **Get-CsPoolFabricState** com a opção – Verbose para verificar se há grupos de roteamento com réplicas ausentes.</span><span class="sxs-lookup"><span data-stu-id="4adab-202">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="4adab-203">Não reinicie o pool inteiro como a primeira etapa de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="4adab-203">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="4adab-204">Para obter mais informações sobre esse cmdlet, confira [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span><span class="sxs-lookup"><span data-stu-id="4adab-204">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="4adab-205">Verifique se todas as instâncias das janelas Visualizador de eventos ou monitor de desempenho estão fechadas para instalações/desinstalações da malha do Windows.</span><span class="sxs-lookup"><span data-stu-id="4adab-205">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="4adab-206">Alterar a configuração de um pool de front-end</span><span class="sxs-lookup"><span data-stu-id="4adab-206">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="4adab-207">Sempre que você adicionar servidores front-end a um pool ou removê-los do pool e depois publicar a nova topologia, siga estas diretrizes:</span><span class="sxs-lookup"><span data-stu-id="4adab-207">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="4adab-208">Após a publicação da nova topologia, você deve reiniciar cada servidor front-end no pool.</span><span class="sxs-lookup"><span data-stu-id="4adab-208">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="4adab-209">Reinicie todos, um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="4adab-209">Restart them one at a time.</span></span>

  - <span data-ttu-id="4adab-210">Se o pool inteiro estiver inoperante durante a alteração de configuração, execute o seguinte cmdlet após a publicação da nova topologia:</span><span class="sxs-lookup"><span data-stu-id="4adab-210">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="4adab-211">Se um servidor front-end falhar e for improvável de ser substituído por alguns dias ou mais, remova o servidor da topologia.</span><span class="sxs-lookup"><span data-stu-id="4adab-211">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="4adab-212">Adicione o novo servidor front-end à topologia quando ele estiver disponível novamente.</span><span class="sxs-lookup"><span data-stu-id="4adab-212">Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

