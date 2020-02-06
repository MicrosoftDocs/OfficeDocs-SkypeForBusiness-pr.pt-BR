---
title: Categoria de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: É possível usar a seção Categoria da página Chat Persistente para configurar as categorias. Uma categoria de sala de chat persistente é uma estrutura lógica para organizar salas de chat. Uma categoria define um conjunto padrão de listas de controle de acesso (ACLs) para controle dos usuários e dos grupos de usuários que podem criar ou ingressar em salas de chat. É possível usar as categorias para aplicar paredes éticas entre diferentes subdivisões dentro de suas organizações.
ms.openlocfilehash: de0a638da6de622b9646347c4eaa733deecdd2ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822544"
---
# <a name="persistent-chat-category"></a>Categoria de Chat Persistente
 
É possível usar a seção **Categoria** da página **Chat Persistente** para configurar as categorias. Uma categoria de sala de chat persistente é uma estrutura lógica para organizar salas de chat. Uma categoria define um conjunto padrão de listas de controle de acesso (ACLs) para controle dos usuários e dos grupos de usuários que podem criar ou ingressar em salas de chat. É possível usar as categorias para aplicar paredes éticas entre diferentes subdivisões dentro de suas organizações.
  
As categorias de sala de chat podem conter salas de chat, mas nenhuma outra categoria. Cada categoria descreve seu conteúdo com metadados, como _nome_ e _Descrição_. Além disso, a categoria tem propriedades que podem ser definidas para controlar o comportamento das salas de chat pertencentes a ele, como se as salas de chat permitirem _convites_ ou _carregamentos de arquivos_ou contenham o _histórico de chats_.
  
Para criar uma nova categoria, consulte [gerenciar categorias no servidor de chat persistente no Skype for Business server 2015](../../manage/persistent-chat/categories.md). Se você for um administrador de chat persistente, poderá criar categorias usando o painel de controle ou cmdlets do Windows PowerShell.
  
## <a name="tasks-that-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Categoria**:
  
- Criar ou editar uma nova categoria
    
- Mover uma sala de chat de uma categoria a outra
    
- Excluir sala de chat ou categoria
    
## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar categorias salas de bate-papo

1. A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.
    
2. No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Categoria**.
    
    Para várias implantações de pool do servidor de chat persistente, selecione o pool apropriado na lista suspensa.
    
4. Na página **Categoria**, clique em **Novo** ou **Editar**.
    
5. Em **selecionar um serviço**, selecione o serviço correspondente ao pool de servidores de chat persistente em que a categoria precisa ser criada. O serviço é o pool persistente do servidor de chat que o chat (cliente) persistente usa para identificar a qual pool a categoria pertence. Uma categoria pode pertencer a apenas um pool de servidor de chat persistente e não pode ser movida para outra ou compartilhada com outro pool.
    
6. Em **Nova categoria**, faça o seguinte:
    
7. Em  **Nome**, especifique um nome para a nova categoria de sala.
    
8. Em  **Descrição**, forneça uma descrição detalhada para a categoria da sala (por exemplo, uma categoria de sala para Contoso).
    
9. Para controlar se os convites podem ser ativados por salas de chat que pertencem a tal categoria, selecione ou limpe a caixa de marcação **Habilitar convites**. Se marcado, as salas nesta categoria poderão ter convites ativados ou desativados; em caso de não marcado, as salas nessa categoria não podem ter convite. Se uma sala tem convites em, quando um novo membro é adicionado a uma sala, ele recebe uma notificação da nova sala em seu cliente de chat persistente.
    
10. Para controlar o envio de arquivo nas salas de chat pertencentes a esta categoria, selecione ou desmarque a caixa de seleção **Habilitar carregamento de arquivo**. Se estiver marcada, as salas desta categoria podem habilitar ou desabilitar carregamentos de arquivos; se estiver desmarcada, as salas nesta categoria não podem ter arquivos carregados.
    
     > [!IMPORTANT]
     > Essa configuração é imposta no servidor porque aplicativos personalizados ou clientes de chat em grupo anterior que usam o servidor de chat de grupo do Office Communications Server 2007 R2 ou o Lync Server 2010, o chat em grupo podem postar arquivos para uma sala. O cliente do Lync 2013 não tem recurso de carregamento/download de arquivo, portanto, se você tiver uma implantação do Lync 2013 ou do Lync 2013, não será possível postar arquivos em uma sala de chat do servidor de chat persistente. 
  
11. Para controlar o histórico de chats, marque ou desmarque a caixa de seleção **habilitar histórico de chats** . Se marcada, as salas de chat se tornam persistentes; caso contrário, as mensagens de chat não são persistentes. Se a conformidade estiver habilitada, as salas de chat serão salvas em conformidade, mas os usuários não poderão acessar mensagens antigas. Essa opção pode ser usada para salas designadas para colaborações ad hoc em tempo real que não precisam de histórico de chats para serem mantidas.
    
12. Em  **Editar categoria**, faça o seguinte:
    
    - Em **Associação**, na seção **Membros permitidos** , adicione ou remova usuários e outras entidades de segurança dos serviços de domínio Active Directory (usuários, grupos de distribuição, unidades organizacionais e assim por diante) que podem ser adicionados como membros de salas de chat pertencentes à categoria. As entidades permitidas por uma categoria podem pesquisar por salas na categoria (a menos que uma sala esteja oculta, caso o qual apenas membros da sala podem pesquisar por ela no diretório).
    
    - Em **Associação**, na seção **Membros negados** , adicione ou remova usuários e outras entidades de segurança do Active Directory associadas a membros sendo negados da sala.
    
    - Em **Associação**, na seção **criadores** , adicione ou remova usuários e outras entidades de segurança do Active Directory associadas aos criadores para a categoria. Um criador é um usuário que tem permissões de criar salas de chat e atribuir gerentes e membros de sala de chat.
    
13. Clique em **Confirmar**.
    
## <a name="see-also"></a>Confira também

Para obter detalhes sobre recursos e recursos do servidor de chat persistente, consulte [planejar o servidor de chat persistente no Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [implantar o servidor de chat persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [gerenciar o servidor de chat persistente no Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

