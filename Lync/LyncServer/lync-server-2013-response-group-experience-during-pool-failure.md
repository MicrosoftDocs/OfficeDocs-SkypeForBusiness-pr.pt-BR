---
title: Lync Server 2013 experiência do grupo de resposta durante falha do pool
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
ms.openlocfilehash: 2beb0a914fe5a2880926872ed1cab365fac988f0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="18fc5-102">Experiência do grupo de resposta no Lync Server 2013 durante falha do pool</span><span class="sxs-lookup"><span data-stu-id="18fc5-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18fc5-103">_**Última modificação do tópico:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="18fc5-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="18fc5-104">Essa seção descreve em detalhes como a atividade do grupo de resposta é afetada nos seguintes estágios:</span><span class="sxs-lookup"><span data-stu-id="18fc5-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="18fc5-105">Uma interrupção ocorre no pool primário, mas o failover ainda não foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="18fc5-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="18fc5-106">O serviço realizou um failover ao pool de backup.</span><span class="sxs-lookup"><span data-stu-id="18fc5-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="18fc5-107">O serviço realizou um failback ao pool primário.</span><span class="sxs-lookup"><span data-stu-id="18fc5-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="18fc5-108">Experiência do usuário quando ocorre interrupção</span><span class="sxs-lookup"><span data-stu-id="18fc5-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="18fc5-109">Quando ocorre uma interrupção de um pool ou site, mas o administrador ainda não iniciou o failover, a atividade do grupo de resposta é manipulada como descrito na seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="18fc5-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18fc5-p101">Durante a recuperação de desastre, as chamadas se comportam de forma diferente se os grupos de resposta do pool primário forem importados ao pool de backup durante a recuperação. Na tabela seguinte, as referências aos grupos de resposta importados significam que os grupos de resposta do pool primário foram importados ao pool de backup durante o modo de recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="18fc5-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="18fc5-112">Ocorre a interrupção</span><span class="sxs-lookup"><span data-stu-id="18fc5-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18fc5-113">Tipo de chamada ou ação do usuário</span><span class="sxs-lookup"><span data-stu-id="18fc5-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="18fc5-114">Durante a interrupção</span><span class="sxs-lookup"><span data-stu-id="18fc5-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18fc5-115">Chamadas conectadas ao agente</span><span class="sxs-lookup"><span data-stu-id="18fc5-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-116">Chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-117">Chamadas anônimas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18fc5-118">Chamadas em andamento ainda não conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="18fc5-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="18fc5-119">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18fc5-120">Novas chamadas</span><span class="sxs-lookup"><span data-stu-id="18fc5-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-121">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-122">Se um grupo de resposta for importado, as chamadas serão conectadas ao pool de backup, mas os agentes hospedados no pool primário serão inacessíveis.</span><span class="sxs-lookup"><span data-stu-id="18fc5-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18fc5-123">Os agente fazem chamadas em nome do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="18fc5-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="18fc5-124">O recurso é desabilitado durante esse estágio.</span><span class="sxs-lookup"><span data-stu-id="18fc5-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18fc5-125">Entrada do agente e informações do agente</span><span class="sxs-lookup"><span data-stu-id="18fc5-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-126">Os grupos de agente pertencentes ao pool primário podem ser exibidos no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="18fc5-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-127">Os grupos de agentes pertencentes ao pool de backup podem ser exibido no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="18fc5-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-128">Os grupos de agentes importados não são exibidos no console do agente.</span><span class="sxs-lookup"><span data-stu-id="18fc5-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18fc5-129">Configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="18fc5-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-130">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="18fc5-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-131">Os grupos de respostas pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="18fc5-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-132">Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18fc5-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="18fc5-133">Experiência do usuário durante o failover</span><span class="sxs-lookup"><span data-stu-id="18fc5-133">User Experience During Failover</span></span>

<span data-ttu-id="18fc5-p102">Quando um administrador chama um failover para um pool de backup, a atividade do grupo de resposta é manipulada durante e depois do failover, conforme descrito na tabela seguinte. A primeira coluna descreve o tipo de atividade que pode estar ocorrendo. A coluna do meio descreve como cada atividade é manipulada durante o breve período necessário para enviar o failover ao pool de backup. A última coluna descreve como a atividade é manipulada durante todo o período, após o processo de failover ser concluído e o pool de backup estar disponível para o pool primário.</span><span class="sxs-lookup"><span data-stu-id="18fc5-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18fc5-p103">Durante a recuperação de desastre, as chamadas se comportam de maneiras diferentes se os grupos de respostas do pool primário forem importados ao pool de backup durante a recuperação. Na seguinte tabela, as referências aos grupos de resposta importados significam que os grupos de respostas do pool primário foram importados ao pool de backup durante o modo de recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="18fc5-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="18fc5-140">O failover é iniciado</span><span class="sxs-lookup"><span data-stu-id="18fc5-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18fc5-141">Tipo de chamada ou ação do usuário</span><span class="sxs-lookup"><span data-stu-id="18fc5-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="18fc5-142">Durante o failover</span><span class="sxs-lookup"><span data-stu-id="18fc5-142">During Failover</span></span></th>
<th><span data-ttu-id="18fc5-143">Após a conclusão do failover</span><span class="sxs-lookup"><span data-stu-id="18fc5-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18fc5-144">Chamadas conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="18fc5-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-145">Chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-146">Chamadas anônimas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-147">Chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-148">Para grupos de respostas importados, as chamadas anônimas que alcançaram o pool de backup permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18fc5-149">Chamadas em andamento ainda não conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="18fc5-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="18fc5-150">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-151">Se os grupos de respostas não forem importados, não haverá chamadas nesse status.</span><span class="sxs-lookup"><span data-stu-id="18fc5-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-152">Para grupos de chamadas importados, as chamadas que alcançaram o pool de backup permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18fc5-153">Novas chamadas</span><span class="sxs-lookup"><span data-stu-id="18fc5-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-154">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-155">Para grupos de respostas importados, as chamadas se conectam ao pool de backup, mas os agentes hospedados no pool primário são inalcançáveis.</span><span class="sxs-lookup"><span data-stu-id="18fc5-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-156">Se os grupos de resposta não forem importados, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-157">Para grupos de respostas importados, as chamadas são conectadas ao pool de backup.</span><span class="sxs-lookup"><span data-stu-id="18fc5-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18fc5-158">O agente chama em nome do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="18fc5-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="18fc5-159">O recurso é desabilitado durante esse estágio</span><span class="sxs-lookup"><span data-stu-id="18fc5-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-160">Se os grupos de resposta não forem importados, as chamadas falham.</span><span class="sxs-lookup"><span data-stu-id="18fc5-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-161">Para grupos de resposta importados, as chamadas são bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18fc5-162">Entrada do agente e informação do agente</span><span class="sxs-lookup"><span data-stu-id="18fc5-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-163">Os grupos de agente pertencentes ao pool primário podem ser exibidos no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="18fc5-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-164">Os grupos de agentes pertencentes ao pool de backup podem ser exibido no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="18fc5-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-165">Os grupos de agentes importados são exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="18fc5-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-166">Os grupos de agentes pertencentes ao pool primário podem ser exibidos no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="18fc5-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-167">Os grupos de agentes pertencentes ao pool de backup podem ser exibido no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="18fc5-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-168">Os grupos de agentes importados são exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="18fc5-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18fc5-169">Configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="18fc5-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-170">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="18fc5-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-171">Os grupos de respostas pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="18fc5-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-172">Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18fc5-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-173">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back end, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="18fc5-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-174">Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="18fc5-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-175">Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18fc5-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="18fc5-176">Experiência do usuário durante o failback</span><span class="sxs-lookup"><span data-stu-id="18fc5-176">User Experience During Failback</span></span>

<span data-ttu-id="18fc5-177">Quando um administrador chama o failback para o pool primário, a atividade do grupo de resposta é manipulada durante e após o failback, conforme descritos na tabela seguinte.</span><span class="sxs-lookup"><span data-stu-id="18fc5-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18fc5-p104">Durante a recuperação de desastre, as chamadas se comportam de forma diferente dependendo se os grupos de resposta do pool primário foram importados ao pool de backup durante a recuperação. Na tabela seguinte, as referências dos grupos de respostas importados significam que os grupos de respostas do pool primário foram importados ao pool de backup durante o modo de recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="18fc5-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="18fc5-180">Administração de chamada no Failback</span><span class="sxs-lookup"><span data-stu-id="18fc5-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18fc5-181">Tipo de chamada ou ação do usuário</span><span class="sxs-lookup"><span data-stu-id="18fc5-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="18fc5-182">Durante o failback</span><span class="sxs-lookup"><span data-stu-id="18fc5-182">During Failback</span></span></th>
<th><span data-ttu-id="18fc5-183">Após a conclusão do failback</span><span class="sxs-lookup"><span data-stu-id="18fc5-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18fc5-184">Chamadas conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="18fc5-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-185">Chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-186">Se os grupos de respostas não forem importados, nenhuma chamada anônima estará nesse status.</span><span class="sxs-lookup"><span data-stu-id="18fc5-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-187">Para grupos de resposta importados, as chamadas anônimas permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-188">Chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-189">Se os grupos de respostas não forem importados, nenhuma chamada anônima estará nesse status.</span><span class="sxs-lookup"><span data-stu-id="18fc5-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-190">Para grupos de resposta importados, as chamadas anônimas permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18fc5-191">Chamadas em andamento ainda não conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="18fc5-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-192">Se os grupos de respostas não forem importados, nenhuma chamada estará nesse status.</span><span class="sxs-lookup"><span data-stu-id="18fc5-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-193">Para grupos de respostas importados, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-194">Se os grupos de respostas não forem importados, nenhuma chamada estará nesse status.</span><span class="sxs-lookup"><span data-stu-id="18fc5-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-195">Para grupos de respostas importados, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18fc5-196">Novas chamadas</span><span class="sxs-lookup"><span data-stu-id="18fc5-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="18fc5-197">Chamadas conectadas ao pool primário, mas os agentes hospedados no pool primário são inacessíveis.</span><span class="sxs-lookup"><span data-stu-id="18fc5-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="18fc5-198">Chamadas conectadas ao pool primário.</span><span class="sxs-lookup"><span data-stu-id="18fc5-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18fc5-199">Chamadas de agentes em nome do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="18fc5-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="18fc5-200">Recurso desabilitado durante esse estágio.</span><span class="sxs-lookup"><span data-stu-id="18fc5-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="18fc5-201">Chamadas bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="18fc5-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18fc5-202">Entrada do agente e informações do agente</span><span class="sxs-lookup"><span data-stu-id="18fc5-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-203">Os grupos de agente pertencentes ao pool primário podem ser exibidos no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="18fc5-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-204">Os grupos de agentes pertencentes ao pool de backup podem ser exibido no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="18fc5-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-205">Os grupos de agentes importados são exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="18fc5-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-206">Os grupos de agente pertencentes ao pool primário podem ser exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="18fc5-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-207">Os grupos de agentes pertencentes ao pool de backup podem ser exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="18fc5-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-208">Os grupos de agentes importados não são exibidos no console do agente.</span><span class="sxs-lookup"><span data-stu-id="18fc5-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18fc5-209">Configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="18fc5-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-210">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="18fc5-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-211">Os grupos de respostas pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="18fc5-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-212">Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18fc5-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="18fc5-213">Os grupos de respostas pertencentes ao pool primário podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="18fc5-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-214">Os grupos de respostas pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="18fc5-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="18fc5-215">Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18fc5-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

