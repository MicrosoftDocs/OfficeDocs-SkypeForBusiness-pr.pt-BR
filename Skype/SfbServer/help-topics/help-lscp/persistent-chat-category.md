---
title: Categoria de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: É possível usar a seção Categoria da página Chat Persistente para configurar as categorias. Uma categoria de sala de bate-papo persistente é uma estrutura lógica para organizar salas de chat. Uma categoria define um conjunto padrão de listas de controle de acesso (ACLs) para controle dos usuários e dos grupos de usuários que podem criar ou ingressar em salas de chat. É possível usar as categorias para aplicar paredes éticas entre diferentes subdivisões dentro de suas organizações.
ms.openlocfilehash: dc1ce00a65186da02979afb67900dce7f0943a19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910950"
---
# <a name="persistent-chat-category"></a>Categoria de Chat Persistente
 
É possível usar a seção **Categoria** da página **Chat Persistente** para configurar as categorias. Uma categoria de sala de bate-papo persistente é uma estrutura lógica para organizar salas de chat. Uma categoria define um conjunto padrão de listas de controle de acesso (ACLs) para controle dos usuários e dos grupos de usuários que podem criar ou ingressar em salas de chat. É possível usar as categorias para aplicar paredes éticas entre diferentes subdivisões dentro de suas organizações.
  
As categorias de sala de chat podem conter salas de chat, mas nenhuma outra categoria. Cada categoria descreve seu conteúdo com metadados, como _nome_ e _Descrição_. Além disso, a categoria tem propriedades que podem ser definidas para controlar o comportamento da sala de chat que pertencem a ele, por exemplo, se as salas de bate-papo permitir _convites_ ou _Carregamentos de arquivo_ou contêm o _Histórico de Chat_.
  
Para criar uma nova categoria, consulte [Gerenciar categorias no servidor de Chat persistente no Skype para Business Server 2015](../../manage/persistent-chat/categories.md). Se você for um administrador de Chat persistente, você pode criar categorias usando o painel de controle ou os cmdlets do Windows PowerShell.
  
## <a name="tasks-that-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Categoria**:
  
- Criar ou editar uma nova categoria
    
- Mover uma sala de chat de uma categoria a outra
    
- Excluir sala de chat ou categoria
    
## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar categorias salas de bate-papo

1. A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.
    
2. No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Categoria**.
    
    Para várias implantações de pool de servidor de Chat persistente, selecione o pool apropriado na lista suspensa.
    
4. Na página **Categoria**, clique em **Novo** ou **Editar**.
    
5. Em **Selecionar um serviço**, selecione o serviço correspondente para o pool de servidor de Chat persistente no qual a categoria precisa ser criado. O serviço é o servidor de Chat persistente pool (cliente) de Chat persistente usado para identificar qual categoria de pool pertence. Uma categoria pode pertencer a apenas um pool do servidor de Chat persistente e não pode ser movida para outro ou compartilhada com outro pool.
    
6. Em **Nova categoria**, faça o seguinte:
    
7. Em  **Nome**, especifique um nome para a nova categoria de sala.
    
8. Em  **Descrição**, forneça uma descrição detalhada para a categoria da sala (por exemplo, uma categoria de sala para Contoso).
    
9. Para controlar se os convites podem ser ativados por salas de chat que pertencem a tal categoria, selecione ou limpe a caixa de marcação **Habilitar convites**. Se marcado, as salas nesta categoria poderão ter convites ativados ou desativados; em caso de não marcado, as salas nessa categoria não podem ter convite. Se uma sala tiver convites ativado, quando um novo membro é adicionado a uma sala, ele obtém uma notificação da nova sala em seu cliente de Chat persistente.
    
10. Para controlar o envio de arquivo nas salas de chat pertencentes a esta categoria, selecione ou desmarque a caixa de seleção **Habilitar carregamento de arquivo**. Se estiver marcada, as salas desta categoria podem habilitar ou desabilitar carregamentos de arquivos; se estiver desmarcada, as salas nesta categoria não podem ter arquivos carregados.
    
     > [!IMPORTANT]
     > Esta configuração é aplicada no servidor, pois aplicativos personalizados ou antigos clientes de Chat de grupo que usam o servidor Office Communications Server 2007 R2 grupo bate-papo ou no Lync Server 2010, Chat de grupo podem postar arquivos em uma sala. O cliente do Lync 2013 não tem o recurso de upload/download de arquivos, portanto, se você tiver uma implantação do Lync 2013 pura ou o cliente do Lync 2013, não é possível postar arquivos em uma sala de chat Persistent Chat Server. 
  
11. Para controlar o histórico de chat, marque ou desmarque a caixa de seleção **Habilitar o histórico de chat** . Se marcada, as salas de chat se tornam persistentes; caso contrário, as mensagens de chat não são persistentes. Se a conformidade estiver habilitada, as salas de chat serão salvas em conformidade, mas os usuários não poderão acessar mensagens antigas. Essa opção pode ser usada para salas designadas para colaboração em tempo real e ad hoc que não necessitem de histórico de chat para ser mantido.
    
12. Em  **Editar categoria**, faça o seguinte:
    
    - Em **associação**, na seção **membros permitidos** , adicione ou remova usuários e outras entidades do Active Directory Domain Services (usuários, grupos de distribuição, unidades organizacionais e assim por diante) que são permitidas a serem adicionados como membros de salas de bate-papo que pertencem à categoria. As entidades permitidas por uma categoria podem pesquisar por salas na categoria (a menos que uma sala esteja oculta, caso o qual apenas membros da sala podem pesquisar por ela no diretório).
    
    - Em **associação**, na seção **membros negados** , adicione ou remova usuários e outras entidades do Active Directory associadas aos membros sendo negados da sala.
    
    - Em **associação**, na seção **criadores** , adicione ou remova usuários e outras entidades do Active Directory associadas criadores para a categoria. Um criador é um usuário que tem permissões de criar salas de chat e atribuir gerentes e membros de sala de chat.
    
13. Clique em **Confirmar**.
    
## <a name="see-also"></a>Confira também

Para obter detalhes sobre os recursos de servidor de Chat persistente e recursos, consulte [Plan for Persistent Chat Server in Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server na Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [Gerenciar o servidor de Chat persistente no Skype para Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

