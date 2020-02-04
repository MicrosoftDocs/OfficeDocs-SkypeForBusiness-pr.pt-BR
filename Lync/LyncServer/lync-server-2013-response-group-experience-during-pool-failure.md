---
title: 'Lync Server 2013: Experiência do grupo de resposta durante falha no pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad00afac363642106019269e86111f61eaca504e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="fe172-102">Experiência do grupo de resposta no Lync Server 2013 durante falha no pool</span><span class="sxs-lookup"><span data-stu-id="fe172-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe172-103">_**Tópico da última modificação:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="fe172-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="fe172-104">Esta seção descreve detalhadamente como a atividade do grupo de resposta é afetada nos seguintes estágios:</span><span class="sxs-lookup"><span data-stu-id="fe172-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="fe172-105">Ocorre uma paralisação no pool primário, mas o failover ainda não foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="fe172-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="fe172-106">O serviço falha no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="fe172-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="fe172-107">O serviço de volta ao pool primário.</span><span class="sxs-lookup"><span data-stu-id="fe172-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="fe172-108">Experiência do usuário quando ocorre uma falha</span><span class="sxs-lookup"><span data-stu-id="fe172-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="fe172-109">Quando ocorre uma falha de pool ou site, mas o administrador ainda não iniciou o failover, a atividade do grupo de resposta é manipulada conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="fe172-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe172-110">Durante a recuperação de desastres, as chamadas se comportam de forma diferente dependendo se os grupos de resposta do pool primário foram importados para o pool de backup durante a recuperação</span><span class="sxs-lookup"><span data-stu-id="fe172-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="fe172-111">Na tabela a seguir, as referências a grupos de resposta importados significam que os grupos de resposta de pool primário foram importados para o pool de backup durante o modo de recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="fe172-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="fe172-112">Ocorre uma falha</span><span class="sxs-lookup"><span data-stu-id="fe172-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe172-113">Tipo de ação do usuário ou chamada</span><span class="sxs-lookup"><span data-stu-id="fe172-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="fe172-114">Durante a interrupção</span><span class="sxs-lookup"><span data-stu-id="fe172-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe172-115">Chamadas conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="fe172-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe172-116">As chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="fe172-117">As chamadas anônimas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe172-118">Chamadas em andamento ainda não conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="fe172-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="fe172-119">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe172-120">Novas chamadas</span><span class="sxs-lookup"><span data-stu-id="fe172-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe172-121">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="fe172-122">Se os grupos de resposta foram importados, as chamadas conectam-se ao pool de backup, mas os agentes hospedados no pool primário são inacessíveis.</span><span class="sxs-lookup"><span data-stu-id="fe172-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe172-123">Chamadas de agente em nome do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="fe172-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="fe172-124">O recurso está desativado durante este estágio.</span><span class="sxs-lookup"><span data-stu-id="fe172-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe172-125">Informações de entrada e agente do agente</span><span class="sxs-lookup"><span data-stu-id="fe172-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe172-126">Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="fe172-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="fe172-127">Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="fe172-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="fe172-128">Os grupos de agente importados não são exibidos no console do agente.</span><span class="sxs-lookup"><span data-stu-id="fe172-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe172-129">Configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="fe172-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe172-130">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="fe172-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="fe172-131">Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="fe172-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="fe172-132">Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="fe172-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="fe172-133">Experiência do usuário durante o failover</span><span class="sxs-lookup"><span data-stu-id="fe172-133">User Experience During Failover</span></span>

<span data-ttu-id="fe172-134">Quando um administrador invoca o failover para um pool de backup, a atividade do grupo de resposta é manipulada durante e após o failover conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="fe172-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="fe172-135">A primeira coluna descreve o tipo de atividade que pode estar ocorrendo.</span><span class="sxs-lookup"><span data-stu-id="fe172-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="fe172-136">A coluna do meio descreve como cada atividade é manipulada durante o tempo curto necessário para failover para o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="fe172-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="fe172-137">A última coluna descreve como a atividade é manipulada pela duração, após o término do processo de failover e o pool de backup se posicionar para o pool primário.</span><span class="sxs-lookup"><span data-stu-id="fe172-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe172-138">Durante a recuperação de desastres, as chamadas se comportam de forma diferente dependendo se os grupos de resposta do pool primário foram importados para o pool de backup durante a recuperação</span><span class="sxs-lookup"><span data-stu-id="fe172-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="fe172-139">Na tabela a seguir, as referências a grupos de resposta importados significam que os grupos de resposta de pool primário foram importados para o pool de backup durante o modo de recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="fe172-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="fe172-140">O failover é iniciado</span><span class="sxs-lookup"><span data-stu-id="fe172-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe172-141">Tipo de ação do usuário ou chamada</span><span class="sxs-lookup"><span data-stu-id="fe172-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="fe172-142">Durante o failover</span><span class="sxs-lookup"><span data-stu-id="fe172-142">During Failover</span></span></th>
<th><span data-ttu-id="fe172-143">Após a conclusão do failover</span><span class="sxs-lookup"><span data-stu-id="fe172-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe172-144">Chamadas conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="fe172-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe172-145">As chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="fe172-146">As chamadas anônimas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="fe172-147">As chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="fe172-148">Para grupos de resposta importados, chamadas anônimas que atingiram o pool de backup permanecerão conectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe172-149">Chamadas em andamento ainda não conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="fe172-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="fe172-150">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe172-151">Se os grupos de resposta não foram importados, nenhuma chamada está nesse status.</span><span class="sxs-lookup"><span data-stu-id="fe172-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="fe172-152">Para os grupos de resposta importados, as chamadas que atingiram o pool de backup permanecerão conectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe172-153">Novas chamadas</span><span class="sxs-lookup"><span data-stu-id="fe172-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe172-154">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="fe172-155">Para grupos de resposta importados, chamadas conectam-se ao pool de backup, mas os agentes hospedados no pool primário não são acessíveis.</span><span class="sxs-lookup"><span data-stu-id="fe172-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="fe172-156">Se os grupos de resposta não foram importados, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="fe172-157">Para grupos de resposta importados, chamadas conectam-se ao pool de backup.</span><span class="sxs-lookup"><span data-stu-id="fe172-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe172-158">Chamadas de agente em nome do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="fe172-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="fe172-159">O recurso está desativado durante este estágio</span><span class="sxs-lookup"><span data-stu-id="fe172-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe172-160">Se os grupos de resposta não foram importados, as chamadas falharão.</span><span class="sxs-lookup"><span data-stu-id="fe172-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="fe172-161">Para os grupos de resposta importados, as chamadas são bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="fe172-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe172-162">Informações de entrada e agente do agente</span><span class="sxs-lookup"><span data-stu-id="fe172-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe172-163">Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="fe172-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="fe172-164">Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="fe172-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="fe172-165">Grupos de agente importados são exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="fe172-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="fe172-166">Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="fe172-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="fe172-167">Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="fe172-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="fe172-168">Grupos de agente importados são exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="fe172-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe172-169">Configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="fe172-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe172-170">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="fe172-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="fe172-171">Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="fe172-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="fe172-172">Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="fe172-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="fe172-173">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="fe172-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="fe172-174">Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="fe172-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="fe172-175">Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="fe172-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="fe172-176">Experiência do usuário durante o failback</span><span class="sxs-lookup"><span data-stu-id="fe172-176">User Experience During Failback</span></span>

<span data-ttu-id="fe172-177">Quando um administrador invoca o failback para o pool primário, a atividade do grupo de resposta é manipulada durante e após o failback, conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="fe172-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe172-178">Durante a recuperação de desastres, as chamadas se comportam de forma diferente dependendo se os grupos de resposta do pool primário foram importados para o pool de backup durante a recuperação</span><span class="sxs-lookup"><span data-stu-id="fe172-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="fe172-179">Na tabela a seguir, as referências a grupos de resposta importados significam que os grupos de resposta de pool primário foram importados para o pool de backup durante o modo de recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="fe172-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="fe172-180">Tratamento de chamadas em failback</span><span class="sxs-lookup"><span data-stu-id="fe172-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe172-181">Tipo de ação do usuário ou chamada</span><span class="sxs-lookup"><span data-stu-id="fe172-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="fe172-182">Durante o failback</span><span class="sxs-lookup"><span data-stu-id="fe172-182">During Failback</span></span></th>
<th><span data-ttu-id="fe172-183">Após a conclusão do failback</span><span class="sxs-lookup"><span data-stu-id="fe172-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe172-184">Chamadas conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="fe172-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe172-185">As chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="fe172-186">Se os grupos de resposta não foram importados, não há chamadas anônimas nesse status.</span><span class="sxs-lookup"><span data-stu-id="fe172-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="fe172-187">Para grupos de resposta importados, as chamadas anônimas permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="fe172-188">As chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="fe172-189">Se os grupos de resposta não foram importados, não há chamadas anônimas nesse status.</span><span class="sxs-lookup"><span data-stu-id="fe172-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="fe172-190">Para grupos de resposta importados, as chamadas anônimas permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe172-191">Chamadas em andamento ainda não conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="fe172-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe172-192">Se os grupos de resposta não foram importados, nenhuma chamada está nesse status.</span><span class="sxs-lookup"><span data-stu-id="fe172-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="fe172-193">Para os grupos de resposta importados, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="fe172-194">Se os grupos de resposta não foram importados, nenhuma chamada está nesse status.</span><span class="sxs-lookup"><span data-stu-id="fe172-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="fe172-195">Para os grupos de resposta importados, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="fe172-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe172-196">Novas chamadas</span><span class="sxs-lookup"><span data-stu-id="fe172-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="fe172-197">Chamadas conectadas ao pool primário, mas os agentes hospedados no pool primário não são acessíveis.</span><span class="sxs-lookup"><span data-stu-id="fe172-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="fe172-198">Chamadas conectadas ao pool primário.</span><span class="sxs-lookup"><span data-stu-id="fe172-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe172-199">Chamadas de agente em nome do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="fe172-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="fe172-200">O recurso está desativado durante este estágio.</span><span class="sxs-lookup"><span data-stu-id="fe172-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="fe172-201">Chamadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="fe172-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe172-202">Informações de entrada e agente do agente</span><span class="sxs-lookup"><span data-stu-id="fe172-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe172-203">Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="fe172-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="fe172-204">Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="fe172-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="fe172-205">Grupos de agente importados são exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="fe172-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="fe172-206">Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="fe172-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="fe172-207">Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="fe172-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="fe172-208">Os grupos de agente importados não são exibidos no console do agente.</span><span class="sxs-lookup"><span data-stu-id="fe172-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe172-209">Configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="fe172-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fe172-210">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="fe172-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="fe172-211">Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="fe172-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="fe172-212">Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="fe172-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="fe172-213">Os grupos de resposta pertencentes ao pool primário podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="fe172-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="fe172-214">Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="fe172-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="fe172-215">Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="fe172-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

