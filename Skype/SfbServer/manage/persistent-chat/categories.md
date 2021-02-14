---
title: Gerenciar categorias no Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 'Resumo: Saiba como gerenciar categorias de Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 648629e42994c59f5d6ba5ee5592729f4dff0bbe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815121"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gerenciar categorias no Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como gerenciar categorias de Servidor de Chat Persistente no Skype for Business Server 2015.
  
Uma categoria é uma estrutura lógica para organizar salas de chat. Uma categoria define um conjunto padrão de ACLs (listas de controle de acesso) para controlar os usuários e grupos de usuários que podem criar ou ingressar nas salas de chat. As categorias de sala de chat contêm salas de chat, mas não outras categorias. Cada categoria descreve seu conteúdo com metadados, como Nome e Descrição. A categoria tem propriedades que podem ser definidas para controlar o comportamento das salas de chat pertencentes a ela; por exemplo, se as salas de chat permitem Convites ou Carregamentos de Arquivos ou contêm Histórico de Chat. 
  
Criar e gerenciar salas de chat é muito mais fácil com o uso correto de categorias. Como administrador do Servidor de Chat Persistente, você pode definir AllowedMembers e Criadores para cada categoria e também definir as configurações e os comportamentos padrão da sala de chat que serão aplicados a todas as salas de chat criadas na categoria. Por exemplo, se você definir membros Permitidos da categoria como contoso.com, poderá adicionar qualquer grupo ou usuário da Contoso como membro para salas de chat nessa categoria. Se você definir os Membros Permitidos em uma categoria como Vendas, somente grupos e usuários nesta lista de distribuição poderão ser adicionados como membros às salas de chat nessa categoria. A propriedade Criadores permite controlar quem pode criar salas de chat nessa categoria. Depois que a sala de chat é criada, qualquer pessoa do grupo AllowedMembers pode ser designada como Gerente para operações de gerenciamento contínuas nas salas (por exemplo, alterações de associação e aprovação).
  
Definir uma lista de membros para uma categoria oferece os seguintes benefícios:
  
- Todas as salas de chat nesta categoria estão sujeitas às restrições definidas no nível da categoria. Você pode usar isso para segregar as salas de chat baseando-se nas necessidades de negócios e políticas de acesso.
    
- Um usuário membro na lista Criadores  pode criar novas salas de chat naquela categoria. Se você quiser implementar um sistema em que um número restrito de pessoas na organização possa criar salas de chat, esse controle pode ser usado para atender a esses requisitos. 
    
Usuários, Unidades organizacionais (OUs) e grupos de usuários identificados como Criadores da categoria são os únicos indivíduos e grupos que têm permissão para criar salas na categoria. Depois que a categoria for criada, você poderá escolher usuários, OUs e grupos de usuários na lista AllowedMembers da categoria como gerentes e membros da sala de chat para gerenciar e participar da sala. 
  
Antes de configurar categorias, certifique-se de ler categorias de chat persistente, salas de chat e funções de usuário [no Skype for Business Server 2015.](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)
  
Você pode configurar e gerenciar categorias usando o Painel de Controle ou os cmdlets do Windows PowerShell.

> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here) Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>Configurar categorias usando o Painel de Controle

1. A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.
    
2. No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Categoria**.
    
    Para várias implantações de pool de Servidor de Chat Persistente, selecione o pool apropriado na lista lista.
    
4. Na página **Categoria**, clique em **Novo** ou **Editar**.
    
5. Em **Selecionar um Serviço,** selecione o serviço correspondente ao pool de Servidor de Chat Persistente no qual a categoria precisa ser criada. O serviço é o pool de Servidor de Chat Persistente que o cliente de Chat Persistente usa para identificar a qual pool a categoria pertence. Uma categoria pode pertencer a apenas um pool de Servidor de Chat Persistente e não pode ser movida para outro pool ou compartilhada com outro pool.
    
6. Em **Nova Categoria**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para a nova categoria de sala.
    
   - Em **Descrição**, forneça uma descrição detalhada da categoria de sala (por exemplo, uma categoria de sala para Contoso).
    
   - Para controlar se os convites podem ser habilitados para salas de chat que pertencem a essa categoria, marque ou desmarque a caixa de seleção **Habilitar convites**. Se for marcada, as salas nessa categoria poderão ter os convites ativados ou desativados; se for desmarcada, as salas nessa categoria não terão permissão para enviar convites. Se uma sala tiver convites, quando um novo membro for adicionado a uma sala, ele receberá uma notificação da nova sala em seu cliente de Chat Persistente.
    
   - Para controlar os carregamentos de arquivo nas salas de chat que pertencem a essa categoria, marque ou desmarque a caixa de seleção **Habilitar carregamento de arquivo**. Se for marcada, as salas dessa categoria poderão habilitar ou desabilitar os carregamentos de arquivo; se for desmarcada, as salas dessa categoria não terão permissão para carregamentos de arquivo.
    
   - Para controlar o histórico de chat, marque ou des limpe a **caixa de seleção Habilitar histórico** de chat. Se for marcada, as salas de chats se tornarão persistentes; caso contrário, as mensagens de chat não serão persistentes. Se a conformidade for habilitada, salas de chats serão salvas em conformidade, mas os usuários não poderão acessar mensagens mais antigas. Essa opção pode ser usada para salas designadas para colaborações ad hoc em tempo real que não precisam persistir no histórico do chat.
    
7. Em **Editar Categoria**, faça o seguinte:
    
   - In **Membership**, in the **Allowed members section,** add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are allowed to be added as members of chat rooms belonging to the category. As entidades permitidas por uma categoria podem pesquisar por salas na categoria (a menos que uma sala esteja oculta, caso o qual apenas membros da sala podem pesquisar por ela no diretório).
    
   - Em **Associação,** na seção **Membros** Negados, adicione ou remova usuários e outras entidades do Active Directory associadas aos membros que estão sendo negados da sala.
    
   - Em **Associação,** na seção **Criadores,** adicione ou remova usuários e outras entidades do Active Directory associadas aos criadores da categoria. Um criador é um usuário com permissões para criar salas de chat e atribuir gerentes e membros de sala de chat.
    
8. Clique em **Confirmar**.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Configurar categorias usando o Windows PowerShell

Você pode configurar categorias usando os seguintes cmdlets do Windows PowerShell:
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Criar uma nova categoria  <br/> |
|Set-CsPersistentChatCategory  <br/> |Definir configurações para uma categoria existente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recuperar informações sobre categorias  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Remover uma categoria  <br/> |
   
Você pode configurar os seguintes parâmetros para categorias:
  
- EnableFileUpload. Permite carregamentos de arquivos para as salas de chat na categoria.
    
- EnableInvitations. Habilita convites para a categoria. Os usuários na lista AllowedMembers receberão automaticamente um convite para ingressar em uma nova sala de chat no momento em que a nova sala for criada.
    
- ChatHistory. Habilita ou desabilita o recurso de histórico de chat.
    
- Criadores. Especifica os usuários que têm permissão para criar salas de chat dentro da categoria.
    
- AllowedMembers. Especifica os usuários que têm permissão para acessar salas de chat dentro da categoria.
    
- DeniedMembers. Lista os usuários que não têm permissão de acessar as salas de chat dentro da categoria.
    
Para obter informações completas sobre sintaxe de cmdlet, incluindo todos os parâmetros, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
### <a name="create-a-new-category"></a>Criar uma nova categoria

Você pode criar uma nova categoria usando o cmdlet **New-CsPersistentChatCategory.** Por exemplo, o comando a seguir cria uma nova categoria chamada HelpDesk no pool atl-cs-001.contoso.com. Neste exemplo, o carregamento de arquivos está habilitado:
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Configurar uma categoria existente

Você pode configurar uma categoria existente usando o cmdlet **Set-CsPersistentCategory.**
  
Por exemplo, o comando a seguir especifica que o usuário1 é um AllowedMember e um Criador, enquanto o usuário2 tem acesso negado às salas na categoria:
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Obter informações sobre categorias

Você pode obter informações sobre categorias usando o cmdlet **Get-CsPersistentChatCategory.** Por exemplo, o comando a seguir retorna informações para todas as categorias de Chat Persistente na organização:
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Remover uma categoria

Você pode remover uma categoria usando o cmdlet **Remove-CsPersistentChatCategory.** Antes de remover uma categoria, primeiro você deve excluir todas as salas de chat dela ou mover as salas de chat para uma nova categoria. Por exemplo, o comando a seguir remove a categoria que tem a Identidade "atl-cs-001.contoso.com\helpdesk":
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
