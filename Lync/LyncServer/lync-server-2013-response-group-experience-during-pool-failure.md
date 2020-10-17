---
title: Lync Server 2013 experiência do grupo de resposta durante falha do pool
description: Lync Server 2013 experiência do grupo de resposta durante falha no pool.
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
ms.openlocfilehash: 7d8d5904bc6934d4c330202bafa66d6dd8a16ff5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564567"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="3571c-103">Experiência do grupo de resposta no Lync Server 2013 durante falha do pool</span><span class="sxs-lookup"><span data-stu-id="3571c-103">Response group experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3571c-104">_**Última modificação do tópico:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="3571c-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="3571c-105">Essa seção descreve em detalhes como a atividade do grupo de resposta é afetada nos seguintes estágios:</span><span class="sxs-lookup"><span data-stu-id="3571c-105">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="3571c-106">Uma interrupção ocorre no pool primário, mas o failover ainda não foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="3571c-106">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="3571c-107">O serviço realizou um failover ao pool de backup.</span><span class="sxs-lookup"><span data-stu-id="3571c-107">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="3571c-108">O serviço realizou um failback ao pool primário.</span><span class="sxs-lookup"><span data-stu-id="3571c-108">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="3571c-109">Experiência do usuário quando ocorre interrupção</span><span class="sxs-lookup"><span data-stu-id="3571c-109">User Experience When Outage Occurs</span></span>

<span data-ttu-id="3571c-110">Quando ocorre uma interrupção de um pool ou site, mas o administrador ainda não iniciou o failover, a atividade do grupo de resposta é manipulada como descrito na seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="3571c-110">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3571c-p101">Durante a recuperação de desastre, as chamadas se comportam de forma diferente se os grupos de resposta do pool primário forem importados ao pool de backup durante a recuperação. Na tabela seguinte, as referências aos grupos de resposta importados significam que os grupos de resposta do pool primário foram importados ao pool de backup durante o modo de recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="3571c-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="3571c-113">Ocorre a interrupção</span><span class="sxs-lookup"><span data-stu-id="3571c-113">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3571c-114">Tipo de chamada ou ação do usuário</span><span class="sxs-lookup"><span data-stu-id="3571c-114">Type of call or user action</span></span></th>
<th><span data-ttu-id="3571c-115">Durante a interrupção</span><span class="sxs-lookup"><span data-stu-id="3571c-115">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3571c-116">Chamadas conectadas ao agente</span><span class="sxs-lookup"><span data-stu-id="3571c-116">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3571c-117">Chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-117">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="3571c-118">Chamadas anônimas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-118">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3571c-119">Chamadas em andamento ainda não conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="3571c-119">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="3571c-120">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-120">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3571c-121">Novas chamadas</span><span class="sxs-lookup"><span data-stu-id="3571c-121">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3571c-122">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-122">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="3571c-123">Se um grupo de resposta for importado, as chamadas serão conectadas ao pool de backup, mas os agentes hospedados no pool primário serão inacessíveis.</span><span class="sxs-lookup"><span data-stu-id="3571c-123">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3571c-124">Os agente fazem chamadas em nome do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="3571c-124">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="3571c-125">O recurso é desabilitado durante esse estágio.</span><span class="sxs-lookup"><span data-stu-id="3571c-125">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3571c-126">Entrada do agente e informações do agente</span><span class="sxs-lookup"><span data-stu-id="3571c-126">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3571c-127">Os grupos de agentes pertencentes ao pool primário podem ser exibidos no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="3571c-127">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="3571c-128">Os grupos de agentes pertencentes ao pool de backup podem ser exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="3571c-128">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="3571c-129">Os grupos de agentes importados não são exibidos no console do agente.</span><span class="sxs-lookup"><span data-stu-id="3571c-129">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3571c-130">Configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="3571c-130">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3571c-131">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="3571c-131">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="3571c-132">Os grupos de respostas pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="3571c-132">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="3571c-133">Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3571c-133">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="3571c-134">Experiência do usuário durante o failover</span><span class="sxs-lookup"><span data-stu-id="3571c-134">User Experience During Failover</span></span>

<span data-ttu-id="3571c-p102">Quando um administrador chama um failover para um pool de backup, a atividade do grupo de resposta é manipulada durante e depois do failover, conforme descrito na tabela seguinte. A primeira coluna descreve o tipo de atividade que pode estar ocorrendo. A coluna do meio descreve como cada atividade é manipulada durante o breve período necessário para enviar o failover ao pool de backup. A última coluna descreve como a atividade é manipulada durante todo o período, após o processo de failover ser concluído e o pool de backup estar disponível para o pool primário.</span><span class="sxs-lookup"><span data-stu-id="3571c-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3571c-p103">Durante a recuperação de desastre, as chamadas se comportam de maneiras diferentes se os grupos de respostas do pool primário forem importados ao pool de backup durante a recuperação. Na seguinte tabela, as referências aos grupos de resposta importados significam que os grupos de respostas do pool primário foram importados ao pool de backup durante o modo de recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="3571c-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="3571c-141">O failover é iniciado</span><span class="sxs-lookup"><span data-stu-id="3571c-141">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3571c-142">Tipo de chamada ou ação do usuário</span><span class="sxs-lookup"><span data-stu-id="3571c-142">Type of call or user action</span></span></th>
<th><span data-ttu-id="3571c-143">Durante o failover</span><span class="sxs-lookup"><span data-stu-id="3571c-143">During Failover</span></span></th>
<th><span data-ttu-id="3571c-144">Após a conclusão do failover</span><span class="sxs-lookup"><span data-stu-id="3571c-144">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3571c-145">Chamadas conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="3571c-145">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3571c-146">Chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-146">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="3571c-147">Chamadas anônimas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-147">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="3571c-148">Chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-148">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="3571c-149">Para grupos de respostas importados, as chamadas anônimas que alcançaram o pool de backup permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-149">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3571c-150">Chamadas em andamento ainda não conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="3571c-150">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="3571c-151">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-151">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3571c-152">Se os grupos de respostas não forem importados, não haverá chamadas nesse status.</span><span class="sxs-lookup"><span data-stu-id="3571c-152">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="3571c-153">Para grupos de chamadas importados, as chamadas que alcançaram o pool de backup permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-153">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3571c-154">Novas chamadas</span><span class="sxs-lookup"><span data-stu-id="3571c-154">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3571c-155">As chamadas são desconectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-155">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="3571c-156">Para grupos de respostas importados, as chamadas se conectam ao pool de backup, mas os agentes hospedados no pool primário são inalcançáveis.</span><span class="sxs-lookup"><span data-stu-id="3571c-156">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="3571c-157">Se os grupos de resposta não forem importados, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-157">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="3571c-158">Para grupos de respostas importados, as chamadas são conectadas ao pool de backup.</span><span class="sxs-lookup"><span data-stu-id="3571c-158">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3571c-159">O agente chama em nome do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="3571c-159">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="3571c-160">O recurso é desabilitado durante esse estágio</span><span class="sxs-lookup"><span data-stu-id="3571c-160">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3571c-161">Se os grupos de resposta não forem importados, as chamadas falham.</span><span class="sxs-lookup"><span data-stu-id="3571c-161">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="3571c-162">Para grupos de resposta importados, as chamadas são bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="3571c-162">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3571c-163">Entrada do agente e informação do agente</span><span class="sxs-lookup"><span data-stu-id="3571c-163">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3571c-164">Os grupos de agentes pertencentes ao pool primário podem ser exibidos no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="3571c-164">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="3571c-165">Os grupos de agentes pertencentes ao pool de backup podem ser exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="3571c-165">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="3571c-166">Os grupos de agentes importados são exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="3571c-166">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="3571c-167">Os grupos de agentes pertencentes ao pool primário podem ser exibidos no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="3571c-167">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="3571c-168">Os grupos de agentes pertencentes ao pool de backup podem ser exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="3571c-168">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="3571c-169">Os grupos de agentes importados são exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="3571c-169">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3571c-170">Configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="3571c-170">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3571c-171">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="3571c-171">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="3571c-172">Os grupos de respostas pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="3571c-172">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="3571c-173">Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3571c-173">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="3571c-174">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back end, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="3571c-174">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="3571c-175">Os grupos de resposta pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="3571c-175">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="3571c-176">Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3571c-176">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="3571c-177">Experiência do usuário durante o failback</span><span class="sxs-lookup"><span data-stu-id="3571c-177">User Experience During Failback</span></span>

<span data-ttu-id="3571c-178">Quando um administrador chama o failback para o pool primário, a atividade do grupo de resposta é manipulada durante e após o failback, conforme descritos na tabela seguinte.</span><span class="sxs-lookup"><span data-stu-id="3571c-178">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3571c-p104">Durante a recuperação de desastre, as chamadas se comportam de forma diferente dependendo se os grupos de resposta do pool primário foram importados ao pool de backup durante a recuperação. Na tabela seguinte, as referências dos grupos de respostas importados significam que os grupos de respostas do pool primário foram importados ao pool de backup durante o modo de recuperação de desastre.</span><span class="sxs-lookup"><span data-stu-id="3571c-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="3571c-181">Administração de chamada no Failback</span><span class="sxs-lookup"><span data-stu-id="3571c-181">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3571c-182">Tipo de chamada ou ação do usuário</span><span class="sxs-lookup"><span data-stu-id="3571c-182">Type of call or user action</span></span></th>
<th><span data-ttu-id="3571c-183">Durante o failback</span><span class="sxs-lookup"><span data-stu-id="3571c-183">During Failback</span></span></th>
<th><span data-ttu-id="3571c-184">Após a conclusão do failback</span><span class="sxs-lookup"><span data-stu-id="3571c-184">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3571c-185">Chamadas conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="3571c-185">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3571c-186">Chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-186">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="3571c-187">Se os grupos de respostas não forem importados, nenhuma chamada anônima estará nesse status.</span><span class="sxs-lookup"><span data-stu-id="3571c-187">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="3571c-188">Para grupos de resposta importados, as chamadas anônimas permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-188">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="3571c-189">Chamadas normais permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-189">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="3571c-190">Se os grupos de respostas não forem importados, nenhuma chamada anônima estará nesse status.</span><span class="sxs-lookup"><span data-stu-id="3571c-190">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="3571c-191">Para grupos de resposta importados, as chamadas anônimas permanecem conectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-191">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3571c-192">Chamadas em andamento ainda não conectadas a um agente</span><span class="sxs-lookup"><span data-stu-id="3571c-192">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3571c-193">Se os grupos de respostas não forem importados, nenhuma chamada estará nesse status.</span><span class="sxs-lookup"><span data-stu-id="3571c-193">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="3571c-194">Para grupos de respostas importados, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-194">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="3571c-195">Se os grupos de respostas não forem importados, nenhuma chamada estará nesse status.</span><span class="sxs-lookup"><span data-stu-id="3571c-195">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="3571c-196">Para grupos de respostas importados, as chamadas serão desconectadas.</span><span class="sxs-lookup"><span data-stu-id="3571c-196">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3571c-197">Novas chamadas</span><span class="sxs-lookup"><span data-stu-id="3571c-197">New calls</span></span></p></td>
<td><p><span data-ttu-id="3571c-198">Chamadas conectadas ao pool primário, mas os agentes hospedados no pool primário são inacessíveis.</span><span class="sxs-lookup"><span data-stu-id="3571c-198">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="3571c-199">Chamadas conectadas ao pool primário.</span><span class="sxs-lookup"><span data-stu-id="3571c-199">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3571c-200">Chamadas de agentes em nome do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="3571c-200">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="3571c-201">Recurso desabilitado durante esse estágio.</span><span class="sxs-lookup"><span data-stu-id="3571c-201">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="3571c-202">Chamadas bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="3571c-202">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3571c-203">Entrada do agente e informações do agente</span><span class="sxs-lookup"><span data-stu-id="3571c-203">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3571c-204">Os grupos de agentes pertencentes ao pool primário podem ser exibidos no console do agente, mas os agentes não podem entrar.</span><span class="sxs-lookup"><span data-stu-id="3571c-204">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="3571c-205">Os grupos de agentes pertencentes ao pool de backup podem ser exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="3571c-205">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="3571c-206">Os grupos de agentes importados são exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="3571c-206">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="3571c-207">Os grupos de agente pertencentes ao pool primário podem ser exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="3571c-207">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="3571c-208">Os grupos de agentes pertencentes ao pool de backup podem ser exibidos no console do agente e os agentes podem entrar.</span><span class="sxs-lookup"><span data-stu-id="3571c-208">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="3571c-209">Os grupos de agentes importados não são exibidos no console do agente.</span><span class="sxs-lookup"><span data-stu-id="3571c-209">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3571c-210">Configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="3571c-210">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="3571c-211">Os grupos de resposta pertencentes ao pool primário podem ser exibidos, dependendo da disponibilidade do banco de dados back-end do pool primário, mas não podem ser modificados.</span><span class="sxs-lookup"><span data-stu-id="3571c-211">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="3571c-212">Os grupos de respostas pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="3571c-212">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="3571c-213">Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3571c-213">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="3571c-214">Os grupos de respostas pertencentes ao pool primário podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="3571c-214">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="3571c-215">Os grupos de respostas pertencentes ao pool de backup podem ser exibidos e modificados.</span><span class="sxs-lookup"><span data-stu-id="3571c-215">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="3571c-216">Grupos de resposta importados não podem ser exibidos com o painel de controle do Lync Server ou com a ferramenta de configuração do grupo de resposta, mas podem ser configurados usando cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3571c-216">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

