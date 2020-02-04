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
ms.openlocfilehash: 2b01181296a42f786a4739b5ec59d775212baaf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="6dd29-102">Visão geral do aplicativo grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dd29-102">Overview of the Response Group application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dd29-103">_**Tópico da última modificação:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="6dd29-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="6dd29-104">Quando um chamador chama um grupo de resposta, a chamada é roteada para um agente com base em um grupo de busca ou nas respostas do chamador às perguntas de IVR (resposta de voz interativa).</span><span class="sxs-lookup"><span data-stu-id="6dd29-104">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="6dd29-105">O aplicativo grupo de resposta usa métodos de roteamento de grupo de resposta padrão para direcionar a chamada para o próximo agente disponível.</span><span class="sxs-lookup"><span data-stu-id="6dd29-105">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="6dd29-106">Os métodos de roteamento de chamadas incluem serial, Idle mais longo, paralelo, rodízio e roteamento de atendedor (ou seja, todos os agentes são chamados ao mesmo tempo para cada chamada de entrada, independentemente da presença atual).</span><span class="sxs-lookup"><span data-stu-id="6dd29-106">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="6dd29-107">Se nenhum agente estiver disponível, a chamada será mantida em uma fila até que um agente esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="6dd29-107">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="6dd29-108">Enquanto estiver na fila, o chamador ouvirá música até que um agente disponível aceite a chamada.</span><span class="sxs-lookup"><span data-stu-id="6dd29-108">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="6dd29-109">Se a fila estiver cheia ou se a chamada expirar durante a fila, o chamador pode ouvir uma mensagem e, em seguida, desconectado ou transferido para um destino diferente.</span><span class="sxs-lookup"><span data-stu-id="6dd29-109">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="6dd29-110">Quando um agente aceita a chamada, o chamador pode ou não ver a identidade do agente, dependendo de como o administrador configura o grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="6dd29-110">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="6dd29-111">Os agentes podem ser formais, o que significa que devem entrar no grupo antes de aceitarem chamadas encaminhadas para o grupo, ou informal, o que significa que eles não entram e saem do grupo para aceitar chamadas.</span><span class="sxs-lookup"><span data-stu-id="6dd29-111">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6dd29-112">Somente os usuários no local podem ser agentes.</span><span class="sxs-lookup"><span data-stu-id="6dd29-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="6dd29-113">Se um agente for movido do local para o online, as chamadas em grupo de resposta não serão roteadas para esse agente.</span><span class="sxs-lookup"><span data-stu-id="6dd29-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="6dd29-114">O aplicativo grupo de resposta usa um serviço interno, chamado fazer correspondência, para enfileirar chamadas e localizar agentes disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6dd29-114">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="6dd29-115">Cada computador que executa o aplicativo do grupo de resposta executa o serviço fazer correspondência, mas apenas um serviço de correspondência por pool do Lync Server fica ativo por vez--os outros são passivos.</span><span class="sxs-lookup"><span data-stu-id="6dd29-115">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="6dd29-116">Se a correspondência ativa que faz o serviço ficar indisponível durante uma interrupção não planejada, um dos serviços de correspondência passiva será ativado.</span><span class="sxs-lookup"><span data-stu-id="6dd29-116">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="6dd29-117">O aplicativo grupo de resposta faz o melhor possível para garantir que o encaminhamento de chamadas e o enfileiramento continuem ininterruptos.</span><span class="sxs-lookup"><span data-stu-id="6dd29-117">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="6dd29-118">No entanto, quando ocorre uma correspondência fazendo a transição do serviço, todas as chamadas que estão sendo transferidas no momento são perdidas.</span><span class="sxs-lookup"><span data-stu-id="6dd29-118">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="6dd29-119">Por exemplo, se a transição for devida ao servidor de front-end, todas as chamadas atualmente manipuladas pela correspondência ativa que está fazendo o serviço nesse servidor front-end também serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="6dd29-119">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="6dd29-120">No Lync Server 2013, duas funções de gerenciamento estão disponíveis para o gerenciamento de grupos de resposta: gerente de grupo de resposta e administrador de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="6dd29-120">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="6dd29-121">Os administradores de grupo de resposta podem gerenciar qualquer aspecto de qualquer grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="6dd29-121">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="6dd29-122">Os gerentes de grupo de resposta podem gerenciar apenas determinados aspectos e somente para os grupos de resposta que eles possuem.</span><span class="sxs-lookup"><span data-stu-id="6dd29-122">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="6dd29-123">A nova função gerente pode ajudar a reduzir os custos de administração, pois você pode delegar responsabilidades limitadas para grupos de resposta específicos para qualquer usuário habilitado para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6dd29-123">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="6dd29-124">Para acomodar a nova função gerente, o aplicativo do grupo de resposta do Lync Server 2013 introduz um **tipo de fluxo de trabalho** gerenciado ou não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="6dd29-124">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="6dd29-125">A tabela a seguir descreve os grupos de resposta gerenciados e não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="6dd29-125">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="6dd29-126">Grupos de resposta gerenciados e não gerenciados</span><span class="sxs-lookup"><span data-stu-id="6dd29-126">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dd29-127">Tipo de grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="6dd29-127">Response group type</span></span></th>
<th><span data-ttu-id="6dd29-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="6dd29-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6dd29-129">Não gerenciado</span><span class="sxs-lookup"><span data-stu-id="6dd29-129">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6dd29-130">Os grupos de resposta não gerenciados não têm gerentes atribuídos.</span><span class="sxs-lookup"><span data-stu-id="6dd29-130">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="6dd29-131">Somente o administrador do grupo de resposta pode configurar esses grupos de resposta.</span><span class="sxs-lookup"><span data-stu-id="6dd29-131">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="6dd29-132">Vários grupos de resposta não gerenciados podem compartilhar uma fila ou um grupo de agente.</span><span class="sxs-lookup"><span data-stu-id="6dd29-132">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="6dd29-133">Quando você migra grupos de resposta de uma versão anterior para o Lync Server 2013, o tipo é definido como não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="6dd29-133">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6dd29-134">Gerenciado</span><span class="sxs-lookup"><span data-stu-id="6dd29-134">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6dd29-135">Os administradores de grupo de resposta podem configurar qualquer aspecto de grupos de resposta gerenciado.</span><span class="sxs-lookup"><span data-stu-id="6dd29-135">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="6dd29-136">Os gerentes de grupo de resposta não podem exibir ou modificar os grupos de resposta que não foram atribuídos explicitamente a eles.</span><span class="sxs-lookup"><span data-stu-id="6dd29-136">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="6dd29-137">Os gerentes de grupo de resposta podem configurar apenas algumas configurações para os grupos de resposta atribuídos explicitamente a eles.</span><span class="sxs-lookup"><span data-stu-id="6dd29-137">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="6dd29-138">Grupos de resposta gerenciada não podem compartilhar filas ou grupos de agente com qualquer outro grupo de resposta, gerenciado ou não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="6dd29-138">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6dd29-139">A tabela a seguir descreve as ações que os gerentes de grupo de resposta podem e não podem realizar para os grupos de resposta atribuídos a eles.</span><span class="sxs-lookup"><span data-stu-id="6dd29-139">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="6dd29-140">Funcionalidades do Gerenciador de grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="6dd29-140">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6dd29-141">Pode configurar:</span><span class="sxs-lookup"><span data-stu-id="6dd29-141">Can configure:</span></span></th>
<th><span data-ttu-id="6dd29-142">Pode criar, excluir ou configurar:</span><span class="sxs-lookup"><span data-stu-id="6dd29-142">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="6dd29-143">Consegue</span><span class="sxs-lookup"><span data-stu-id="6dd29-143">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="6dd29-144">Agentes</span><span class="sxs-lookup"><span data-stu-id="6dd29-144">Agents</span></span></p></li>
<li><p><span data-ttu-id="6dd29-145">Mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="6dd29-145">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="6dd29-146">Nome do grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="6dd29-146">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="6dd29-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="6dd29-147">Description</span></span></p></li>
<li><p><span data-ttu-id="6dd29-148">Número para exibição</span><span class="sxs-lookup"><span data-stu-id="6dd29-148">Display number</span></span></p></li>
<li><p><span data-ttu-id="6dd29-149">Horário comercial</span><span class="sxs-lookup"><span data-stu-id="6dd29-149">Business hours</span></span></p></li>
<li><p><span data-ttu-id="6dd29-150">Música de espera</span><span class="sxs-lookup"><span data-stu-id="6dd29-150">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="6dd29-151">Status (ativo/inativo)</span><span class="sxs-lookup"><span data-stu-id="6dd29-151">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="6dd29-152">Fluxos de trabalho de grupo de busca ou de reação de voz interativa (IVR)</span><span class="sxs-lookup"><span data-stu-id="6dd29-152">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="6dd29-153">Grupos de agente</span><span class="sxs-lookup"><span data-stu-id="6dd29-153">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="6dd29-154">Filas</span><span class="sxs-lookup"><span data-stu-id="6dd29-154">Queues</span></span></p></li>
<li><p><span data-ttu-id="6dd29-155">Conjuntos de feriados</span><span class="sxs-lookup"><span data-stu-id="6dd29-155">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="6dd29-156">Criar ou excluir qualquer tipo de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="6dd29-156">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="6dd29-157">Modifique as configurações do grupo de respostas principais, como: <strong>URI SIP</strong>, <strong>número de telefone</strong>ou <strong>tipo de fluxo de trabalho</strong>.</span><span class="sxs-lookup"><span data-stu-id="6dd29-157">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6dd29-158">Os gerentes de grupo de resposta podem usar as seguintes ferramentas para gerenciar os grupos de resposta designados.</span><span class="sxs-lookup"><span data-stu-id="6dd29-158">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="6dd29-159">Painel de Controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="6dd29-159">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6dd29-160">Os gerentes de grupo de resposta só podem gerenciar as configurações de grupo de resposta com essa ferramenta.</span><span class="sxs-lookup"><span data-stu-id="6dd29-160">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="6dd29-161">Outras configurações do Lync Server não estão disponíveis para gerentes.</span><span class="sxs-lookup"><span data-stu-id="6dd29-161">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="6dd29-162">Ferramenta de Configuração de Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="6dd29-162">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="6dd29-163">Shell de Gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="6dd29-163">Lync Server Management Shell</span></span>

<span data-ttu-id="6dd29-164">Grupo de resposta dimensionável bem para ambientes de departamento ou de grupo de trabalho (para obter detalhes, consulte [planejamento de capacidade para o grupo de resposta no Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) e pode ser implantado em instalações de telefonia totalmente novas.</span><span class="sxs-lookup"><span data-stu-id="6dd29-164">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="6dd29-165">Ele é compatível com chamadas de implantação do Enterprise Voice e da rede da operadora local.</span><span class="sxs-lookup"><span data-stu-id="6dd29-165">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="6dd29-166">Os agentes podem usar o Lync 2013, o Lync 2010, o Lync 2010 Attendant ou o Lync Phone Edition para fazer as chamadas serem roteadas para eles.</span><span class="sxs-lookup"><span data-stu-id="6dd29-166">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="6dd29-167">O aplicativo grupo de resposta é um componente do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6dd29-167">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="6dd29-168">Ao implantar o Enterprise Voice, o aplicativo grupo de resposta é instalado e ativado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6dd29-168">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

