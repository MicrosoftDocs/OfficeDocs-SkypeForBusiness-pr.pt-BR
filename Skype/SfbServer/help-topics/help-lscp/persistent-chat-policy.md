---
title: Política de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Você pode usar a página Política de Chat Persistente do grupo Chat Persistente para gerenciar políticas no nível global, de pool, de site ou de usuário, inclusive para configurar a política global padrão e criar uma ou mais políticas de usuário e de site para sua implantação. Se o servidor de chat persistente estiver habilitado para um usuário por política, o ambiente do servidor de chat persistente aparecerá no cliente.
ms.openlocfilehash: 957956ce8537dd9f3ce08dd0919c7392a0c20810
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686184"
---
# <a name="persistent-chat-policy"></a>Política de Chat Persistente
 
Você pode usar a página **Política de Chat Persistente** do grupo **Chat Persistente** para gerenciar políticas no nível global, de pool, de site ou de usuário, inclusive para configurar a política global padrão e criar uma ou mais políticas de usuário e de site para sua implantação. Se o servidor de chat persistente estiver habilitado para um usuário por política, o ambiente do servidor de chat persistente aparecerá no cliente.
  
A política global é criada automaticamente quando você implanta um servidor de chat persistente, e pode ser configurada, mas não excluída. Como a política global se aplica a todos os usuários, ela não precisa ser definida por usuário.
  
Você pode criar e configurar várias políticas de site e de usuário, juntamente com a política global, habilitar usuários para o servidor de chat persistente. As políticas de servidor de chat persistente do pool e do site substituem a política global de servidor de chat persistente, mas somente para os usuários desse site. As políticas de usuário substituem as políticas globais, de pool e de site para os usuários aos quais são atribuídas.
  
> [!NOTE]
> Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar suporte a servidor de chat persistente à topologia e, em seguida, publicar a topologia. Para obter detalhes, consulte [Adicionar servidor de chat persistente à sua topologia do Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md). 
  
## <a name="tasks-that-you-can-perform"></a>Tarefas que você pode executar

Você pode executar as seguintes tarefas na página **Política de Chat Persistente**: habilitar e gerenciar a política de Servidor de Chat Persistente.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Para configurar a política global para chats persistentes

1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.
    
3. No painel de controle do Skype for Business Server, clique em **chat persistente**e, em seguida, clique em **política de chat persistente**.
    
4. Clique em **Global** na lista de políticas, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.
    
5. Em **Editar Política de Chat Persistent - Global**, siga este procedimento:
    
   - Em **Nome**, especifique um novo nome para a política global, se não desejar usar o padrão Global.
    
   - Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política global para _centralSiteName_).
    
   - Para controlar o chat persistente para todos os sites e usuários não controlados especificamente por meio de uma política de site ou política de usuário, marque ou desmarque a caixa de seleção **habilitar chat persistente** .
    
6. Clique em **Confirmar**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Para criar uma política de chat persistente para um site

Para cada site que você implantou, é possível criar uma política de chat persistente específica do site.
  
A configuração da política de site substitui a política global, mas somente para o site específico coberto pela política de site.
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.
    
4. Clique em **Novo** e, em seguida, clique em **Política de site**.
    
5. Em **Selecionar um Site**, clique no site ao qual a política deverá ser aplicada.
    
6. Em **Nova Política de Chat Persistente**, siga este procedimento:
    
   - Em **Nome**, especifique um nome para a nova política de site (por exemplo, Redmond).
    
   - Em **Descrição**, forneça detalhes sobre a política de site (por exemplo, política de sala de chat de Redmond).
    
   - Para controlar o Chat Persistente para todos os sites não controlados especificamente por meio de uma política de site, marque ou desmarque a caixa de seleção **Habilitar Chat Persistente**.
    
7. Clique em **Confirmar**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>Para criar uma política de usuário para chat persistente

No painel de controle do Skype for Business Server, você define as políticas de usuário que podem ser atribuídas aos usuários nos **usuários**.
  
A política de usuário substitui as políticas globais e de site, mas apenas para os usuários específicos aos quais ela é atribuída.
  
1. Em uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.
    
4. Clique em **Novo** e em **Política de usuário**.
    
5. Em **Nova Política de Chat Persistente**, siga este procedimento:
    
   - Em **Nome**, especifique um nome para a nova política de usuário.
    
   - Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política de chat persistente para um usuário específico).
    
   - Para controlar o chat persistente para todos os usuários que não são controlados especificamente por meio de uma política de usuário, marque ou desmarque a caixa de seleção **habilitar chat persistente** .
    
6. Clique em **Confirmar**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Para aplicar uma política de usuário de chat persistente a uma conta de usuário

Se um usuário tiver sido habilitado para o Skype for Business Server, você poderá aplicar políticas adequadas a usuários específicos para habilitá-las ou desabilitá-las para um servidor de chat persistente.
  
Use o procedimento deste tópico para aplicar uma política de usuário de chat persistente criada anteriormente a uma ou mais contas de usuário ou grupos de usuários.
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.
    
3. Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.
    
4. Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.
    
5. Em **Editar usuário do Lync Server** na **política de chat persistente**, selecione a política de usuário de chat persistente que você deseja aplicar.
    
    > [!NOTE]
    > As ** \<configurações\> automáticas** aplicam a política em vigor padrão. Essas configurações são aplicadas automaticamente pelo servidor.
  
6. Clique em **Confirmar**.
    

