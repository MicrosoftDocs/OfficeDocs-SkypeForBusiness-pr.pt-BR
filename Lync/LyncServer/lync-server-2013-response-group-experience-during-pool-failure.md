---
title: 'Lync Server 2013: Experiência do grupo de resposta durante falha no pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90911bebc7c3e60847f5b3fcb8f69523697af0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="c614d-102">Experiência do grupo de resposta no Lync Server 2013 durante falha no pool</span><span class="sxs-lookup"><span data-stu-id="c614d-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c614d-103">_**Tópico da última modificação:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="c614d-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="c614d-104">Esta seção descreve detalhadamente como a atividade do grupo de resposta é afetada nos seguintes estágios:</span><span class="sxs-lookup"><span data-stu-id="c614d-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="c614d-105">Ocorre uma paralisação no pool primário, mas o failover ainda não foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="c614d-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="c614d-106">O serviço falha no pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c614d-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="c614d-107">O serviço de volta ao pool primário.</span><span class="sxs-lookup"><span data-stu-id="c614d-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="c614d-108">Experiência do usuário quando ocorre uma falha</span><span class="sxs-lookup"><span data-stu-id="c614d-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="c614d-109">Quando ocorre uma falha de pool ou site, mas o administrador ainda não iniciou o failover, a atividade do grupo de resposta é manipulada conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c614d-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c614d-110">Durante a recuperação de desastres, as chamadas se comportam de forma diferente dependendo se os grupos de resposta do pool primário foram importados para o pool de backup durante a recuperação</span><span class="sxs-lookup"><span data-stu-id="c614d-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="c614d-111">Na tabela a seguir, as referências a grupos de resposta importados significam que os grupos de resposta de pool primário foram importados para o pool de backup durante o modo de recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="c614d-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="c614d-112">Ocorre uma falha</span><span class="sxs-lookup"><span data-stu-id="c614d-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c614d-113">Tipo de ação do usuário ou chamada</span><span class="sxs-lookup"><span data-stu-id="c614d-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="c614d-114">Durante a interrupção</span><span class="sxs-lookup"><span data-stu-id="c614d-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c614d-115">Chamadas conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="c614d-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c614d-116">As chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="c614d-117">As chamadas anônimas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c614d-118">Chamadas em andamento ainda não conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="c614d-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="c614d-119">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c614d-120">Novas chamadas</span><span class="sxs-lookup"><span data-stu-id="c614d-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c614d-121">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="c614d-122">Se os grupos de resposta foram importados, as chamadas conectam-se ao pool de backup, mas os agentes hospedados no pool primário são inacessíveis.</span><span class="sxs-lookup"><span data-stu-id="c614d-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c614d-123">Chamadas de agente em nome do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="c614d-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="c614d-124">O recurso está desativado durante este estágio.</span><span class="sxs-lookup"><span data-stu-id="c614d-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c614d-125">Informações de entrada e agente do agente</span><span class="sxs-lookup"><span data-stu-id="c614d-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c614d-126">Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="c614d-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="c614d-127">Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="c614d-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="c614d-128">Os grupos de agente importados não são exibidos no console do agente.</span><span class="sxs-lookup"><span data-stu-id="c614d-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c614d-129">Configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="c614d-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c614d-130">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="c614d-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="c614d-131">Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="c614d-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="c614d-132">Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c614d-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="c614d-133">Experiência do usuário durante o failover</span><span class="sxs-lookup"><span data-stu-id="c614d-133">User Experience During Failover</span></span>

<span data-ttu-id="c614d-134">Quando um administrador invoca o failover para um pool de backup, a atividade do grupo de resposta é manipulada durante e após o failover conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c614d-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="c614d-135">A primeira coluna descreve o tipo de atividade que pode estar ocorrendo.</span><span class="sxs-lookup"><span data-stu-id="c614d-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="c614d-136">A coluna do meio descreve como cada atividade é manipulada durante o tempo curto necessário para failover para o pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c614d-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="c614d-137">A última coluna descreve como a atividade é manipulada pela duração, após o término do processo de failover e o pool de backup se posicionar para o pool primário.</span><span class="sxs-lookup"><span data-stu-id="c614d-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c614d-138">Durante a recuperação de desastres, as chamadas se comportam de forma diferente dependendo se os grupos de resposta do pool primário foram importados para o pool de backup durante a recuperação</span><span class="sxs-lookup"><span data-stu-id="c614d-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="c614d-139">Na tabela a seguir, as referências a grupos de resposta importados significam que os grupos de resposta de pool primário foram importados para o pool de backup durante o modo de recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="c614d-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="c614d-140">O failover é iniciado</span><span class="sxs-lookup"><span data-stu-id="c614d-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c614d-141">Tipo de ação do usuário ou chamada</span><span class="sxs-lookup"><span data-stu-id="c614d-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="c614d-142">Durante o failover</span><span class="sxs-lookup"><span data-stu-id="c614d-142">During Failover</span></span></th>
<th><span data-ttu-id="c614d-143">Após a conclusão do failover</span><span class="sxs-lookup"><span data-stu-id="c614d-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c614d-144">Chamadas conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="c614d-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c614d-145">As chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="c614d-146">As chamadas anônimas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c614d-147">As chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="c614d-148">Para grupos de resposta importados, chamadas anônimas que atingiram o pool de backup permanecerão conectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c614d-149">Chamadas em andamento ainda não conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="c614d-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="c614d-150">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c614d-151">Se os grupos de resposta não foram importados, nenhuma chamada está nesse status.</span><span class="sxs-lookup"><span data-stu-id="c614d-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="c614d-152">Para os grupos de resposta importados, as chamadas que atingiram o pool de backup permanecerão conectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c614d-153">Novas chamadas</span><span class="sxs-lookup"><span data-stu-id="c614d-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c614d-154">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="c614d-155">Para grupos de resposta importados, chamadas conectam-se ao pool de backup, mas os agentes hospedados no pool primário não são acessíveis.</span><span class="sxs-lookup"><span data-stu-id="c614d-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c614d-156">Se os grupos de resposta não foram importados, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="c614d-157">Para grupos de resposta importados, chamadas conectam-se ao pool de backup.</span><span class="sxs-lookup"><span data-stu-id="c614d-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c614d-158">Chamadas de agente em nome do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="c614d-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="c614d-159">O recurso está desativado durante este estágio</span><span class="sxs-lookup"><span data-stu-id="c614d-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c614d-160">Se os grupos de resposta não foram importados, as chamadas falharão.</span><span class="sxs-lookup"><span data-stu-id="c614d-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="c614d-161">Para os grupos de resposta importados, as chamadas são bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="c614d-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c614d-162">Informações de entrada e agente do agente</span><span class="sxs-lookup"><span data-stu-id="c614d-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c614d-163">Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="c614d-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="c614d-164">Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="c614d-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="c614d-165">Grupos de agente importados são exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="c614d-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c614d-166">Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="c614d-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="c614d-167">Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="c614d-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="c614d-168">Grupos de agente importados são exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="c614d-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c614d-169">Configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="c614d-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c614d-170">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="c614d-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="c614d-171">Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="c614d-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="c614d-172">Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c614d-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c614d-173">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="c614d-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="c614d-174">Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="c614d-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="c614d-175">Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c614d-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="c614d-176">Experiência do usuário durante o failback</span><span class="sxs-lookup"><span data-stu-id="c614d-176">User Experience During Failback</span></span>

<span data-ttu-id="c614d-177">Quando um administrador invoca o failback para o pool primário, a atividade do grupo de resposta é manipulada durante e após o failback, conforme descrito na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c614d-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c614d-178">Durante a recuperação de desastres, as chamadas se comportam de forma diferente dependendo se os grupos de resposta do pool primário foram importados para o pool de backup durante a recuperação</span><span class="sxs-lookup"><span data-stu-id="c614d-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="c614d-179">Na tabela a seguir, as referências a grupos de resposta importados significam que os grupos de resposta de pool primário foram importados para o pool de backup durante o modo de recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="c614d-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="c614d-180">Tratamento de chamadas em failback</span><span class="sxs-lookup"><span data-stu-id="c614d-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c614d-181">Tipo de ação do usuário ou chamada</span><span class="sxs-lookup"><span data-stu-id="c614d-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="c614d-182">Durante o failback</span><span class="sxs-lookup"><span data-stu-id="c614d-182">During Failback</span></span></th>
<th><span data-ttu-id="c614d-183">Após a conclusão do failback</span><span class="sxs-lookup"><span data-stu-id="c614d-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c614d-184">Chamadas conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="c614d-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c614d-185">As chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="c614d-186">Se os grupos de resposta não foram importados, não há chamadas anônimas nesse status.</span><span class="sxs-lookup"><span data-stu-id="c614d-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="c614d-187">Para grupos de resposta importados, as chamadas anônimas permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c614d-188">As chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="c614d-189">Se os grupos de resposta não foram importados, não há chamadas anônimas nesse status.</span><span class="sxs-lookup"><span data-stu-id="c614d-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="c614d-190">Para grupos de resposta importados, as chamadas anônimas permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c614d-191">Chamadas em andamento ainda não conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="c614d-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c614d-192">Se os grupos de resposta não foram importados, nenhuma chamada está nesse status.</span><span class="sxs-lookup"><span data-stu-id="c614d-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="c614d-193">Para os grupos de resposta importados, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c614d-194">Se os grupos de resposta não foram importados, nenhuma chamada está nesse status.</span><span class="sxs-lookup"><span data-stu-id="c614d-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="c614d-195">Para os grupos de resposta importados, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="c614d-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c614d-196">Novas chamadas</span><span class="sxs-lookup"><span data-stu-id="c614d-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="c614d-197">Chamadas conectadas ao pool primário, mas os agentes hospedados no pool primário não são acessíveis.</span><span class="sxs-lookup"><span data-stu-id="c614d-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="c614d-198">Chamadas conectadas ao pool primário.</span><span class="sxs-lookup"><span data-stu-id="c614d-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c614d-199">Chamadas de agente em nome do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="c614d-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="c614d-200">O recurso está desativado durante este estágio.</span><span class="sxs-lookup"><span data-stu-id="c614d-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="c614d-201">Chamadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="c614d-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c614d-202">Informações de entrada e agente do agente</span><span class="sxs-lookup"><span data-stu-id="c614d-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c614d-203">Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="c614d-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="c614d-204">Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="c614d-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="c614d-205">Grupos de agente importados são exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="c614d-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c614d-206">Grupos de agente pertencentes ao pool primário podem ser visualizados no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="c614d-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="c614d-207">Grupos de agente pertencentes ao pool de backup podem ser visualizados no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="c614d-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="c614d-208">Os grupos de agente importados não são exibidos no console do agente.</span><span class="sxs-lookup"><span data-stu-id="c614d-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c614d-209">Configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="c614d-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c614d-210">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="c614d-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="c614d-211">Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="c614d-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="c614d-212">Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c614d-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c614d-213">Os grupos de resposta pertencentes ao pool primário podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="c614d-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="c614d-214">Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="c614d-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="c614d-215">Os grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração de grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c614d-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

