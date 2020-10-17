---
title: 'Lync Server 2013: topologias e componentes para servidores front-end, mensagens instantâneas e presença'
description: 'Lync Server 2013: topologias e componentes para servidores front-end, mensagens instantâneas e presença.'
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
ms.openlocfilehash: 474911ef0e60d57151aa778688cf2e6a8e1bfcf7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550287"
---
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="dfcb2-103">Topologias e componentes para servidores front-end, mensagens instantâneas e presença no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfcb2-103">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfcb2-104">_**Última modificação do tópico:** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="dfcb2-104">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="dfcb2-105">Os únicos componentes necessários para mensagem instantânea (IM) e presença são:</span><span class="sxs-lookup"><span data-stu-id="dfcb2-105">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="dfcb2-p101">Os servidores do front-end da sua organização ou servidores do Standard Edition. As capacidades de IM e presença estão sempre habilitadas nestes servidores.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-p101">Your organization’s Front End Servers or Standard Edition servers. IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="dfcb2-108">Um balanceador de carga, se você tiver um pool de front-ends Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-108">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="dfcb2-109">Para obter mais informações, consulte [Load Balancing Requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfcb2-109">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="dfcb2-110">Planejando a implantação de pools de Front Ends</span><span class="sxs-lookup"><span data-stu-id="dfcb2-110">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="dfcb2-111">No Lync Server 2013, a arquitetura do pool de front-ends foi alterada e essas alterações afetam o modo como você deve planejar e manter seus pools de front-ends.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-111">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="dfcb2-112">Recomendamos que todos os pools de front-ends Enterprise Edition incluam pelo menos três servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-112">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="dfcb2-113">No Lync Server, a arquitetura dos pools de front-ends usa um modelo de sistemas distribuídos, com os dados de cada usuário mantidos em três servidores front-end no pool.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-113">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="dfcb2-114">Para obter mais informações sobre essa nova arquitetura, consulte [Topology Changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span><span class="sxs-lookup"><span data-stu-id="dfcb2-114">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="dfcb2-115">Se você não quiser implantar três servidores de front-end Enterprise Edition e quiser a recuperação de desastres, recomendamos usar o Lync Server Standard Edition e criar dois pools com um relacionamento de backup emparelhado.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-115">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="dfcb2-116">Isso fornecerá uma solução de recuperação de desastres com apenas dois servidores.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-116">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="dfcb2-117">Para obter mais informações, sobre topologias e recursos de alta disponibilidade e recuperação de desastres, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="dfcb2-117">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="dfcb2-118">Planejando o gerenciamento de pool de Front Ends</span><span class="sxs-lookup"><span data-stu-id="dfcb2-118">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="dfcb2-119">Para pools de front-ends, siga as diretrizes desta seção.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-119">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="dfcb2-120">Garantir que os pools sejam funcionais</span><span class="sxs-lookup"><span data-stu-id="dfcb2-120">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="dfcb2-121">Com o novo modelo distribuído para pools de front-ends, determinados números de servidores de um pool devem estar em execução para que o pool funcione.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-121">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="dfcb2-122">Há dois modos de perda para um pool</span><span class="sxs-lookup"><span data-stu-id="dfcb2-122">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="dfcb2-123">Perda de quorum de nível de grupo de roteamento, causada por servidores de réplica insuficientes para um grupo de roteamento específico.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-123">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="dfcb2-124">Um grupo de roteamento é uma agregação de um conjunto de usuários hospedados no pool.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-124">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="dfcb2-125">Cada grupo de roteamento tem três réplicas no pool: uma principal e duas segundas.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-125">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="dfcb2-126">Perda de quorum no nível do pool, causada quando não há servidores semente suficientes em execução no pool.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-126">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="dfcb2-127">Perda de quórum no nível do grupo de roteamento</span><span class="sxs-lookup"><span data-stu-id="dfcb2-127">Routing Group Level quorum loss</span></span>

<span data-ttu-id="dfcb2-128">Na primeira vez que você iniciar um novo pool de front-ends, é essencial que 85% dos servidores estejam em funcionamento, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-128">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="dfcb2-129">Se menos servidores estiverem em execução, os serviços poderão estar presos no estado inicial e o pool pode não iniciar.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-129">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfcb2-130">Número total de servidores no pool</span><span class="sxs-lookup"><span data-stu-id="dfcb2-130">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="dfcb2-131">Número de servidores que devem estar em execução para que o pool seja iniciado pela primeira vez</span><span class="sxs-lookup"><span data-stu-id="dfcb2-131">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfcb2-132">duas</span><span class="sxs-lookup"><span data-stu-id="dfcb2-132">2</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-133">1</span><span class="sxs-lookup"><span data-stu-id="dfcb2-133">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfcb2-134">3D</span><span class="sxs-lookup"><span data-stu-id="dfcb2-134">3</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-135">3D</span><span class="sxs-lookup"><span data-stu-id="dfcb2-135">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfcb2-136">4 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-136">4</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-137">3D</span><span class="sxs-lookup"><span data-stu-id="dfcb2-137">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfcb2-138">5 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-138">5</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-139">4 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-139">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfcb2-140">6 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-140">6</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-141">5 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-141">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfcb2-142">7 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-142">7</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-143">5 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-143">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfcb2-144">8 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-144">8</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-145">6 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-145">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfcb2-146">9 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-146">9</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-147">7 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-147">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfcb2-148">10 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-148">10</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-149">8 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-149">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfcb2-150">11</span><span class="sxs-lookup"><span data-stu-id="dfcb2-150">11</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-151">9 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-151">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfcb2-152">12 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-152">12</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-153">10 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-153">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dfcb2-154">Cada vez subsequente que o pool é iniciado, 85% dos servidores devem ser iniciados (conforme mostrado na tabela anterior).</span><span class="sxs-lookup"><span data-stu-id="dfcb2-154">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="dfcb2-155">Se esse número de servidores não puder ser iniciado (mas servidores suficientes podem ser iniciados para que você não esteja em perda de quorum no nível do pool), você pode usar o cmdlet **Reset-CsPoolRegistrarState – resettype QuorumLossRecovery** para permitir que o pool se recupere dessa perda de quorum de nível do grupo de roteamento e faça o andamento.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-155">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="dfcb2-156">Para obter mais informações sobre como usar esse cmdlet, consulte [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span><span class="sxs-lookup"><span data-stu-id="dfcb2-156">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dfcb2-157">Como o Lync Server usa o banco de dados SQL principal como testemunha, se você desligar o banco de dados primário e alternar para a cópia espelho e desligar servidores front-end suficientes para que não sejam executados de acordo com a tabela anterior, todo o pool será desativado.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-157">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="dfcb2-158">Para obter mais informações, consulte <A href="https://go.microsoft.com/fwlink/?linkid=393672">testemunha de espelhamento de banco de dados</A>.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-158">For more information, see <A href="https://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="dfcb2-159">Perda de quorum no nível do pool</span><span class="sxs-lookup"><span data-stu-id="dfcb2-159">Pool-level quorum loss</span></span>

<span data-ttu-id="dfcb2-160">Para que um pool de front-ends funcione, ele não pode ficar em perda de quorum no nível do pool.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-160">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="dfcb2-161">Se o número de servidores em execução estiver abaixo do nível funcional, conforme mostrado na tabela a seguir, os servidores restantes do pool serão interrompidos em todos os serviços do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-161">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="dfcb2-162">Observe que os números na tabela a seguir pressupõem que os servidores de back-end no pool estão em execução.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-162">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfcb2-163">Número total de Servidores de Front End no pool</span><span class="sxs-lookup"><span data-stu-id="dfcb2-163">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="dfcb2-164">Número de servidores que devem estar em execução para o pool ser funcional</span><span class="sxs-lookup"><span data-stu-id="dfcb2-164">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfcb2-165">duas</span><span class="sxs-lookup"><span data-stu-id="dfcb2-165">2</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-166">1</span><span class="sxs-lookup"><span data-stu-id="dfcb2-166">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfcb2-167">3-4</span><span class="sxs-lookup"><span data-stu-id="dfcb2-167">3-4</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-168">Qualquer 2</span><span class="sxs-lookup"><span data-stu-id="dfcb2-168">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfcb2-169">5-6</span><span class="sxs-lookup"><span data-stu-id="dfcb2-169">5-6</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-170">Qualquer 3</span><span class="sxs-lookup"><span data-stu-id="dfcb2-170">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfcb2-171">7 </span><span class="sxs-lookup"><span data-stu-id="dfcb2-171">7</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-172">Qualquer 4</span><span class="sxs-lookup"><span data-stu-id="dfcb2-172">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfcb2-173">8-9</span><span class="sxs-lookup"><span data-stu-id="dfcb2-173">8-9</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-174">Quatro dos primeiros sete servidores</span><span class="sxs-lookup"><span data-stu-id="dfcb2-174">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfcb2-175">10-12</span><span class="sxs-lookup"><span data-stu-id="dfcb2-175">10-12</span></span></p></td>
<td><p><span data-ttu-id="dfcb2-176">Qualquer 5 dos primeiros 9 servidores</span><span class="sxs-lookup"><span data-stu-id="dfcb2-176">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dfcb2-177">Na tabela anterior, os "primeiros servidores" são os servidores que foram inicialmente exibidos, cronologicamente, quando o pool foi iniciado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-177">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="dfcb2-178">Para determinar esses servidores, você pode usar o cmdlet **Get-CsComputer** com a opção **– PoolFqdn** .</span><span class="sxs-lookup"><span data-stu-id="dfcb2-178">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="dfcb2-179">Este cmdlet mostrará os servidores na ordem em que eles aparecem na topologia e aqueles que estão na parte superior da lista são os primeiros servidores.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-179">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="dfcb2-180">Pool de Front-Ends com dois Servidores de Front End</span><span class="sxs-lookup"><span data-stu-id="dfcb2-180">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="dfcb2-p112">Não recomendamos implantar um pool de Front Ends que contém apenas dois Servidores de Front End. Se você precisar implantar este tipo de pool, siga as seguintes orientações:</span><span class="sxs-lookup"><span data-stu-id="dfcb2-p112">We do not recommend deploying a Front End pool that contains only two Front End Servers. If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="dfcb2-p113">Se um dos dois Servidores de Front End ficar inativo, você deve ativá-lo assim que possível. Da mesma forma, se você precisar atualizar um dos dois servidores, ative-o assim que a atualização terminar.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-p113">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can. Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="dfcb2-185">Se por alguma razão você precisar desativar ambos os servidores ao mesmo tempo, realize o seguinte procedimento quando o tempo de inatividade do pool for concluído:</span><span class="sxs-lookup"><span data-stu-id="dfcb2-185">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="dfcb2-186">A prática recomendada é reiniciar ambos os servidores front-end ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-186">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="dfcb2-187">Se os dois servidores não podem ser reinicidos ao mesmo tempo, você deve ativá-los na ordem contrária em que foram desativados.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-187">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="dfcb2-188">Se você não puder ativá-los nesta ordem, use o seguinte cmdlet antes de ativar o pool:</span><span class="sxs-lookup"><span data-stu-id="dfcb2-188">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="dfcb2-189">Etapas adicionais para garantir que os pools sejam funcionais</span><span class="sxs-lookup"><span data-stu-id="dfcb2-189">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="dfcb2-190">Você deve observar alguns outros fatores para garantir que seus pools de front-ends permaneçam funcionais.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-190">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="dfcb2-191">Ao migrar usuários para o pool pela primeira vez, certifique-se de que pelo menos três dos Servidores de Front End estão em execução.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-191">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="dfcb2-192">Se você estabelecer um relacionamento de emparelhamento entre este e um outro pool para fins de recuperação de desastres, após estabelecer esse relacionamento você deve garantir que o pool tenha três Servidores de Front End em execução simultânea em algum momento para sincronizar adequadamente os dados com o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-192">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="dfcb2-193">Para obter mais informações sobre emparelhamento de pool e recursos de recuperação de desastre, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="dfcb2-193">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="dfcb2-194">Melhorar a confiabilidade das atualizações de pool</span><span class="sxs-lookup"><span data-stu-id="dfcb2-194">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="dfcb2-195">Quando precisar atualizar ou corrigir os servidores em um pool de front-ends, siga o fluxo de trabalho mostrado em [atualizar ou atualizar servidores front-end no Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)e as seguintes diretrizes:</span><span class="sxs-lookup"><span data-stu-id="dfcb2-195">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="dfcb2-196">Quando você migra de um domínio de atualização para outro para atualizações (seguindo o fluxo de trabalho em [atualizar ou atualizar servidores front-end no Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), você usará o cmdlet **Get-CsPoolUpgradeReadinessState** e verificará se o estado está pronto.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-196">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="dfcb2-197">A adição de uma espera de 20 minutos entre cada domínio de atualização após o alcance de "pronto" tornará as atualizações mais confiáveis.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-197">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="dfcb2-198">Se ele **não estiver pronto** durante os 20 minutos, reinicie o timer de 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-198">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="dfcb2-199">Além disso, você pode executar o cmdlet **Get-CsPoolFabricState** antes e depois de iniciar o intervalo de 20 minutos e certificar-se de que não haja alterações nas primidades e nos secundários de grupos de roteamento.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-199">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="dfcb2-200">Não vá para o próximo domínio de atualização se qualquer um dos servidores no último domínio de atualização corrigido estiver preso ou não for reiniciado.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-200">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="dfcb2-201">Isso também se aplica se não for possível iniciar qualquer um dos servidores de uma atualização.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-201">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="dfcb2-202">Execute **Get-CsPoolFabricState** para certificar-se de que todos os grupos de roteamento têm um primário e pelo menos um secundário; isso confirmará se todos os usuários possuem serviço.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-202">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="dfcb2-203">Se alguns usuários tiverem serviços e outros não, execute **Get-CsPoolFabricState** com a opção – Verbose para verificar os grupos de roteamento que possuem réplicas ausentes.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-203">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="dfcb2-204">Não reinicia o pool inteiro como a primeira etapa de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-204">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="dfcb2-205">Para obter mais informações sobre esse cmdlet, consulte [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span><span class="sxs-lookup"><span data-stu-id="dfcb2-205">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="dfcb2-206">Certifique-se de que todas as instâncias das janelas Visualizador de eventos ou monitor de desempenho estejam fechadas para instalar/desinstalar o Windows Fabric.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-206">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="dfcb2-207">Alterando a configuração de um Pool de Front Ends</span><span class="sxs-lookup"><span data-stu-id="dfcb2-207">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="dfcb2-208">Sempre que você adicionar ou remover Servidores de Front End de um pool, e depois publicar a nova topologia, siga essas orientações:</span><span class="sxs-lookup"><span data-stu-id="dfcb2-208">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="dfcb2-209">Após a publicação da nova topologia, você deve reiniciar cada servidor de front-end no pool.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-209">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="dfcb2-210">Reinicie todos eles, um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-210">Restart them one at a time.</span></span>

  - <span data-ttu-id="dfcb2-211">Se todo o pool ficou desativado durante a alteração nas configurações, execute o seguinte cmdlet depois de publicar a nova topologia:</span><span class="sxs-lookup"><span data-stu-id="dfcb2-211">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="dfcb2-p119">Se um Servidor de Front End falhar e não puder ser substituído em alguns dias ou mais, remova o servidor da topologia. Adicione o novo Servidor de Front End à topologia quando estiver disponível novamente.</span><span class="sxs-lookup"><span data-stu-id="dfcb2-p119">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology. Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

