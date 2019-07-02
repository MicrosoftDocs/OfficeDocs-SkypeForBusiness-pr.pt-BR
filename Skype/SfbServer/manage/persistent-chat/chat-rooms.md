---
title: Gerenciar salas de chat no Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Resumo: saiba como gerenciar salas de chat do servidor de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 5b7345626a42073bf7ebd0cb5f9900c6e15f0e2b
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35417943"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gerenciar salas de chat no Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como gerenciar salas de chat do servidor de chat persistente no Skype for Business Server 2015.
  
Criar e gerenciar sala de chat é mais fácil com o uso correto de categorias. Uma categoria define quem pode criar ou ingressar nas salas de chat. Antes de tentar gerenciar salas de chat, certifique-se de ler categorias de chat [persistente, salas de chat e funções de usuário no Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) e [gerenciar categorias no servidor de chat persistente no Skype for Business Server 2015](categories.md).
  
> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015. 

Você pode configurar e gerenciar salas de chat usando a interface de linha de comando do Windows PowerShell ou usando o cliente Skype for Business se você for membro da sala de chat. Esse tópico descreve como gerenciar salas de chat usando a interface de linha de comando do Windows PowerShell. Se você quiser gerenciar salas de chat usando o cliente Skype for Business, consulte a ajuda do cliente. 
  
As salas de chat podem ser um dos dois tipos: normal e Auditorium. Uma sala Normal permite que todos os membros publiquem e leiam mensagens. Uma sala Auditório permite que apenas Apresentadores publiquem, mas todos podem ler.
  
Quem pode acessar e gerenciar as salas de chat depende das funções de usuários, conforme o seguinte:
  
- Os usuários devem ser Membros de uma sala de chat para poderem publicar e ler mensagens.
    
- Os Apresentadores podem publicar nas salas Auditório.
    
- Os administradores podem excluir qualquer conteúdo (por exemplo, conteúdo publicado antes de determinada data) de qualquer sala de chat para impedir que o banco de dados assuma proporções muito grandes. Eles também podem remover ou substituir mensagens consideradas impróprias para uma sala de chat específica.
    
- Os usuários finais, inclusive os autores das mensagens, não podem excluir conteúdo de nenhuma sala de chat.
    
- Os Gerentes de sala de chat podem fazer alterações em todas as propriedades da sala de chat, incluindo desabilitar salas. No entanto, eles não podem excluir uma sala nem alterar a categoria dela. 
    
- Somente os administradores podem excluir salas de chat após a criação.
    
Você pode configurar e gerenciar salas de chat usando os seguintes cmdlets do Windows PowerShell:
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |Cria uma nova sala de chat  <br/> |
|Set-CsPersistentChatRoom  <br/> |Definir configurações para salas existentes; atribuir usuários e grupos de usuários para a sala  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recuperar informações sobre salas  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Limpar uma sala ou as mensagens de uma sala  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Remover uma sala  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Remover mensagens de uma sala  <br/> |
   
Use o cmdlet **New-CsPersistentChatRoom** para criar salas de chat e o cmdlet **Set-CsPersistentChatRoom** para configurar uma sala de chat existente, incluindo a adição de usuários à sala de chat. Você pode configurar os seguintes parâmetros para as salas de chat:
  
- Desabilitado. Permite que você desative ou ative uma sala de chat. 
    
- Convites. Permite que você habilite ou desabilite os convites da sala de chat, que são usados para notificar usuários quando eles forem adicionados como membros de uma sala de chat. A configuração padrão para convites é herdada, o que faz com que a sala de chat adote a configuração de convite definida na categoria que ela pertence. Definir as configurações de convite para falso no nível da sala de chat permite que a configuração da categoria seja substituída. 
    
- Privacidade. Permite que você especifique se uma sala de chat é Aberta, Fechada ou Secreta. Salas abertas podem ser pesquisadas e acessadas por qualquer pessoa. Salas fechadas podem ser pesquisadas por qualquer pessoa, mas podem ser acessadas apenas por membros. Salas secretas podem ser pesquisadas e acessadas apenas por membros da sala. Por padrão, cada nova sala é configurada inicialmente como Fechada.
    
- Tipo. Permite que você especifique se uma sala de chat é uma sala normal, que aceita mensagens publicadas por qualquer membro ou uma sala Auditorium, que aceita mensagens postadas apenas por um apresentador.
    
- Suplemento. Permite que você associe um suplemento configurado anteriormente à uma sala de chat, fazendo com que o conteúdo da URL seja visualizado por membros durante suas participações.
    
Além dos parâmetros acima, o cmdlet **set-CsPersistentChatRoom** permite atribuir usuários à sala de chat da seguinte maneira:
  
- Membros. Configura a associação para a sala de chat. Você pode adicionar ou remover um ou vários membros usando um único cmdlet especificando o endereço SIP dos usuários. Para permitir que os usuários sejam adicionados em massa, os grupos de distribuição ou as unidades organizacionais do Active Directory também podem ser especificados.
    
- Gerentes. Permite que você atribua gerentes para a sala de chat. Os gerentes têm permissões para definir a associação de uma sala de chat, além de outras configurações.
    
- Apresentadores. Permite que você atribua apresentadores para uma sala de chat tipo Auditório. 
    
  Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
## <a name="create-a-new-room"></a>Criar uma nova sala

Você pode criar uma nova sala usando o cmdlet **New-CsPersistentChatRoom**. Por exemplo, o comando a seguir cria uma nova sala de chat chamada ITChatRoom no pool atl-cs-001.contoso.com. Neste exemplo, a sala de chat é adicionada à categoria de TI:
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**Observação:** O PersistentChatPoolFqdn não será necessário se uma das seguintes opções for verdadeira: 
  
- Há apenas um pool de servidores de chat persistente.
    
- Você oferece um FQDN do pool para a categoria.
    
- Você oferece um FQDN do pool para adicionar a sala.
    
## <a name="configure-an-existing-room"></a>Configurar uma sala existente

Você pode configurar uma sala existente usando o cmdlet **set-CsPersistentChatRoom** . Por exemplo, o comando a seguir atribui user1 como membro e apresentador, Usuário2 como gerente, da testCat Auditorium:
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 O próximo exemplo adiciona todos os usuários da UO NorthAmericaUsers no Active Directory à sala de chat NorthAmerica:
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

O próximo exemplo adiciona todos os membros do grupo de distribuição Finanças à mesma sala de chat:
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>Habilitar ou desabilitar uma sala

Se o tópico de uma sala de chat persistente não for mais relevante, você poderá deixar a sala de chat indisponível para os usuários desabilitá-la. Quando uma sala de chat está desabilitada, todos os membros são desconectados imediatamente da sala. Após uma sala de chat ser desabilitada, os usuários não podem participar novamente ou encontrá-la nas pesquisas de sala de chat.
  
Se o histórico da sala de chat persistir, o conteúdo será preservado quando a sala de chat estiver desabilitada. Entretanto, o conteúdo não será exibido nas pesquisas durante o tempo em que a sala de chat permanecer no estado desabilitado. Se você habilitá-la mais tarde, os usuários poderão pesquisar mensagens que foram publicadas antes da sala de chat ser desabilitada. Para obter informações sobre como configurar o histórico de salas de chat, consulte [gerenciar categorias no servidor de chat persistente no Skype for Business server 2015](categories.md). 
  
Se uma sala de chat for desabilitada, sua lista de associação e outras configurações serão preservadas. Como administrador, você poderá habilitar uma sala que está desabilitada, e não é necessário criar as configurações novamente de maneira manual.
  
Você pode desabilitar uma sala usando o cmdlet **set-CsPersistentChatRoom** e definindo o parâmetro Disabled como true:
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

Para habilitar uma sala de chat, defina o parâmetro Disabled para False:
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>Obter informações sobre salas

Para obter informações sobre as salas configuradas para uso em sua organização, você pode usar o cmdlet **Get-CsPersistentChatRoom**.
  
O comando a seguir retorna informações sobre todas as salas de chat configuradas para uso na organização:
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>Remover todo o conteúdo de uma sala

Você pode remover o conteúdo de uma sala usando o cmdlet **Clear-CsPersistentChatRoom**. Por exemplo, o comando a seguir remove todo o conteúdo da sala de Chat Persistente ITChatRoom, que foi adicionado à sala em ou antes de 1º de março de 2015:
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>Remover uma mensagem de uma sala

Você pode remover uma ou mais mensagens no banco de dados de Chat Persistente e, como opção, substituir a mensagem com uma mensagem padrão ou com uma mensagem fornecida pelo administrador por meio do cmdlet **Remove-CsPersistentChatMessage**. Por exemplo, o comando a seguir remove todas as mensagens da sala de chat ITChatRoom que foram publicadas pelo usuário kenmyer@contoso.com:
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

O próximo exemplo substitui as mensagens removidas pela observação de que a mensagem não está mais disponível:
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>Remover uma sala

Você pode remover uma sala usando o cmdlet **Remove-CsPersistentChatRoom**.
  
Por exemplo, o comando a seguir remove a sala de chat RedmondChatRoom:
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>Mover uma sala de uma categoria para outra

Se um gerente de sala de chat tem privilégios de **Criador** em outra categoria, ele ou ela pode mover a sala de uma categoria para outra. A sala não é excluída nem recriada. É uma alteração de associação dentro do banco de dados.
  
Mudar a categoria de uma sala de chat deve ser feito raramente e com cuidado. Uma categoria determina a associação permitida para a sala de chat, por isso, quando uma sala de chat muda de categoria, todas as listas de controle de acesso do sistema (SACLs) não mais suportadas pela nova categoria são purgadas. Por exemplo, se um usuário for membro da sala e não mais um Membro permitido na nova categoria, a associação da sala será modificada e o usuário será removido da sala.
  

