---
title: Criar ou modificar um grupo de agentes no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Criar ou modificar um grupo de agentes no Grupo de Resposta, no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: dfa09c3341ad47f2646939738cb67db7b7f27304
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837091"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a>Criar ou modificar um grupo de agentes no Skype for Business
 
Criar ou modificar um grupo de agentes no Grupo de Resposta, no Skype for Business Server Enterprise Voice.
  
Ao criar um grupo de operadores, você seleciona os operadores atribuídos ao grupo e especifica configurações de grupo adicionais, como o método de roteamento e se um operador pode entrar e sair do grupo. 
  
Um agente que deve entrar e sair do grupo, que é diferente de entrar ou sair do Skype for Business, é chamado de agente formal. Os operadores formais precisam entrar no grupo para que possam receber as chamadas roteadas para o grupo. Isso pode ser útil para os operadores que respondem às chamadas do grupo em tempo parcial. Os agentes formais entrar e sair de seus grupos clicando em um item de menu no Skype for Business para abrir o navegador da Internet Windows Internet Explorer e exibir um console de página da Web.
  
Um operador que não precisa entrar ou sair do grupo é denominado operador informal. Os agentes informais entrarão automaticamente no grupo quando entrarem no Skype for Business e não poderão sair do grupo.
  
Apenas os usuários locais podem ser operadores. Se um operador for movido de local para online, a chamada do grupo de resposta não será mais roteada para ele.
  
Use um dos procedimentos a seguir para criar ou modificar um grupo de agentes.
  
> [!IMPORTANT]
> Quando você atribuir os usuários como operadores do grupo de resposta, informe-os de que, se tiverem o modo de privacidade habilitado, precisarão pesquisar os contatos do "RGS Presence Watcher" e adicioná-los à sua lista de contatos. Os operadores com o modo de privacidade habilitado, mas que não têm o "RGS Presence Watcher" na lista de contatos, não podem receber chamadas para o grupo de resposta. Os operadores que não têm o modo de privacidade habilitado não são afetados. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a>Para usar o Painel de Controle do Skype for Business Server para criar ou modificar um grupo de agentes

1. Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidos que suportam o Grupo de Resposta.
    
    > [!NOTE]
    > Se você é um dos Gerentes de Grupo de Resposta delegados para um fluxo de trabalho gerenciado, você pode criar grupos e os usar nos fluxos de trabalho que você gerencia. 
  
2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.  
    
3. Na barra de navegação à esquerda, clique em **Grupos de resposta** e depois em **Grupo**.
    
4. Na página **Grupo**, execute um dos seguintes procedimentos:
    
   - Para criar um novo grupo de agentes, clique em **Novo**. No campo de pesquisa **Selecionar um serviço**, digite todo ou parte do nome do serviço **ApplicationServer** para o qual você deseja adicionar o grupo. Na lista resultante de serviços, clique no serviço desejado e em **OK**.
    
   - Para modificar um grupo de agentes existente, digite todo ou parte do nome do grupo de agentes no campo de pesquisa. Na lista de resultados, clique no grupo desejado, clique em **Editar** e depois, clique em **Exibir Detalhes**.
    
5. Em **Nome**, digite o nome que identifica o grupo de agentes.
    
6. Em **Descrição**, digite uma descrição para o grupo.
    
7. Na **Política de participação**, selecione uma das seguintes opções para configurar o comportamento de logon para o grupo:
    
   - Selecione **Informal** para especificar que os agentes no grupo não precisam entrar e sair do grupo. Os agentes entrarão automaticamente no grupo quando entrarem no Skype for Business.
    
   - Selecione **Formal** para especificar que os agentes no grupo precisam entrar e sair do grupo. Quando você seleciona essa opção, os agentes clicam em um item de menu no Skype for Business para abrir o Internet Explorer e exibir um console de página da Web para entrar e sair do grupo.
    
8. Em **Tempo de alerta (segundos)**, especifique a duração em segundos do toque para um agente antes de oferecer a chamada para o próximo agente disponível (o padrão é de 20 segundos).
    
    > [!IMPORTANT]
    > A configuração Tempo de alerta do agente não pode ultrapassar 180 segundos. Caso contrário, o aplicativo do cliente rejeitará a chamada devido ao fato de o timer de transação SIP atingir seu tempo máximo de espera. 
  
9. No **Método de roteamento**, selecione o método para roteamento de chamadas a agentes no grupo da seguinte maneira:
    
   - Para oferecer uma nova chamada primeiro ao agente que ficou ocioso por mais tempo (teve uma presença de Disponível ou **Inativo** no Skype for Business por mais tempo), clique em Ocioso por mais **tempo.**  
    
   - Para oferecer uma nova chamada para todos os operadores disponíveis ao mesmo tempo, clique em **Em paralelo**. A chamada é enviada ao primeiro operador que a aceitar.
    
   - Para oferecer uma nova chamada a cada operador um após o outro, clique em **Round robin**. 
    
   - Para sempre oferecer uma nova chamada aos operadores na ordem em que estão na lista **Operadores**, clique em **Em série**. 
    
   - Para oferecer uma nova chamada para todos os agentes que estão assinados no Skype for Business e no aplicativo grupo de resposta ao mesmo tempo, independentemente de sua presença atual, clique em **Attendant**. Os usuários configurados como agentes podem ver todas as chamadas que estão aguardando e atender chamadas em espera em qualquer ordem. A chamada é enviada ao primeiro agente que a aceita, após o qual os outros agentes não veem mais a chamada.
    
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
    
      - Se a lista de distribuição contiver usuários para os quais o Lync Server 2010 está habilitado, mas o Enterprise Voice não está habilitado, eles serão adicionados ao grupo de agentes como agentes não habilitadas. Certifique-se de que todos os membros da lista de distribuição tenham o Enterprise Voice habilitado para suas contas de usuário.
    
    > [!IMPORTANT]
    > Se você usar uma lista de distribuição de email, associações ocultas ou listas ocultas poderão se tornar visíveis para o administrador ou usuários do Grupo de Resposta. 
  
    Associações ou listas ocultas podem se tornar visíveis da seguinte maneira:
    
     - Se uma lista de distribuição tiver sido configurada para que a associação seja ocultada e o administrador do Grupo de Resposta atribuir a lista de distribuição à lista de agentes, os usuários poderão ligar para o grupo para descobrir quem são os membros. 
    
     - Se uma lista de distribuição tiver sido configurada para que ela seja ocultada na Lista de Endereços Global do Exchange, o administrador do Grupo de Resposta poderá ver a lista de distribuição e atribuí-la à lista de agentes se o processo do Grupo de Resposta tiver os direitos e permissões de usuário apropriados, mesmo que o administrador não tenha os direitos e permissões de usuário apropriados.
    
11. Clique em **Confirmar**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a>Para usar o Shell de Gerenciamento do Skype for Business Server para criar ou modificar um grupo de agentes

1. Faça logoff como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidos que suportam o Grupo de Resposta.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
3. Use **New-CsRgsAgentGroup** para criar um novo grupo de agentes. Use  **Set-CsRgsAgentGroup** para modificar um grupo de agentes existente. Na linha de comando, execute:
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    Por exemplo:
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > A configuração Tempo de alerta do agente não pode ultrapassar 180 segundos. Caso contrário, o aplicativo do cliente rejeitará a chamada devido ao fato de o timer de transação SIP atingir seu tempo máximo de espera. 
  
4. Confirme a criação do novo grupo. Execute:
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a>Confira também

[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[Set-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[Get-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
