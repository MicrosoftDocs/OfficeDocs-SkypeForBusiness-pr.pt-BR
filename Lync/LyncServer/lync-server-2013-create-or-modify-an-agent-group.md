---
title: 'Lync Server 2013: criar ou modificar um grupo de agentes'
description: 'Lync Server 2013: criar ou modificar um grupo de agentes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a8d3f33df64ba1eacd4fa65a0706d030dc9b5f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574457"
---
# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="4721b-103">Criar ou modificar um grupo de agentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4721b-103">Create or modify an agent group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4721b-104">_**Última modificação do tópico:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="4721b-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="4721b-105">Use um dos procedimentos a seguir para criar ou modificar um grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="4721b-105">Use one of the following procedures to create or modify an agent group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4721b-106">Um administrador — por exemplo, CsVoiceAdministrator — deve habilitar usuários para o Enterprise Voice e o Lync Server antes que os usuários possam ser atribuídos a grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="4721b-106">An Administrator—for example, CsVoiceAdministrator—must enable users for Enterprise Voice and Lync Server before the users can be assigned to agent groups.</span></span> <span data-ttu-id="4721b-107">Se você é um dos Gerentes de Grupo de Resposta designados para um fluxo de trabalho gerenciado, você pode criar grupos de agentes e os usar nos fluxos de trabalho que você gerencia.</span><span class="sxs-lookup"><span data-stu-id="4721b-107">If you are one of the delegated Response Group Managers for a managed workflow, you can create agent groups and use the agent groups in the workflows that you manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4721b-p102">Quando você atribuir os usuários como operadores do grupo de resposta, informe-os de que, se tiverem o modo de privacidade habilitado, precisarão pesquisar os contatos do "RGS Presence Watcher" e adicioná-los à sua lista de contatos. Os operadores com o modo de privacidade habilitado, mas que não têm o "RGS Presence Watcher" na lista de contatos, não podem receber chamadas para o grupo de resposta. Os operadores que não têm o modo de privacidade habilitado não são afetados.</span><span class="sxs-lookup"><span data-stu-id="4721b-p102">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="4721b-111">Para usar o painel de controle do Lync Server para criar ou modificar um grupo de agentes</span><span class="sxs-lookup"><span data-stu-id="4721b-111">To use Lync Server Control Panel to create or modify an agent group</span></span>

1.  <span data-ttu-id="4721b-112">Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="4721b-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4721b-113">Se você é um dos Gerentes de Grupo de Resposta delegados para um fluxo de trabalho gerenciado, você pode criar grupos e os usar nos fluxos de trabalho que você gerencia.</span><span class="sxs-lookup"><span data-stu-id="4721b-113">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="4721b-114">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4721b-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4721b-115">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4721b-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4721b-116">Na barra de navegação à esquerda, clique em **Grupos de resposta** e depois em **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="4721b-116">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="4721b-117">Na página **Grupo**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="4721b-117">On the **Group** page, do one of the following:</span></span>
    
      - <span data-ttu-id="4721b-p104">Para criar um novo grupo de agentes, clique em **Novo**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço **ApplicationServer** para o qual você deseja adicionar o grupo. Na lista resultante de serviços, clique no serviço desejado e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4721b-p104">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="4721b-p105">Para modificar um grupo de agentes existente, digite todo ou parte do nome do grupo de agentes no campo de pesquisa. Na lista de resultados, clique no grupo desejado, clique em **Editar** e depois, clique em **Exibir Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="4721b-p105">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4721b-123">Em **Nome**, digite o nome que identifica o grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="4721b-123">In **Name**, type an identifying name for the agent group.</span></span>

6.  <span data-ttu-id="4721b-124">Em **Descrição**, digite uma descrição para o grupo.</span><span class="sxs-lookup"><span data-stu-id="4721b-124">In **Description**, type a description for the group.</span></span>

7.  <span data-ttu-id="4721b-125">Na **Política de participação**, selecione uma das seguintes opções para configurar o comportamento de logon para o grupo:</span><span class="sxs-lookup"><span data-stu-id="4721b-125">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
      - <span data-ttu-id="4721b-126">Selecione **Informal** para especificar que os agentes no grupo não precisam entrar e sair do grupo.</span><span class="sxs-lookup"><span data-stu-id="4721b-126">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="4721b-127">Os agentes são automaticamente conectados ao grupo quando entram no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4721b-127">Agents are automatically signed in to the group when they sign in to Lync Server 2013.</span></span>
    
      - <span data-ttu-id="4721b-128">Selecione **Formal** para especificar que os agentes no grupo precisam entrar e sair do grupo.</span><span class="sxs-lookup"><span data-stu-id="4721b-128">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="4721b-129">Quando você seleciona essa opção, os agentes clicam em um item de menu no Lync para abrir o Internet Explorer e exibir um console de página da Web para entrar e sair do grupo.</span><span class="sxs-lookup"><span data-stu-id="4721b-129">When you select this option, agents click a menu item in Lync to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

8.  <span data-ttu-id="4721b-130">Em **Tempo de alerta (segundos)**, especifique a duração em segundos do toque para um agente antes de oferecer a chamada para o próximo agente disponível (o padrão é de 20 segundos).</span><span class="sxs-lookup"><span data-stu-id="4721b-130">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4721b-p108">A configuração Tempo de alerta do agente não pode ultrapassar 180 segundos. Caso contrário, o aplicativo do cliente rejeitará a chamada devido ao fato de o timer de transação SIP atingir seu tempo máximo de espera.</span><span class="sxs-lookup"><span data-stu-id="4721b-p108">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

9.  <span data-ttu-id="4721b-133">No **Método de roteamento**, selecione o método para roteamento de chamadas a agentes no grupo da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4721b-133">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
      - <span data-ttu-id="4721b-134">Para oferecer uma nova chamada primeiro para o agente que esteve ocioso o mais longo (teve uma presença de **disponível** ou **inativo** no Lync Server o mais longo), clique em **ocioso mais longo**.</span><span class="sxs-lookup"><span data-stu-id="4721b-134">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Lync Server the longest), click **Longest idle**.</span></span>
    
      - <span data-ttu-id="4721b-p109">Para oferecer uma nova chamada para todos os operadores disponíveis ao mesmo tempo, clique em **Em paralelo**. A chamada é enviada ao primeiro operador que a aceitar.</span><span class="sxs-lookup"><span data-stu-id="4721b-p109">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
      - <span data-ttu-id="4721b-137">Para oferecer uma nova chamada a cada operador um após o outro, clique em **Round robin**.</span><span class="sxs-lookup"><span data-stu-id="4721b-137">To offer a new call to each agent in turn, click **Round robin**.</span></span>
    
      - <span data-ttu-id="4721b-138">Para sempre oferecer uma nova chamada aos operadores na ordem em que estão na lista **Operadores**, clique em **Em série**.</span><span class="sxs-lookup"><span data-stu-id="4721b-138">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span>
    
      - <span data-ttu-id="4721b-139">Para oferecer uma nova chamada a todos os agentes que estão conectados ao Lync Server 2013 e ao aplicativo de grupo de resposta ao mesmo tempo, independentemente de sua presença atual, clique em **atendedor**.</span><span class="sxs-lookup"><span data-stu-id="4721b-139">To offer a new call to all agents who are signed into Lync Server 2013 and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="4721b-140">Os usuários do atendedor do Lync 2010 que estão configurados como agentes podem ver todas as chamadas que estão aguardando e respondendo a chamadas em espera em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="4721b-140">Lync 2010 Attendant users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="4721b-141">A chamada é enviada ao primeiro agente que a aceita, após o qual os outros usuários do Lync 2010 Attendant não mais veem a chamada.</span><span class="sxs-lookup"><span data-stu-id="4721b-141">The call is sent to the first agent who accepts it, after which the other Lync 2010 Attendant users no longer see the call.</span></span>

10. <span data-ttu-id="4721b-142">Em **Agentes**, especifique como você deseja criar sua lista de agentes:</span><span class="sxs-lookup"><span data-stu-id="4721b-142">In **Agents**, specify how you want to create your agents list:</span></span>
    
      - <span data-ttu-id="4721b-143">Para usar uma lista de agentes personalizada, clique em **Definir um grupo personalizado de agentes** e execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="4721b-143">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
        
          - <span data-ttu-id="4721b-p111">Para adicionar um usuário ao grupo de agentes, clique em **Selecionar**, depois no campo de pesquisa **Selecionar Agentes**, digite todo ou parte do nome do usuário que você quer adicionar ao grupo e clique em **Localizar**. Na lista de agentes resultante, clique no usuário que você quer adicionar e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4721b-p111">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
        
          - <span data-ttu-id="4721b-146">Para remover um usuário do grupo de agentes, na lista de agentes, clique no usuário que deseja remover e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="4721b-146">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
        
          - <span data-ttu-id="4721b-147">Para alterar a ordem em que os agentes são oferecidos às chamadas nos grupos usando rodízio ou encaminhamento em série, na lista de agentes, clique em um usuário e depois clique em seta para cima ou na seta para baixo.</span><span class="sxs-lookup"><span data-stu-id="4721b-147">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span>
    
      - <span data-ttu-id="4721b-148">Para usar uma lista de distribuição do Microsoft Exchange Server como grupo de agentes, clique em **Usar uma lista de distribuição de email existente** e em **Endereço da lista de distribuição**, digite o endereço de email da lista de distribuição (por exemplo, NetworkSupport@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4721b-148">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
        
        <span data-ttu-id="4721b-149">Se você usar uma lista de distribuição por email, estará sujeito às seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="4721b-149">If you use an email distribution list, you are subject to the following constraints:</span></span>
        
          - <span data-ttu-id="4721b-p112">Você não pode selecionar várias listas de distribuição para o grupo de operadores. Cada grupo oferece suporte a apenas uma lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="4721b-p112">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
        
          - <span data-ttu-id="4721b-152">Se a lista de distribuição contiver uma ou mais listas de distribuição, os membros das listas aninhadas não serão adicionados à lista de operadores.</span><span class="sxs-lookup"><span data-stu-id="4721b-152">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
        
          - <span data-ttu-id="4721b-153">Se os roteamentos em série e round robin forem selecionados, o servidor oferecerá uma chamada de entrada ao agente apropriado de acordo com o método de roteamento e com a ordem na qual os agentes estão listados na lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="4721b-153">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
        
          - <span data-ttu-id="4721b-154">Se a lista de distribuição contiver usuários para os quais o Lync Server 2010 está habilitado, mas o Enterprise Voice não está habilitado, ele será adicionado ao grupo de agentes como agentes do Dysfunctional.</span><span class="sxs-lookup"><span data-stu-id="4721b-154">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="4721b-155">Certifique-se de que todos os membros da lista de distribuição tenham o Enterprise Voice habilitado para suas contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="4721b-155">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="4721b-156">Se você usar uma lista de distribuição de email, associações ocultas ou listas ocultas podem se tornar visíveis para o administrador ou os usuários do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="4721b-156">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span>

        
        </div>
        
        <span data-ttu-id="4721b-157">Associações ou listas ocultas podem se tornar visíveis da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="4721b-157">Hidden memberships or hidden lists can become visible as follows:</span></span>
        
          - <span data-ttu-id="4721b-158">Se uma lista de distribuição tiver sido configurada para que a associação fique oculta e o administrador do grupo de resposta atribuir a lista de distribuição à lista de agentes, os usuários poderão chamar o grupo para descobrir quem são os membros.</span><span class="sxs-lookup"><span data-stu-id="4721b-158">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span>
        
          - <span data-ttu-id="4721b-159">Se uma lista de distribuição tiver sido configurada para que fique oculta na lista de endereços global do Exchange, o administrador do grupo de resposta poderá ver a lista de distribuição e atribuí-la à lista de agentes se o processo do grupo de resposta tiver os direitos e permissões do usuário apropriados, mesmo que o administrador não tenha os direitos e permissões do usuário apropriados.</span><span class="sxs-lookup"><span data-stu-id="4721b-159">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>

11. <span data-ttu-id="4721b-160">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4721b-160">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="4721b-161">Para usar o Windows PowerShell para criar ou modificar um grupo de agentes</span><span class="sxs-lookup"><span data-stu-id="4721b-161">To use Windows PowerShell to create or modify an agent group</span></span>

1.  <span data-ttu-id="4721b-162">Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="4721b-162">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="4721b-163">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4721b-163">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4721b-164">Use **New-CsRgsAgentGroup** para criar um novo grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="4721b-164">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="4721b-165">Use  **Set-CsRgsAgentGroup** para modificar um grupo de agentes existente.</span><span class="sxs-lookup"><span data-stu-id="4721b-165">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="4721b-166">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="4721b-166">At the command line, run:</span></span>
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    <span data-ttu-id="4721b-167">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4721b-167">For example:</span></span>
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4721b-p115">A configuração Tempo de alerta do agente não pode ultrapassar 180 segundos. Caso contrário, o aplicativo do cliente rejeitará a chamada devido ao fato de o timer de transação SIP atingir seu tempo máximo de espera.</span><span class="sxs-lookup"><span data-stu-id="4721b-p115">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

4.  <span data-ttu-id="4721b-p116">Confirme a criação do novo grupo. Execute:</span><span class="sxs-lookup"><span data-stu-id="4721b-p116">Confirm that the agent group is created. Run:</span></span>
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4721b-172">Confira também</span><span class="sxs-lookup"><span data-stu-id="4721b-172">See Also</span></span>


[<span data-ttu-id="4721b-173">Excluir um grupo de agentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4721b-173">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)  


[<span data-ttu-id="4721b-174">Gerenciar grupos de agente de grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4721b-174">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)  
[<span data-ttu-id="4721b-175">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="4721b-175">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="4721b-176">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="4721b-176">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[<span data-ttu-id="4721b-177">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="4721b-177">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[<span data-ttu-id="4721b-178">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="4721b-178">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

