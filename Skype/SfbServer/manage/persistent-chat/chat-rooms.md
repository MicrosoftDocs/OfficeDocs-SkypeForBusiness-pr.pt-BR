---
title: Gerenciar salas de chat no Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Resumo: saiba como gerenciar salas de chat do Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 63566d897901be32b7d0f33ea099bac202e61515
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830845"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gerenciar salas de chat no Servidor de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Saiba como gerenciar salas de chat do Servidor de Chat Persistente no Skype for Business Server 2015.
  
Criar e gerenciar salas de chat é muito mais fácil com o uso correto de categorias. Uma categoria define quem pode criar ou ingressar nas salas de chat. Antes de tentar gerenciar salas de chat, leia categorias de chat persistente, salas de chat e funções de usuário no [Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) e Gerenciar categorias no Servidor de Chat Persistente [no Skype for Business Server 2015](categories.md).
  
> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015. 

Você pode configurar e gerenciar salas de chat usando a interface Windows PowerShell linha de comando ou usando o cliente Skype for Business se você for membro da sala de chat. Este tópico descreve como gerenciar salas de chat usando a interface Windows PowerShell linha de comando. Se você quiser gerenciar salas de chat usando o Skype for Business cliente, consulte a ajuda do cliente. 
  
As salas de chat podem ser de dois tipos: Normal e Auditório. Uma sala de chat Normal permite que todos os membros postem e leiam mensagens. Um Auditório é um tipo de sala de chat onde somente apresentadores podem postar, mas todos podem ler.
  
Who pode acessar e gerenciar salas de chat depende das funções do usuário da seguinte forma:
  
- Os usuários devem ser Membros de uma sala de chat para poder postar e ler mensagens.
    
- Os apresentadores têm permissão para postar em salas do Auditório.
    
- Os administradores podem excluir qualquer conteúdo (por exemplo, conteúdo postado antes de determinada data) de qualquer sala de char para impedir que o banco de dados assuma proporções muito grandesm. Os administradores também podem remover ou substituir mensagens consideradas inadequadas para uma sala de chat específica.
    
- Os usuários finais, incluisive os autores das mensagens, não podem excluir conteúdo de nenhuma sala de chat.
    
- Os gerentes da sala de chat podem fazer alterações em todas as propriedades da sala de chat, incluindo a desabilitação de salas. No entanto, os gerentes não podem excluir uma sala ou alterar a categoria de uma sala. 
    
- Somente os administradores podem excluir uma sala de chat depois que ela tiver sido criada.
    
Você pode configurar e gerenciar salas de chat usando os seguintes cmdlets Windows PowerShell:
  

|**Cmdlet**|**Descrição**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |Criar uma nova sala de chat  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configurar configurações para uma sala existente; atribuir usuários e grupos de usuários à sala  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recuperar informações sobre salas  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Limpar uma sala ou mensagens de uma sala  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Remover uma sala  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Remover mensagens de uma sala  <br/> |
   
Você usa o cmdlet **New-CsPersistentChatRoom** para criar salas de chat e o cmdlet **Set-CsPersistentChatRoom** para configurar uma sala de chat existente, incluindo a adição de usuários à sala de chat. Você pode configurar os seguintes parâmetros para salas de chat:
  
- Desabilitado. Permite desabilitar ou habilitar uma sala de chat. 
    
- Convites. Permite habilitar ou desabilitar convites de sala de chat, que são usados para notificar os usuários quando eles foram adicionados como membros da sala de chat. A configuração padrão para convites herdados, que fez com que a sala de chat adotasse a configuração de convite configurada na categoria à qual pertence. Configurar a configuração de convites como false no nível da sala de chat permite que a configuração de categoria seja anulada. 
    
- Privacidade. Permite especificar se uma sala de chat é Open, Closed ou Secret. Salas abertas podem ser pesquisadas e acessadas por qualquer pessoa. As salas fechadas podem ser pesquisadas por qualquer pessoa, mas só podem ser acessadas por membros. As salas secretas podem ser pesquisadas e acessadas somente por membros da sala. Por padrão, cada nova sala é configurada inicialmente como Closed.
    
- Digite. Permite especificar se uma sala de chat é uma sala Normal, que aceita mensagens postadas por qualquer membro, ou uma sala auditório, que aceita mensagens postadas somente por um apresentador.
    
- Addin. Permite associar um complemento configurado anteriormente a uma sala de chat, o que permite que o conteúdo da URL seja exibido pelos membros durante a participação.
    
Além dos parâmetros acima, o cmdlet **Set-CsPersistentChatRoom** permite atribuir usuários à sala de chat da seguinte forma:
  
- Membros. Configura a associação para a sala de chat. Você pode adicionar ou remover os membros individuais ou múltiplos usando um único cmdlet especificando o endereço SIP dos usuários. Para permitir que os usuários sejam adicionados em massa, unidades organizacionais ou grupos de distribuição do Active Directory também podem ser especificados.
    
- Gerentes. Permite atribuir gerentes à sala de chat. Os gerentes têm as permissões para definir a associação de uma sala de chat juntamente com outras configurações.
    
- Apresentadores. Permite atribuir apresentadores a uma sala de chat do Auditório. 
    
  Para obter detalhes sobre sintaxe, incluindo todos os parâmetros, consulte Skype for Business Server Shell de Gerenciamento [2015](../management-shell.md).
  
## <a name="create-a-new-room"></a>Criar uma nova sala

Você pode criar uma nova sala usando o cmdlet **New-CsPersistentChatRoom.** Por exemplo, o comando a seguir cria uma nova sala de chat chamada ITChatRoom no pool atl-cs-001.contoso.com. Neste exemplo, a sala de chat é adicionada à categoria de IT:
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**Observação:** PersistentChatPoolFqdn não será necessário se um dos seguintes for verdadeiro: 
  
- Há apenas um pool de Servidor de Chat Persistente.
    
- Você oferece um FQDN do pool para a categoria.
    
- Você oferece um FQDN do pool para adicionar a sala.
    
## <a name="configure-an-existing-room"></a>Configurar uma sala existente

Você pode configurar uma sala existente usando o cmdlet **Set-CsPersistentChatRoom.** Por exemplo, o comando a seguir atribui user1 como membro e apresentador e user2 como gerente da sala auditório testCat:
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 O próximo exemplo adiciona todos os usuários da UO NorthAmericaUsers no active Directory à sala de chat NorthAmerica:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

O próximo exemplo adiciona todos os membros do grupo de distribuição Finanças à mesma sala de chat:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>Desabilitar ou habilitar uma sala

Se o tópico de uma sala de Chat Persistente não for mais relevante, você poderá tornar a sala de chat indisponível para os usuários desabilitando-a. Quando uma sala de chat está desabilitada, todos os membros são desconectados imediatamente da sala. Após uma sala de chat é desabilitada, os usuários não podem participar novamente ou encontrar nas pesquisas de sala de chat.
  
Se o histórico da sala de chat persistir, o conteúdo será preservado quando a sala de chat estiver desabilitada. No entanto, este conteúdo não será exibido nas pesquisas durante o momento que a sala de chat permanece em um estado desabilitado. Se você posteriormente habilitar a sala de chat, os usuários podem pesquisar por mensagens publicadas antes da sala de chat ser desabilitada. Para obter informações sobre como configurar o histórico da sala de chat, consulte [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md). 
  
Se uma sala de chat for desabilitada, sua lista de associações e outras configurações serão preservadas. Como administrador, você pode habilitar uma sala que foi desabilitada e não precisa criar manualmente as configurações.
  
Você pode desabilitar uma sala usando o cmdlet **Set-CsPersistentChatRoom** e definindo o parâmetro Disabled como True:
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

Para habilitar uma sala de chat, de definir o parâmetro Disabled como False:
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>Obter informações sobre salas

Para obter informações sobre as salas configuradas para uso em sua organização, você pode usar o cmdlet **Get-CsPersistentChatRoom.**
  
O comando a seguir retorna informações sobre todas as salas de chat configuradas para uso na organização:
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>Remover todo o conteúdo de uma sala

Você pode remover conteúdo de uma sala usando o cmdlet **Clear-CsPersistentChatRoom.** Por exemplo, o comando a seguir remove todo o conteúdo da sala de Chat Persistente ITChatRoom que foi adicionada à sala em ou antes de 1º de março de 2015:
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>Remover uma mensagem de uma sala

Você pode remover uma ou mais mensagens no banco de dados de Chat Persistente e, opcionalmente, substituir a mensagem por uma mensagem padrão ou por uma mensagem fornecida pelo administrador, usando o cmdlet **Remove-CsPersistentChatMessage.** Por exemplo, o comando a seguir remove todas as mensagens da sala de chat ITChatRoom que foram postadas pelo usuário kenmyer@contoso.com:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

O próximo exemplo substitui todas as mensagens removidas pela observação de que a mensagem não está mais disponível:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>Remover uma sala

Você pode remover uma sala usando o cmdlet **Remove-CsPersistentChatRoom.**
  
Por exemplo, o seguinte comando remove a sala de chat RedmondChatRoom:
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>Mover uma sala de uma categoria para outra

Se um gerente de sala de chat tiver **privilégios** de Criador em outra categoria, ele poderá mover a sala de uma categoria para outra. A sala não é excluída e recriada. É uma mudança de associação no banco de dados.
  
Alterar uma categoria de sala de chat deve ser feita raramente e com cautela. Uma categoria determina o membro permitido para a sala de chat, por isso, quando uma sala de chat muda de categoria, todas as listas de controle de acesso ao sistema (SACLs) não mais suportados pela nova categoria são purgadas. Por exemplo, se um usuário era membro da sala e não é mais um membro permitido na nova categoria, a associação de sala será modificada e o usuário será removido da sala.
  

