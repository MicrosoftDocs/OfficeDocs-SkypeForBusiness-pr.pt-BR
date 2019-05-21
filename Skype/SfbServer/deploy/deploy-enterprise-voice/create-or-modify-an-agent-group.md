---
title: Criar ou modificar um grupo de agente no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Crie ou modifique um grupo de agente no grupo resposta no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 0481e8048245908c757cf0dd1ecaed5d69291cb3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286201"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a><span data-ttu-id="9843a-103">Criar ou modificar um grupo de agente no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9843a-103">Create or modify an agent group in Skype for Business</span></span>
 
<span data-ttu-id="9843a-104">Crie ou modifique um grupo de agente no grupo resposta no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9843a-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="9843a-105">Ao criar um grupo de operadores, você seleciona os operadores atribuídos ao grupo e especifica configurações de grupo adicionais, como o método de roteamento e se um operador pode entrar e sair do grupo.</span><span class="sxs-lookup"><span data-stu-id="9843a-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="9843a-106">Um agente que deve entrar e sair do grupo, que é diferente de entrar ou sair do Skype for Business, é chamado de agente formal.</span><span class="sxs-lookup"><span data-stu-id="9843a-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="9843a-107">Os operadores formais precisam entrar no grupo para que possam receber as chamadas roteadas para o grupo.</span><span class="sxs-lookup"><span data-stu-id="9843a-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="9843a-108">Isso pode ser útil para os operadores que respondem às chamadas do grupo em tempo parcial.</span><span class="sxs-lookup"><span data-stu-id="9843a-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="9843a-109">Os agentes formais entram e saem de seus grupos clicando em um item de menu no Skype for Business para abrir o navegador da Internet do Windows Internet Explorer e exibir um console de página da Web.</span><span class="sxs-lookup"><span data-stu-id="9843a-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="9843a-110">Um operador que não precisa entrar ou sair do grupo é denominado operador informal.</span><span class="sxs-lookup"><span data-stu-id="9843a-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="9843a-111">Agentes informais são automaticamente conectados ao grupo quando eles se conectam ao Skype for Business, e não podem sair do grupo.</span><span class="sxs-lookup"><span data-stu-id="9843a-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="9843a-112">Somente os usuários no local podem ser agentes.</span><span class="sxs-lookup"><span data-stu-id="9843a-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="9843a-113">Se um agente for movido do local para o online, as chamadas em grupo de resposta não serão roteadas para esse agente.</span><span class="sxs-lookup"><span data-stu-id="9843a-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="9843a-114">Use um dos procedimentos a seguir para criar ou modificar um grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="9843a-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9843a-p104">Quando você atribui usuários como agentes de grupo de resposta, informe-os de que, se eles tiverem o modo Privacidade habilitado, precisarão pesquisar por contatos "RGS Presence Watcher" e adicioná-los à sua lista Contatos. Agentes que tem o modo Privacidade habilitado, mas não tem "RGS Presence Watcher" em sua lista de Contatos, não podem receber chamadas no grupo de resposta. Agentes que não têm o modo Privacidade habilitado não são afetados.</span><span class="sxs-lookup"><span data-stu-id="9843a-p104">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="9843a-118">Para usar o painel de controle do Skype for Business Server para criar ou modificar um grupo de agente</span><span class="sxs-lookup"><span data-stu-id="9843a-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="9843a-119">Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="9843a-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9843a-120">Se você é um dos Gerentes de Grupo de Resposta delegados para um fluxo de trabalho gerenciado, você pode criar grupos e os usar nos fluxos de trabalho que você gerencia.</span><span class="sxs-lookup"><span data-stu-id="9843a-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="9843a-121">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9843a-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9843a-122">Na barra de navegação à esquerda, clique em **Grupos de resposta**e depois em **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="9843a-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="9843a-123">Na página **Grupo**, execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="9843a-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="9843a-p105">Para criar um novo grupo de agentes, clique em **Novo**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço **ApplicationServer** para o qual você deseja adicionar o grupo. Na lista resultante de serviços, clique no serviço desejado e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9843a-p105">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="9843a-p106">Para modificar um grupo de agentes existente, digite todo ou parte do nome do grupo de agentes no campo de pesquisa. Na lista de resultados, clique no grupo desejado, clique em **Editar**e depois, clique em **Exibir Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="9843a-p106">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="9843a-129">Em **Nome**, digite o nome que identifica o grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="9843a-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="9843a-130">Em **Descrição**, digite uma descrição para o grupo.</span><span class="sxs-lookup"><span data-stu-id="9843a-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="9843a-131">Na **Política de participação**, selecione uma das seguintes opções para configurar o comportamento de logon para o grupo:</span><span class="sxs-lookup"><span data-stu-id="9843a-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="9843a-132">Selecione **Informal** para especificar que os agentes no grupo não precisam entrar e sair do grupo.</span><span class="sxs-lookup"><span data-stu-id="9843a-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="9843a-133">Os agentes são conectados automaticamente ao grupo quando entram no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9843a-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="9843a-134">Selecione  **Formal** para especificar que os agentes no grupo precisam entrar e sair do grupo.</span><span class="sxs-lookup"><span data-stu-id="9843a-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="9843a-135">Quando você seleciona essa opção, os agentes clicam em um item de menu no Skype for Business para abrir o Internet Explorer e exibir um console de página da Web para entrar e sair do grupo.</span><span class="sxs-lookup"><span data-stu-id="9843a-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="9843a-136">Em **Tempo de alerta (segundos)**, especifique a duração em segundos do toque para um agente antes de oferecer a chamada para o próximo agente disponível (o padrão é de 20 segundos).</span><span class="sxs-lookup"><span data-stu-id="9843a-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9843a-p109">A configuração Tempo de alerta do agente não pode ultrapassar 180 segundos. Caso contrário, o aplicativo do cliente rejeitará a chamada devido ao fato de o timer de transação SIP atingir seu tempo máximo de espera.</span><span class="sxs-lookup"><span data-stu-id="9843a-p109">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="9843a-139">No **Método de roteamento**, selecione o método para roteamento de chamadas a agentes no grupo da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9843a-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="9843a-140">Para oferecer uma nova chamada primeiro ao agente que esteve ociosa o mais longo (teve uma presença de **disponível** ou inativo no \*\*\*\* Skype for Business por mais tempo), clique em ociosa mais **longa**.</span><span class="sxs-lookup"><span data-stu-id="9843a-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="9843a-p110">Para oferecer uma nova chamada para todos os agentes disponíveis ao mesmo tempo, clique em **Em paralelo**. A chamada é enviada ao primeiro agente que a aceitar.</span><span class="sxs-lookup"><span data-stu-id="9843a-p110">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="9843a-143">Para oferecer uma nova chamada a cada operador um após o outro, clique em  **Round robin**.</span><span class="sxs-lookup"><span data-stu-id="9843a-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="9843a-144">Para sempre oferecer uma nova chamada aos agentes na ordem em que estão na lista **Agentes**, clique em **Em série**.</span><span class="sxs-lookup"><span data-stu-id="9843a-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="9843a-145">Para oferecer uma nova chamada para todos os agentes conectados ao Skype for Business e ao aplicativo de grupo de resposta ao mesmo tempo, independentemente da presença atual, clique em **atendente**.</span><span class="sxs-lookup"><span data-stu-id="9843a-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="9843a-146">Os usuários configurados como agentes podem ver todas as chamadas que estão aguardando e responder às chamadas em espera em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="9843a-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="9843a-147">A chamada é enviada ao primeiro agente que a aceita, e os outros usuários não veem mais a chamada.</span><span class="sxs-lookup"><span data-stu-id="9843a-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="9843a-148">Em  **Agentes**, especifique como você deseja criar sua lista de agentes:</span><span class="sxs-lookup"><span data-stu-id="9843a-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
    - <span data-ttu-id="9843a-149">Para usar uma lista de agentes personalizada, clique em **Definir um grupo personalizado de agentes**e execute um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="9843a-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
    - <span data-ttu-id="9843a-p112">Para adicionar um usuário ao grupo de agentes, clique em  **Selecionar**, depois no campo de pesquisa  **Selecionar Agentes**, digite todo ou parte do nome do usuário que você quer adicionar ao grupo e clique em  **Localizar**. Na lista de agentes resultante, clique no usuário que você quer adicionar e clique em  **OK**.</span><span class="sxs-lookup"><span data-stu-id="9843a-p112">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
    - <span data-ttu-id="9843a-152">Para remover um usuário do grupo de agentes, na lista de agentes, clique no usuário que deseja remover e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="9843a-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
    - <span data-ttu-id="9843a-153">Para alterar a ordem em que os agentes são oferecidos às chamadas nos grupos usando rodízio ou encaminhamento em série, na lista de agentes, clique em um usuário e depois clique em seta para cima ou na seta para baixo.</span><span class="sxs-lookup"><span data-stu-id="9843a-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
    - <span data-ttu-id="9843a-154">Para usar uma lista de distribuição do Microsoft Exchange Server como grupo de agentes, clique em **Usar uma lista de distribuição de email existente**e em **Endereço da lista de distribuição**, digite o endereço de email da lista de distribuição (por exemplo, NetworkSupport@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9843a-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
      <span data-ttu-id="9843a-155">Se você usar uma lista de distribuição por email, estará sujeito às seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="9843a-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
      - <span data-ttu-id="9843a-p113">Você não pode selecionar várias listas de distribuição para o grupo de operadores. Cada grupo oferece suporte a apenas uma lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="9843a-p113">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
    
      - <span data-ttu-id="9843a-158">Se a lista de distribuição contiver uma ou mais listas de distribuição, os membros das listas aninhadas não serão adicionados à lista de operadores.</span><span class="sxs-lookup"><span data-stu-id="9843a-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
      - <span data-ttu-id="9843a-159">Se os roteamentos em série e round robin forem selecionados, o servidor oferecerá uma chamada de entrada ao agente apropriado de acordo com o método de roteamento e com a ordem na qual os agentes estão listados na lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="9843a-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
      - <span data-ttu-id="9843a-p114">Se a lista de distribuição contiver usuários, para os quais o Lync Server 2010 estiver habilitado, porém o Enterprise Voice não estiver habilitado, eles serão adicionados ao grupo de agentes como agentes não funcionais. Garanta que todos os membros da lista de distribuição tenham o Enterprise Voice habilitado em suas contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="9843a-p114">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents. Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9843a-162">Se você usar uma lista de distribuição de email, associações ocultas ou listas ocultas podem ficar visíveis para os usuários ou administradores do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="9843a-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="9843a-163">Associações ou listas ocultas podem se tornar visíveis da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9843a-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="9843a-164">Se uma lista de distribuição foi configurada para que a associação fique oculta e o administrador do grupo de resposta atribua a lista de distribuição à lista de agentes, os usuários podem chamar o grupo para descobrir quem são os membros.</span><span class="sxs-lookup"><span data-stu-id="9843a-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="9843a-165">Se uma lista de distribuição foi configurada para que ela fique oculta na lista de endereços global do Exchange, o administrador do grupo de resposta poderá ver a lista de distribuição e atribuí-la à lista de agentes se o processo do grupo de resposta tiver os direitos de usuário adequados e permissões, mesmo se o administrador não tiver as permissões e direitos de usuário adequados.</span><span class="sxs-lookup"><span data-stu-id="9843a-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="9843a-166">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9843a-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="9843a-167">Para usar o Shell de gerenciamento do Skype for Business Server para criar ou modificar um grupo de agente</span><span class="sxs-lookup"><span data-stu-id="9843a-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="9843a-168">Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="9843a-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="9843a-169">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="9843a-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="9843a-170">Use  **New-CsRgsAgentGroup** para criar um novo grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="9843a-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="9843a-171">Use  **Set-CsRgsAgentGroup** para modificar um grupo de agentes existente.</span><span class="sxs-lookup"><span data-stu-id="9843a-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="9843a-172">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="9843a-172">At the command line, run:</span></span>
    
   ```
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="9843a-173">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9843a-173">For example:</span></span>
    
   ```
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="9843a-p116">A configuração Tempo de alerta do agente não pode ultrapassar 180 segundos. Caso contrário, o aplicativo do cliente rejeitará a chamada devido ao fato de o timer de transação SIP atingir seu tempo máximo de espera.</span><span class="sxs-lookup"><span data-stu-id="9843a-p116">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="9843a-p117">Confirme a criação do novo grupo. Execute:</span><span class="sxs-lookup"><span data-stu-id="9843a-p117">Confirm that the agent group is created. Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="9843a-178">Confira também</span><span class="sxs-lookup"><span data-stu-id="9843a-178">See also</span></span>

[<span data-ttu-id="9843a-179">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="9843a-179">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="9843a-180">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="9843a-180">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="9843a-181">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="9843a-181">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="9843a-182">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="9843a-182">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
