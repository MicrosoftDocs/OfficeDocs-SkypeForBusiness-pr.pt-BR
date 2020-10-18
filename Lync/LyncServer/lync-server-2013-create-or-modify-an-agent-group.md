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
# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a>Criar ou modificar um grupo de agentes no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-07_

Use um dos procedimentos a seguir para criar ou modificar um grupo de agentes.

<div>


> [!NOTE]  
> Um administrador — por exemplo, CsVoiceAdministrator — deve habilitar usuários para o Enterprise Voice e o Lync Server antes que os usuários possam ser atribuídos a grupos de agentes. Se você é um dos Gerentes de Grupo de Resposta designados para um fluxo de trabalho gerenciado, você pode criar grupos de agentes e os usar nos fluxos de trabalho que você gerencia.



</div>

<div>


> [!IMPORTANT]  
> Quando você atribuir os usuários como operadores do grupo de resposta, informe-os de que, se tiverem o modo de privacidade habilitado, precisarão pesquisar os contatos do "RGS Presence Watcher" e adicioná-los à sua lista de contatos. Os operadores com o modo de privacidade habilitado, mas que não têm o "RGS Presence Watcher" na lista de contatos, não podem receber chamadas para o grupo de resposta. Os operadores que não têm o modo de privacidade habilitado não são afetados.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a>Para usar o painel de controle do Lync Server para criar ou modificar um grupo de agentes

1.  Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.
    
    <div>
    

    > [!NOTE]  
    > Se você é um dos Gerentes de Grupo de Resposta delegados para um fluxo de trabalho gerenciado, você pode criar grupos e os usar nos fluxos de trabalho que você gerencia.

    
    </div>

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Grupos de resposta** e depois em **Grupo**.

4.  Na página **Grupo**, execute um dos seguintes procedimentos:
    
      - Para criar um novo grupo de agentes, clique em **Novo**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço **ApplicationServer** para o qual você deseja adicionar o grupo. Na lista resultante de serviços, clique no serviço desejado e em **OK**.
    
      - Para modificar um grupo de agentes existente, digite todo ou parte do nome do grupo de agentes no campo de pesquisa. Na lista de resultados, clique no grupo desejado, clique em **Editar** e depois, clique em **Exibir Detalhes**.

5.  Em **Nome**, digite o nome que identifica o grupo de agentes.

6.  Em **Descrição**, digite uma descrição para o grupo.

7.  Na **Política de participação**, selecione uma das seguintes opções para configurar o comportamento de logon para o grupo:
    
      - Selecione **Informal** para especificar que os agentes no grupo não precisam entrar e sair do grupo. Os agentes são automaticamente conectados ao grupo quando entram no Lync Server 2013.
    
      - Selecione **Formal** para especificar que os agentes no grupo precisam entrar e sair do grupo. Quando você seleciona essa opção, os agentes clicam em um item de menu no Lync para abrir o Internet Explorer e exibir um console de página da Web para entrar e sair do grupo.

8.  Em **Tempo de alerta (segundos)**, especifique a duração em segundos do toque para um agente antes de oferecer a chamada para o próximo agente disponível (o padrão é de 20 segundos).
    
    <div>
    

    > [!IMPORTANT]  
    > A configuração Tempo de alerta do agente não pode ultrapassar 180 segundos. Caso contrário, o aplicativo do cliente rejeitará a chamada devido ao fato de o timer de transação SIP atingir seu tempo máximo de espera.

    
    </div>

9.  No **Método de roteamento**, selecione o método para roteamento de chamadas a agentes no grupo da seguinte maneira:
    
      - Para oferecer uma nova chamada primeiro para o agente que esteve ocioso o mais longo (teve uma presença de **disponível** ou **inativo** no Lync Server o mais longo), clique em **ocioso mais longo**.
    
      - Para oferecer uma nova chamada para todos os operadores disponíveis ao mesmo tempo, clique em **Em paralelo**. A chamada é enviada ao primeiro operador que a aceitar.
    
      - Para oferecer uma nova chamada a cada operador um após o outro, clique em **Round robin**.
    
      - Para sempre oferecer uma nova chamada aos operadores na ordem em que estão na lista **Operadores**, clique em **Em série**.
    
      - Para oferecer uma nova chamada a todos os agentes que estão conectados ao Lync Server 2013 e ao aplicativo de grupo de resposta ao mesmo tempo, independentemente de sua presença atual, clique em **atendedor**. Os usuários do atendedor do Lync 2010 que estão configurados como agentes podem ver todas as chamadas que estão aguardando e respondendo a chamadas em espera em qualquer ordem. A chamada é enviada ao primeiro agente que a aceita, após o qual os outros usuários do Lync 2010 Attendant não mais veem a chamada.

10. Em **Agentes**, especifique como você deseja criar sua lista de agentes:
    
      - Para usar uma lista de agentes personalizada, clique em **Definir um grupo personalizado de agentes** e execute um dos seguintes procedimentos:
        
          - Para adicionar um usuário ao grupo de agentes, clique em **Selecionar**, depois no campo de pesquisa **Selecionar Agentes**, digite todo ou parte do nome do usuário que você quer adicionar ao grupo e clique em **Localizar**. Na lista de agentes resultante, clique no usuário que você quer adicionar e clique em **OK**.
        
          - Para remover um usuário do grupo de agentes, na lista de agentes, clique no usuário que deseja remover e clique em **Remover**.
        
          - Para alterar a ordem em que os agentes são oferecidos às chamadas nos grupos usando rodízio ou encaminhamento em série, na lista de agentes, clique em um usuário e depois clique em seta para cima ou na seta para baixo.
    
      - Para usar uma lista de distribuição do Microsoft Exchange Server como grupo de agentes, clique em **Usar uma lista de distribuição de email existente** e em **Endereço da lista de distribuição**, digite o endereço de email da lista de distribuição (por exemplo, NetworkSupport@contoso.com).
        
        Se você usar uma lista de distribuição por email, estará sujeito às seguintes restrições:
        
          - Você não pode selecionar várias listas de distribuição para o grupo de operadores. Cada grupo oferece suporte a apenas uma lista de distribuição.
        
          - Se a lista de distribuição contiver uma ou mais listas de distribuição, os membros das listas aninhadas não serão adicionados à lista de operadores.
        
          - Se os roteamentos em série e round robin forem selecionados, o servidor oferecerá uma chamada de entrada ao agente apropriado de acordo com o método de roteamento e com a ordem na qual os agentes estão listados na lista de distribuição.
        
          - Se a lista de distribuição contiver usuários para os quais o Lync Server 2010 está habilitado, mas o Enterprise Voice não está habilitado, ele será adicionado ao grupo de agentes como agentes do Dysfunctional. Certifique-se de que todos os membros da lista de distribuição tenham o Enterprise Voice habilitado para suas contas de usuário.
        
        <div>
        

        > [!IMPORTANT]  
        > Se você usar uma lista de distribuição de email, associações ocultas ou listas ocultas podem se tornar visíveis para o administrador ou os usuários do grupo de resposta.

        
        </div>
        
        Associações ou listas ocultas podem se tornar visíveis da seguinte maneira:
        
          - Se uma lista de distribuição tiver sido configurada para que a associação fique oculta e o administrador do grupo de resposta atribuir a lista de distribuição à lista de agentes, os usuários poderão chamar o grupo para descobrir quem são os membros.
        
          - Se uma lista de distribuição tiver sido configurada para que fique oculta na lista de endereços global do Exchange, o administrador do grupo de resposta poderá ver a lista de distribuição e atribuí-la à lista de agentes se o processo do grupo de resposta tiver os direitos e permissões do usuário apropriados, mesmo que o administrador não tenha os direitos e permissões do usuário apropriados.

11. Clique em **Confirmar**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a>Para usar o Windows PowerShell para criar ou modificar um grupo de agentes

1.  Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Use **New-CsRgsAgentGroup** para criar um novo grupo de agentes. Use  **Set-CsRgsAgentGroup** para modificar um grupo de agentes existente. Na linha de comando, execute:
    
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


[Excluir um grupo de agentes no Lync Server 2013](lync-server-2013-delete-an-agent-group.md)  


[Gerenciar grupos de agente de grupo de resposta no Lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)  
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

