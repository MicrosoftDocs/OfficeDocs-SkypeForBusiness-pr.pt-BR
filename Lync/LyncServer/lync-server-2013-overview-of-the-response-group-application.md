---
title: 'Lync Server 2013: visão geral do aplicativo grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df3bb7b9260e85326718bf388da977833c6e87ea
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="81af9-102">Visão geral do aplicativo grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81af9-102">Overview of the Response Group application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81af9-103">_**Última modificação do tópico:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="81af9-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="81af9-104">Quando um chamador chama um grupo de resposta, a chamada é roteada para um agente com base em um grupo de busca ou mas respostas do chamador para as perguntas de IVR (resposta de voz interativa).</span><span class="sxs-lookup"><span data-stu-id="81af9-104">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="81af9-105">O aplicativo grupo de resposta usa métodos de roteamento de grupo de resposta padrão para rotear a chamada para o próximo agente disponível.</span><span class="sxs-lookup"><span data-stu-id="81af9-105">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="81af9-106">Os métodos de roteamento de chamada incluem serial, ocioso por mais tempo, paralelo, round robin, e encaminhamento de Atendente (ou seja, todos os agentes são chamados ao mesmo tempo a cada chamada de entrada, independentemente de sua presença atual).</span><span class="sxs-lookup"><span data-stu-id="81af9-106">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="81af9-107">Se não houverem agentes disponíveis, a chamada será mantida em uma fila até que um agente esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="81af9-107">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="81af9-108">Enquanto está na fila, o chamador ouve música até um agente disponível aceitar a chamada.</span><span class="sxs-lookup"><span data-stu-id="81af9-108">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="81af9-109">Se a fila estiver cheia ou se a chamada expirar enquanto estiver na fila, o chamador poderá ouvir uma mensagem e está desconectado ou transferido para um destino diferente.</span><span class="sxs-lookup"><span data-stu-id="81af9-109">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="81af9-110">Quando um agente aceita a chamada, o chamador pode ou não ser capaz de ver a identidade do agente, dependendo de como o administrador configura o grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="81af9-110">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="81af9-111">Os agentes podem ser formais, o que significa que eles devem entrar no grupo antes de aceitar chamadas encaminhadas para o grupo, ou informais, que significa que eles não precisam entrar no grupo para aceitar chamadas.</span><span class="sxs-lookup"><span data-stu-id="81af9-111">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81af9-p102">Apenas os usuários locais podem ser operadores. Se um operador for movido de local para online, a chamada do grupo de resposta não será mais roteada para ele.</span><span class="sxs-lookup"><span data-stu-id="81af9-p102">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="81af9-114">O aplicativo grupo de resposta usa um serviço interno, chamado fazer correspondência, para enfileirar chamadas e localizar agentes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="81af9-114">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="81af9-115">Cada computador que executa o aplicativo grupo de resposta executa o serviço de correspondência, mas apenas um serviço de correspondência por pool do Lync Server está ativo por vez – os outros são passivos.</span><span class="sxs-lookup"><span data-stu-id="81af9-115">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="81af9-116">Se o serviço Correspondência ativo ficar indisponível durante uma paralisação não planejada, um dos serviços Correspondência passivos ficará ativo.</span><span class="sxs-lookup"><span data-stu-id="81af9-116">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="81af9-117">O aplicativo grupo de resposta faz o melhor para garantir que o roteamento de chamadas e o enfileiramento continuem sem interrupção.</span><span class="sxs-lookup"><span data-stu-id="81af9-117">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="81af9-118">No entanto, quando ocorre uma transição do serviço Correspondência, todas as chamadas em transferência no momento são perdidas.</span><span class="sxs-lookup"><span data-stu-id="81af9-118">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="81af9-119">Por exemplo, se a transição for devido ao servidor de front-end ser desativado, todas as chamadas que estão sendo tratadas no momento pela correspondência ativa, fazendo o serviço nesse servidor de front-end também serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="81af9-119">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="81af9-120">No Lync Server 2013, duas funções de gerenciamento estão disponíveis para gerenciar grupos de resposta: gerente de grupo de resposta e administrador de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="81af9-120">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="81af9-121">Os administradores do grupo de resposta podem gerenciar qualquer aspecto de qualquer grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="81af9-121">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="81af9-122">Os gerentes do grupo de resposta podem gerenciar apenas determinados aspectos e apenas os grupos de resposta que eles possuem.</span><span class="sxs-lookup"><span data-stu-id="81af9-122">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="81af9-123">A nova função de gerente pode ajudar a reduzir os custos de administração, pois você pode delegar responsabilidades limitadas para grupos de resposta específicos para qualquer usuário habilitado para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="81af9-123">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="81af9-124">Para acomodar a nova função gerente, o aplicativo de grupo de resposta do Lync Server 2013 introduz um **tipo de fluxo de trabalho** gerenciado ou não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="81af9-124">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="81af9-125">A tabela a seguir descreve os grupos de respostas Gerenciado ou Não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="81af9-125">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="81af9-126">Grupos de respostas Gerenciado ou Não gerenciado</span><span class="sxs-lookup"><span data-stu-id="81af9-126">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81af9-127">Tipo de grupo de respostas</span><span class="sxs-lookup"><span data-stu-id="81af9-127">Response group type</span></span></th>
<th><span data-ttu-id="81af9-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="81af9-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81af9-129">Não gerenciados</span><span class="sxs-lookup"><span data-stu-id="81af9-129">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="81af9-130">Os grupos de respostas não gerenciados não têm gerentes atribuídos.</span><span class="sxs-lookup"><span data-stu-id="81af9-130">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="81af9-131">Somente o administrador do grupo de resposta pode configurar esses grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="81af9-131">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="81af9-132">Vários grupos de respostas não gerenciados podem compartilhar uma fila ou grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="81af9-132">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="81af9-133">Ao migrar grupos de resposta de uma versão anterior para o Lync Server 2013, o tipo é definido como não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="81af9-133">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81af9-134">Gerenciados</span><span class="sxs-lookup"><span data-stu-id="81af9-134">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="81af9-135">Os administradores do grupo de resposta podem configurar qualquer aspecto de grupos de respostas gerenciados.</span><span class="sxs-lookup"><span data-stu-id="81af9-135">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="81af9-136">Os gerentes do grupo de resposta não podem exibir nem modificar grupos de respostas que não sejam explicitamente atribuídos a eles.</span><span class="sxs-lookup"><span data-stu-id="81af9-136">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="81af9-137">Os gerentes do grupo de resposta podem definir apenas algumas configurações dos grupos de resposta atribuídos explicitamente a eles.</span><span class="sxs-lookup"><span data-stu-id="81af9-137">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="81af9-138">Os grupos de respostas gerenciados não podem compartilhas filas nem grupos de agentes com outros grupos de respostas, sejam gerenciados ou não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="81af9-138">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="81af9-139">A tabela a seguir descreve as ações que os gerentes de grupo de resposta podem ou não executar para os grupos de resposta atribuídos a eles.</span><span class="sxs-lookup"><span data-stu-id="81af9-139">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="81af9-140">Recursos do gerente do grupo de respostas</span><span class="sxs-lookup"><span data-stu-id="81af9-140">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81af9-141">Pode configurar:</span><span class="sxs-lookup"><span data-stu-id="81af9-141">Can configure:</span></span></th>
<th><span data-ttu-id="81af9-142">Pode criar, excluir ou configurar:</span><span class="sxs-lookup"><span data-stu-id="81af9-142">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="81af9-143">Conseguir</span><span class="sxs-lookup"><span data-stu-id="81af9-143">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="81af9-144">SNMP</span><span class="sxs-lookup"><span data-stu-id="81af9-144">Agents</span></span></p></li>
<li><p><span data-ttu-id="81af9-145">Mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="81af9-145">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="81af9-146">Nome do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="81af9-146">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="81af9-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="81af9-147">Description</span></span></p></li>
<li><p><span data-ttu-id="81af9-148">Número de exibição</span><span class="sxs-lookup"><span data-stu-id="81af9-148">Display number</span></span></p></li>
<li><p><span data-ttu-id="81af9-149">Horário comercial</span><span class="sxs-lookup"><span data-stu-id="81af9-149">Business hours</span></span></p></li>
<li><p><span data-ttu-id="81af9-150">Música de espera</span><span class="sxs-lookup"><span data-stu-id="81af9-150">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="81af9-151">Status (ativo/inativo)</span><span class="sxs-lookup"><span data-stu-id="81af9-151">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="81af9-152">Fluxos de trabalho de grupo de busca ou fluxos de trabalho de IVR (reposta interativa de voz)</span><span class="sxs-lookup"><span data-stu-id="81af9-152">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="81af9-153">Grupos de agentes</span><span class="sxs-lookup"><span data-stu-id="81af9-153">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="81af9-154">Filas</span><span class="sxs-lookup"><span data-stu-id="81af9-154">Queues</span></span></p></li>
<li><p><span data-ttu-id="81af9-155">Conjuntos de feriados</span><span class="sxs-lookup"><span data-stu-id="81af9-155">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="81af9-156">Criar ou excluir qualquer tipo de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="81af9-156">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="81af9-157">Modificar configurações centrais do grupo de respostas, como: <strong>URI do SIP</strong>, <strong>Número de Telefone</strong> ou <strong>Tipo de Fluxo de Trabalho</strong>.</span><span class="sxs-lookup"><span data-stu-id="81af9-157">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="81af9-158">Os gerentes do grupo de resposta podem usar as ferramentas a seguir para gerenciar os grupos de resposta designados.</span><span class="sxs-lookup"><span data-stu-id="81af9-158">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="81af9-159">Painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="81af9-159">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="81af9-160">Os gerentes do grupo de resposta podem gerenciar apenas as configurações do grupo de resposta com essa ferramenta.</span><span class="sxs-lookup"><span data-stu-id="81af9-160">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="81af9-161">Outras configurações do Lync Server não estão disponíveis para gerentes.</span><span class="sxs-lookup"><span data-stu-id="81af9-161">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="81af9-162">Ferramenta de configuração do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="81af9-162">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="81af9-163">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="81af9-163">Lync Server Management Shell</span></span>

<span data-ttu-id="81af9-164">O grupo de resposta é dimensionado bem para ambientes de departamento ou de grupo de trabalho (para obter detalhes, consulte [planejamento de capacidade para grupo de resposta no Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) e pode ser implantado em instalações de telefonia totalmente novas.</span><span class="sxs-lookup"><span data-stu-id="81af9-164">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="81af9-165">Ele oferece suporte a chamadas de entrada da implantação do Enterprise Voice e da rede da operadora local.</span><span class="sxs-lookup"><span data-stu-id="81af9-165">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="81af9-166">Os agentes podem usar o Lync 2013, o Lync 2010, o Lync 2010 Attendant ou o Lync Phone Edition para fazer as chamadas roteadas para eles.</span><span class="sxs-lookup"><span data-stu-id="81af9-166">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="81af9-167">O aplicativo grupo de resposta é um componente do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="81af9-167">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="81af9-168">Quando você implanta o Enterprise Voice, o aplicativo grupo de resposta é instalado e ativado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="81af9-168">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

