---
title: Gerenciar categorias no Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 'Resumo: saiba como gerenciar categorias de servidor de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 8a8e8060db896a272293df3259091d4f7667a7d3
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35417936"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gerenciar categorias no Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como gerenciar categorias persistentes do servidor de chat no Skype for Business Server 2015.
  
Uma categoria é uma estrutura lógica para organizar salas de chat. Uma categoria define um conjunto padrão de listas de controle de acesso (ACLs) para controlar os usuários e grupos de usuários que podem criar ou ingressar nas salas de chat. As categorias de salas de chat contêm salas de chat, mas não outras categorias. Cada categoria descreve o conteúdo com metadados, como Name e Description. A categoria tem propriedades que podem ser definidas para controlar o comportamento das salas de chat pertencentes a ela; por exemplo, se as salas de chat permitem convites ou carregamentos de arquivos, ou contenham o histórico de chats. 
  
Criar e gerenciar salas de chat é mais fácil com o uso correto das categorias. Como um administrador do Servidor de Chat Persistente, você poderá definir Membros Permitidos e Criadores para cada categoria, além de definir as configurações e os comportamentos padrão da sala de chat que serão aplicados à todas as salas de chat criadas na categoria. Por exemplo, se você definir o AllowedMembers da categoria como contoso.com, poderá adicionar qualquer grupo ou usuário na contoso como membro para salas de chat nessa categoria. Se definir Membros permitidos em uma categoria para Vendas, apenas grupos e usuários nesta lista de distribuição poderão ser adicionados como membros nas salas de chat em tal categoria. A propriedade Criadores permite que você controle quem pode criar salas de chat na categoria. Após a sala de chat ser criada, qualquer pessoa do grupo Membros Permitidos poderá ser designada como Gerente para operações de gerenciamento contínuo nas salas (por exemplo, alterações e aprovações de associação).
  
Definindo Membros Permitidos e Criadores na categoria com os seguintes benefícios:
  
- Todas as salas de chat nesta categoria estão limitadas às restrições definidas no nível da categoria. Você pode usar isso para segregar as salas de chat com base nas necessidades de negócios e políticas de acesso.
    
- Um usuário que está na lista Criadores pode criar novas salas de chat em tal categoria. Se você desejar implementar um sistema onde um número restrito de pessoas na organização possa criar salas de chat, este controle pode ser usado para atender a essas exigências. 
    
Usuários, Unidades Organizacionais (OUs) e grupos de usuários identificados como Criadores da categoria são os únicos indivíduos e grupos que podem criar salas na categoria. Após a categoria ser criada, você pode escolher usuários, OUs e grupos de usuários da lista Membros Permitidos da categoria como gerentes da sala de chat e membros para gerenciar e participar da sala. 
  
Antes de configurar categorias, certifique-se de ler as [categorias de chat persistente, salas de chat e funções de usuário no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).
  
Você pode configurar e gerenciar categorias usando o Painel de Controle ou por meio dos cmdlets do Windows PowerShell.

> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>Configurar categorias usando o Painel de Controle

1. A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implantação interna.
    
2. No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Categoria**.
    
    Para várias implantações de pool do servidor de chat persistente, selecione o pool apropriado na lista suspensa.
    
4. Na página **Categoria**, clique em **Novo** ou **Editar**.
    
5. Em **selecionar um serviço**, selecione o serviço correspondente ao pool de servidores de chat persistente em que a categoria precisa ser criada. O serviço é o pool de servidores de chat persistentes que o cliente de chat persistente usa para identificar a qual pool a categoria pertence. Uma categoria pode pertencer a apenas um pool de servidores de chat persistente e não pode ser movida para ou compartilhada com outro pool.
    
6. Em **Nova categoria**, faça o seguinte:
    
   - Em  **Nome**, especifique um nome para a nova categoria de sala.
    
   - Em  **Descrição**, forneça uma descrição detalhada para a categoria da sala (por exemplo, uma categoria de sala para Contoso).
    
   - Para controlar se os convites podem ser ativados por salas de chat que pertencem a tal categoria, selecione ou limpe a caixa de marcação **Habilitar convites**. Se marcado, as salas nesta categoria poderão ter convites ativados ou desativados; em caso de não marcado, as salas nessa categoria não podem ter convite. Se uma sala tem convites em, quando um novo membro é adicionado a uma sala, ele recebe uma notificação da nova sala em seu cliente de chat persistente.
    
   - Para controlar o envio de arquivo nas salas de chat pertencentes a esta categoria, selecione ou desmarque a caixa de seleção **Habilitar carregamento de arquivo**. Se estiver marcada, as salas desta categoria podem habilitar ou desabilitar carregamentos de arquivos; se estiver desmarcada, as salas nesta categoria não podem ter arquivos carregados.
    
   - Para controlar o histórico de chats, marque ou desmarque a caixa de seleção **habilitar histórico de chats** . Se marcada, as salas de chat se tornam persistentes; caso contrário, as mensagens de chat não são persistentes. Se a conformidade estiver habilitada, as salas de chat serão salvas em conformidade, mas os usuários não poderão acessar mensagens antigas. Essa opção pode ser usada para salas designadas para colaborações ad hoc em tempo real que não precisam de histórico de chats para serem mantidas.
    
7. Em  **Editar categoria**, faça o seguinte:
    
   - Em **Associação**, na seção **Membros permitidos** , adicione ou remova usuários e outros princípios de serviços de domínio do Active Directory (usuários, grupos de distribuição, unidades organizacionais e assim por diante) que podem ser adicionados como membros de salas de chat pertencente à categoria. As entidades permitidas por uma categoria podem pesquisar por salas na categoria (a menos que uma sala esteja oculta, caso o qual apenas membros da sala podem pesquisar por ela no diretório).
    
   - Em **Associação**, na seção **Membros negados** , adicione ou remova usuários e outras entidades de segurança do Active Directory associadas a membros sendo negados da sala.
    
   - Em **Associação**, na seção **criadores** , adicione ou remova usuários e outras entidades de segurança do Active Directory associadas aos criadores para a categoria. Um criador é um usuário que tem permissões de criar salas de chat e atribuir gerentes e membros de sala de chat.
    
8. Clique em **Confirmar**.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Configurar categorias usando o Windows PowerShell

Você pode configurar categorias usando os seguintes cmdlets do Windows PowerShell:
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Criar uma nova categoria  <br/> |
|Set-CsPersistentChatCategory  <br/> |Definir configurações para uma categoria existente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recuperar informações sobre categorias  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Remover uma categoria  <br/> |
   
É possível configurar os seguintes parâmetros para categorias:
  
- EnableFileUpload. Permite envios de arquivos para as salas de chat na categoria.
    
- EnableInvitations. Habilita convites para a categoria. Os usuários na lista de Membros Permitidos receberão automaticamente um convite para participar de uma nova sala de chat no momento que ela for criada.
    
- ChatHistory. Habilita ou desabilita o recurso de histórico de chat.
    
- Criadores. Especifica os usuários que têm permissão para criar salas de chat dentro da categoria.
    
- Membros Permitidos. Especifica os usuários que têm permissão para acessar salas de chat dentro da categoria.
    
- DeniedMembers. Lista os usuários que não têm permissão para acessar as salas de chat dentro da categoria.
    
Para obter mais informações sobre a sintaxe cmdlet, incluindo todos os parâmetros, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
### <a name="create-a-new-category"></a>Criar uma nova categoria

Você pode criar uma nova categoria usando o cmdlet **New-CsPersistentChatCategory**. Por exemplo, o comando a seguir cria uma nova categoria chamada HelpDesk no pool atl-cs-001.contoso.com. Neste exemplo, o envio de arquivos está habilitado:
  
```
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Configurar uma categoria existente

Você pode configurar uma categoria existente usando o cmdlet **Set-CsPersistentCategory**.
  
Por exemplo, o comando a seguir especifica que Usuário1 é um AllowedMember e um criador, enquanto que User2 tem acesso negado às salas da categoria:
  
```
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Obter informações sobre categorias

Você pode obter informações sobre categorias usando o cmdlet **Get-CsPersistentChatCategory**. Por exemplo, o comando a seguir retorna as informações para todas as categorias do Chat Persistente na organização:
  
```
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Remover uma categoria

Você pode remover uma categoria usando o cmdlet **Remove-CsPersistentChatCategory**. Antes de remover uma categoria, você deve primeiro excluir todas as salas de chat dela ou movê-las para uma nova categoria. Por exemplo, o comando a seguir remove a categoria que tem a identidade "atl-cs-001.contoso.com\helpdesk":
  
```
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
