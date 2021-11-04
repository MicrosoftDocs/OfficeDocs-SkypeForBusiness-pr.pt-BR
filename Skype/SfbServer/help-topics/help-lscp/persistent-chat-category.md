---
title: Categoria de Chat Persistente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: Você pode usar a seção Categoria da página Chat Persistente para configurar categorias. Uma categoria de sala de Chat Persistente é uma estrutura lógica para organizar salas de chat. Uma categoria define um conjunto padrão de listas de controle de acesso (ACLs) para controle dos usuários e dos grupos de usuários que podem criar ou ingressar em salas de chat. É possível usar as categorias para aplicar paredes éticas entre diferentes subdivisões dentro de suas organizações.
ms.openlocfilehash: 57e97faa0dd7c3cb80d75f9a06a8f5d2602ba162
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760839"
---
# <a name="persistent-chat-category"></a>Categoria de Chat Persistente
 
Você pode usar a **seção Categoria** da página **Chat Persistente** para configurar categorias. Uma categoria de sala de Chat Persistente é uma estrutura lógica para organizar salas de chat. Uma categoria define um conjunto padrão de listas de controle de acesso (ACLs) para controle dos usuários e dos grupos de usuários que podem criar ou ingressar em salas de chat. É possível usar as categorias para aplicar paredes éticas entre diferentes subdivisões dentro de suas organizações.
  
As categorias de sala de chat podem conter salas de chat, mas nenhuma outra categoria. Cada categoria descreve seu conteúdo com metadados, como _Nome_ e _Descrição._ Além disso, a categoria tem propriedades que podem ser definidas para controlar o comportamento das salas de chat pertencentes a ela, como se as salas de chat permitem _Convites_ ou _Carregamentos_ de Arquivo ou contêm _Histórico de Chat._
  
Para criar uma nova categoria, consulte [Manage categories in Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/categories.md). Se você for um Administrador de Chat Persistente, poderá criar categorias usando o painel de controle ou Windows PowerShell cmdlets.
  
## <a name="tasks-that-you-can-perform"></a>Tarefas que podem ser executadas

É possível executar as seguintes tarefas na página **Categoria**:
  
- Criar ou editar uma nova categoria
    
- Mover uma sala de chat de uma categoria para outra
    
- Excluir uma sala de chat ou categoria
    
## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar as categorias para salas de chat

1. A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.
    
2. No menu **Iniciar,** selecione o painel de controle Skype for Business Server ou abra uma janela do navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Categoria**.
    
    Para várias implantações de pool do Servidor de Chat Persistente, selecione o pool apropriado na listada.
    
4. Na página **Categoria**, clique em **Novo** ou **Editar**.
    
5. Em **Selecionar um Serviço,** selecione o serviço correspondente ao pool do Servidor de Chat Persistente no qual a categoria precisa ser criada. O serviço é o pool de Servidor de Chat Persistente que o Chat Persistente (cliente) usa para identificar a qual pool a categoria pertence. Uma categoria pode pertencer a apenas um pool de Servidor de Chat Persistente e não pode ser movida para outro ou compartilhada com outro pool.
    
6. Em **Nova Categoria**, faça o seguinte:
    
7. Em **Nome**, especifique um nome para a nova categoria de sala.
    
8. Em **Descrição**, forneça uma descrição detalhada da categoria de sala (por exemplo, uma categoria de sala para Contoso).
    
9. Para controlar se os convites podem ser habilitados para salas de chat que pertencem a essa categoria, marque ou desmarque a caixa de seleção **Habilitar convites**. Se for marcada, as salas nessa categoria poderão ter os convites ativados ou desativados; se for desmarcada, as salas nessa categoria não terão permissão para enviar convites. Se uma sala tiver convites, quando um novo membro for adicionado a uma sala, ele receberá uma notificação da nova sala em seu cliente de Chat Persistente.
    
10. Para controlar os carregamentos de arquivo nas salas de chat que pertencem a essa categoria, marque ou desmarque a caixa de seleção **Habilitar carregamento de arquivo**. Se for marcada, as salas dessa categoria poderão habilitar ou desabilitar os carregamentos de arquivo; se for desmarcada, as salas dessa categoria não terão permissão para carregamentos de arquivo.
    
     > [!IMPORTANT]
     > Essa configuração é imposta no servidor porque aplicativos personalizados ou clientes anteriores de Chat de Grupo que usam o Office Communications Server 2007 R2 Group Chat Server ou o Lync Server 2010, o Chat de Grupo pode postar arquivos em uma sala. O cliente do Lync 2013 não tem capacidade de carregamento/download de arquivos, portanto, se você tiver uma implantação pura do Lync 2013 ou cliente do Lync 2013, não é possível postar arquivos em uma sala de chat do Servidor de Chat Persistente. 
  
11. Para controlar o histórico de chat, selecione ou desempure a caixa de seleção **Habilitar histórico de** chat. Se for marcada, as salas de chats se tornarão persistentes; caso contrário, as mensagens de chat não serão persistentes. Se a conformidade for habilitada, salas de chats serão salvas em conformidade, mas os usuários não poderão acessar mensagens mais antigas. Essa opção pode ser usada para salas designadas para colaborações ad hoc em tempo real que não precisam manter o histórico de chat.
    
12. Em **Editar Categoria**, faça o seguinte:
    
    - Em Associação , na seção **Membros** Permitidos, adicione ou remova usuários e outras entidades de Serviços de Domínio do Active Directory (usuários, grupos de distribuição, unidades organizacionais e assim por diante) que têm permissão para serem adicionados como membros de salas de chat pertencentes à categoria. As entidades permitidas por uma categoria podem pesquisar por salas na categoria (a menos que uma sala esteja oculta, caso o qual apenas membros da sala podem pesquisar por ela no diretório).
    
    - Em **Associação**, na seção **Membros negados,** adicione ou remova usuários e outras entidades do Active Directory associadas aos membros que estão sendo negados da sala.
    
    - Em **Associação**, na seção **Criadores,** adicione ou remova usuários e outras entidades do Active Directory associadas aos criadores da categoria. Um criador é um usuário com permissões para criar salas de chat e atribuir gerentes e membros de sala de chat.
    
13. Clique em **Confirmar**.
    
## <a name="see-also"></a>Confira também

Para obter detalhes sobre recursos e recursos do Servidor de Chat Persistente, consulte [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), Deploy Persistent Chat Server in Skype for Business Server [2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

