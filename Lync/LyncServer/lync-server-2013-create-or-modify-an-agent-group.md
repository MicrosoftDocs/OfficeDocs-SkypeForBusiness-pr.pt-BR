---
title: 'Lync Server 2013: criar ou modificar um grupo de agente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0a2765e9ba72501b148e61d0d38789a46b2c3bc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a>Criar ou modificar um grupo de agente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-07_

Use um dos procedimentos a seguir para criar ou modificar um grupo de agentes.

<div>


> [!NOTE]  
> Um administrador, por exemplo, CsVoiceAdministrator, deve habilitar usuários do Enterprise Voice e do Lync Server antes que os usuários possam ser atribuídos a grupos de agente. Se você for um dos gerentes de grupo de resposta delegados para um fluxo de trabalho gerenciado, poderá criar grupos de agente e usar os grupos de agente nos fluxos de trabalho que você gerencia.



</div>

<div>


> [!IMPORTANT]  
> Quando você atribui usuários como agentes de grupo de resposta, informe-os de que, se eles tiverem o modo Privacidade habilitado, precisarão pesquisar por contatos "RGS Presence Watcher" e adicioná-los à sua lista Contatos. Agentes que tem o modo Privacidade habilitado, mas não tem "RGS Presence Watcher" em sua lista de Contatos, não podem receber chamadas no grupo de resposta. Agentes que não têm o modo Privacidade habilitado não são afetados.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a>Para usar o painel de controle do Lync Server para criar ou modificar um grupo de agente

1.  Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.
    
    <div>
    

    > [!NOTE]  
    > Se você é um dos Gerentes de Grupo de Resposta delegados para um fluxo de trabalho gerenciado, você pode criar grupos e os usar nos fluxos de trabalho que você gerencia.

    
    </div>

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Grupos de resposta**e depois em **Grupo**.

4.  Na página **Grupo**, execute um dos seguintes procedimentos:
    
      - Para criar um novo grupo de agentes, clique em **Novo**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço **ApplicationServer** para o qual você deseja adicionar o grupo. Na lista resultante de serviços, clique no serviço desejado e em **OK**.
    
      - Para modificar um grupo de agentes existente, digite todo ou parte do nome do grupo de agentes no campo de pesquisa. Na lista de resultados, clique no grupo desejado, clique em **Editar**e depois, clique em **Exibir Detalhes**.

5.  Em **Nome**, digite o nome que identifica o grupo de agentes.

6.  Em **Descrição**, digite uma descrição para o grupo.

7.  Na **Política de participação**, selecione uma das seguintes opções para configurar o comportamento de logon para o grupo:
    
      - Selecione **Informal** para especificar que os agentes no grupo não precisam entrar e sair do grupo. Os agentes serão automaticamente conectados ao grupo quando entrarem no Lync Server 2013.
    
      - Selecione  **Formal** para especificar que os agentes no grupo precisam entrar e sair do grupo. Quando você seleciona essa opção, os agentes clicam em um item de menu no Lync para abrir o Internet Explorer e exibir um console de página da Web para entrar e sair do grupo.

8.  Em **Tempo de alerta (segundos)**, especifique a duração em segundos do toque para um agente antes de oferecer a chamada para o próximo agente disponível (o padrão é de 20 segundos).
    
    <div>
    

    > [!IMPORTANT]  
    > A configuração Tempo de alerta do agente não pode ultrapassar 180 segundos. Caso contrário, o aplicativo do cliente rejeitará a chamada devido ao fato de o timer de transação SIP atingir seu tempo máximo de espera.

    
    </div>

9.  No **Método de roteamento**, selecione o método para roteamento de chamadas a agentes no grupo da seguinte maneira:
    
      - Para oferecer uma nova chamada primeiro ao agente que esteve ociosa o mais longo (teve uma presença de **disponível** ou inativo no **** Lync Server a mais longa), clique em ociosa mais **longa**.
    
      - Para oferecer uma nova chamada para todos os agentes disponíveis ao mesmo tempo, clique em **Em paralelo**. A chamada é enviada ao primeiro agente que a aceitar.
    
      - Para oferecer uma nova chamada a cada operador um após o outro, clique em  **Round robin**.
    
      - Para sempre oferecer uma nova chamada aos agentes na ordem em que estão na lista **Agentes**, clique em **Em série**.
    
      - Para oferecer uma nova chamada para todos os agentes conectados ao Lync Server 2013 e o aplicativo de grupo de resposta ao mesmo tempo, independentemente da presença atual, clique em **atendente**. Os usuários do atendente do Lync 2010 configurados como agentes podem ver todas as chamadas que estão aguardando e atender às chamadas em qualquer ordem. A chamada é enviada para o primeiro agente que a aceita, depois do qual os outros usuários do Lync 2010 Attendant não visualizam mais a chamada.

10. Em  **Agentes**, especifique como você deseja criar sua lista de agentes:
    
      - Para usar uma lista de agentes personalizada, clique em **Definir um grupo personalizado de agentes**e execute um dos seguintes procedimentos:
        
          - Para adicionar um usuário ao grupo de agentes, clique em  **Selecionar**, depois no campo de pesquisa  **Selecionar Agentes**, digite todo ou parte do nome do usuário que você quer adicionar ao grupo e clique em  **Localizar**. Na lista de agentes resultante, clique no usuário que você quer adicionar e clique em  **OK**.
        
          - Para remover um usuário do grupo de agentes, na lista de agentes, clique no usuário que deseja remover e clique em **Remover**.
        
          - Para alterar a ordem em que os agentes são oferecidos às chamadas nos grupos usando rodízio ou encaminhamento em série, na lista de agentes, clique em um usuário e depois clique em seta para cima ou na seta para baixo.
    
      - Para usar uma lista de distribuição do Microsoft Exchange Server como grupo de agentes, clique em **Usar uma lista de distribuição de email existente**e em **Endereço da lista de distribuição**, digite o endereço de email da lista de distribuição (por exemplo, NetworkSupport@contoso.com).
        
        Se você usar uma lista de distribuição por email, estará sujeito às seguintes restrições:
        
          - Você não pode selecionar várias listas de distribuição para o grupo de operadores. Cada grupo oferece suporte a apenas uma lista de distribuição.
        
          - Se a lista de distribuição contiver uma ou mais listas de distribuição, os membros das listas aninhadas não serão adicionados à lista de operadores.
        
          - Se os roteamentos em série e round robin forem selecionados, o servidor oferecerá uma chamada de entrada ao agente apropriado de acordo com o método de roteamento e com a ordem na qual os agentes estão listados na lista de distribuição.
        
          - Se a lista de distribuição contiver usuários, para os quais o Lync Server 2010 estiver habilitado, porém o Enterprise Voice não estiver habilitado, eles serão adicionados ao grupo de agentes como agentes não funcionais. Garanta que todos os membros da lista de distribuição tenham o Enterprise Voice habilitado em suas contas de usuário.
        
        <div>
        

        > [!IMPORTANT]  
        > Se você usar uma lista de distribuição de email, associações ocultas ou listas ocultas podem ficar visíveis para os usuários ou administradores do grupo de resposta.

        
        </div>
        
        Associações ou listas ocultas podem se tornar visíveis da seguinte maneira:
        
          - Se uma lista de distribuição foi configurada para que a associação fique oculta e o administrador do grupo de resposta atribua a lista de distribuição à lista de agentes, os usuários podem chamar o grupo para descobrir quem são os membros.
        
          - Se uma lista de distribuição foi configurada para que ela fique oculta na lista de endereços global do Exchange, o administrador do grupo de resposta poderá ver a lista de distribuição e atribuí-la à lista de agentes se o processo do grupo de resposta tiver os direitos de usuário adequados e permissões, mesmo se o administrador não tiver as permissões e direitos de usuário adequados.

11. Clique em **Confirmar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a>Para usar o Windows PowerShell para criar ou modificar um grupo de agente

1.  Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Use  **New-CsRgsAgentGroup** para criar um novo grupo de agentes. Use  **Set-CsRgsAgentGroup** para modificar um grupo de agentes existente. Na linha de comando, execute:
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    Por exemplo:
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > A configuração Tempo de alerta do agente não pode ultrapassar 180 segundos. Caso contrário, o aplicativo do cliente rejeitará a chamada devido ao fato de o timer de transação SIP atingir seu tempo máximo de espera.

    
    </div>

4.  Confirme a criação do novo grupo. Execute:
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluir um grupo de agente no Lync Server 2013](lync-server-2013-delete-an-agent-group.md)  


[Gerenciamento de grupos de agente de resposta no Lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

