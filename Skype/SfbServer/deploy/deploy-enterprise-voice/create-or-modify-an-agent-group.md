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
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a>Criar ou modificar um grupo de agente no Skype for Business
 
Crie ou modifique um grupo de agente no grupo resposta no Skype for Business Server Enterprise Voice.
  
Ao criar um grupo de operadores, você seleciona os operadores atribuídos ao grupo e especifica configurações de grupo adicionais, como o método de roteamento e se um operador pode entrar e sair do grupo. 
  
Um agente que deve entrar e sair do grupo, que é diferente de entrar ou sair do Skype for Business, é chamado de agente formal. Os operadores formais precisam entrar no grupo para que possam receber as chamadas roteadas para o grupo. Isso pode ser útil para os operadores que respondem às chamadas do grupo em tempo parcial. Os agentes formais entram e saem de seus grupos clicando em um item de menu no Skype for Business para abrir o navegador da Internet do Windows Internet Explorer e exibir um console de página da Web.
  
Um operador que não precisa entrar ou sair do grupo é denominado operador informal. Agentes informais são automaticamente conectados ao grupo quando eles se conectam ao Skype for Business, e não podem sair do grupo.
  
Somente os usuários no local podem ser agentes. Se um agente for movido do local para o online, as chamadas em grupo de resposta não serão roteadas para esse agente.
  
Use um dos procedimentos a seguir para criar ou modificar um grupo de agentes.
  
> [!IMPORTANT]
> Quando você atribui usuários como agentes de grupo de resposta, informe-os de que, se eles tiverem o modo Privacidade habilitado, precisarão pesquisar por contatos "RGS Presence Watcher" e adicioná-los à sua lista Contatos. Agentes que tem o modo Privacidade habilitado, mas não tem "RGS Presence Watcher" em sua lista de Contatos, não podem receber chamadas no grupo de resposta. Agentes que não têm o modo Privacidade habilitado não são afetados. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>Para usar o painel de controle do Skype for Business Server para criar ou modificar um grupo de agente

1. Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.
    
    > [!NOTE]
    > Se você é um dos Gerentes de Grupo de Resposta delegados para um fluxo de trabalho gerenciado, você pode criar grupos e os usar nos fluxos de trabalho que você gerencia. 
  
2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.  
    
3. Na barra de navegação à esquerda, clique em **Grupos de resposta**e depois em **Grupo**.
    
4. Na página **Grupo**, execute um dos seguintes procedimentos:
    
   - Para criar um novo grupo de agentes, clique em **Novo**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço **ApplicationServer** para o qual você deseja adicionar o grupo. Na lista resultante de serviços, clique no serviço desejado e em **OK**.
    
   - Para modificar um grupo de agentes existente, digite todo ou parte do nome do grupo de agentes no campo de pesquisa. Na lista de resultados, clique no grupo desejado, clique em **Editar**e depois, clique em **Exibir Detalhes**.
    
5. Em **Nome**, digite o nome que identifica o grupo de agentes.
    
6. Em **Descrição**, digite uma descrição para o grupo.
    
7. Na **Política de participação**, selecione uma das seguintes opções para configurar o comportamento de logon para o grupo:
    
   - Selecione **Informal** para especificar que os agentes no grupo não precisam entrar e sair do grupo. Os agentes são conectados automaticamente ao grupo quando entram no Skype for Business.
    
   - Selecione  **Formal** para especificar que os agentes no grupo precisam entrar e sair do grupo. Quando você seleciona essa opção, os agentes clicam em um item de menu no Skype for Business para abrir o Internet Explorer e exibir um console de página da Web para entrar e sair do grupo.
    
8. Em **Tempo de alerta (segundos)**, especifique a duração em segundos do toque para um agente antes de oferecer a chamada para o próximo agente disponível (o padrão é de 20 segundos).
    
    > [!IMPORTANT]
    > A configuração Tempo de alerta do agente não pode ultrapassar 180 segundos. Caso contrário, o aplicativo do cliente rejeitará a chamada devido ao fato de o timer de transação SIP atingir seu tempo máximo de espera. 
  
9. No **Método de roteamento**, selecione o método para roteamento de chamadas a agentes no grupo da seguinte maneira:
    
   - Para oferecer uma nova chamada primeiro ao agente que esteve ociosa o mais longo (teve uma presença de **disponível** ou inativo no **** Skype for Business por mais tempo), clique em ociosa mais **longa**. 
    
   - Para oferecer uma nova chamada para todos os agentes disponíveis ao mesmo tempo, clique em **Em paralelo**. A chamada é enviada ao primeiro agente que a aceitar.
    
   - Para oferecer uma nova chamada a cada operador um após o outro, clique em  **Round robin**. 
    
   - Para sempre oferecer uma nova chamada aos agentes na ordem em que estão na lista **Agentes**, clique em **Em série**. 
    
   - Para oferecer uma nova chamada para todos os agentes conectados ao Skype for Business e ao aplicativo de grupo de resposta ao mesmo tempo, independentemente da presença atual, clique em **atendente**. Os usuários configurados como agentes podem ver todas as chamadas que estão aguardando e responder às chamadas em espera em qualquer ordem. A chamada é enviada ao primeiro agente que a aceita, e os outros usuários não veem mais a chamada.
    
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
    
    > [!IMPORTANT]
    > Se você usar uma lista de distribuição de email, associações ocultas ou listas ocultas podem ficar visíveis para os usuários ou administradores do grupo de resposta. 
  
    Associações ou listas ocultas podem se tornar visíveis da seguinte maneira:
    
     - Se uma lista de distribuição foi configurada para que a associação fique oculta e o administrador do grupo de resposta atribua a lista de distribuição à lista de agentes, os usuários podem chamar o grupo para descobrir quem são os membros. 
    
     - Se uma lista de distribuição foi configurada para que ela fique oculta na lista de endereços global do Exchange, o administrador do grupo de resposta poderá ver a lista de distribuição e atribuí-la à lista de agentes se o processo do grupo de resposta tiver os direitos de usuário adequados e permissões, mesmo se o administrador não tiver as permissões e direitos de usuário adequados.
    
11. Clique em **Confirmar**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>Para usar o Shell de gerenciamento do Skype for Business Server para criar ou modificar um grupo de agente

1. Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Use  **New-CsRgsAgentGroup** para criar um novo grupo de agentes. Use  **Set-CsRgsAgentGroup** para modificar um grupo de agentes existente. Na linha de comando, execute:
    
   ```
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    Por exemplo:
    
   ```
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > A configuração Tempo de alerta do agente não pode ultrapassar 180 segundos. Caso contrário, o aplicativo do cliente rejeitará a chamada devido ao fato de o timer de transação SIP atingir seu tempo máximo de espera. 
  
4. Confirme a criação do novo grupo. Execute:
    
   ```
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a>Confira também

[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
