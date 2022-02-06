---
title: Política de Chat Persistente
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: 'Você pode usar a página Política de Chat Persistente do grupo de Chat Persistente para gerenciar políticas em nível global, pool, site ou usuário, incluindo a configuração da política global padrão e a criação de uma ou mais políticas de usuário e site adicionais para sua implantação. Se o Servidor de Chat Persistente estiver habilitado para um usuário por política, o ambiente do Servidor de Chat Persistente aparecerá em seu cliente.'
---

# <a name="persistent-chat-policy"></a>Política de Chat Persistente
 
Você pode usar a página Política de **Chat** Persistente do grupo de **Chat** Persistente para gerenciar políticas em nível global, pool, site ou usuário, incluindo a configuração da política global padrão e a criação de uma ou mais políticas de usuário e site adicionais para sua implantação. Se o Servidor de Chat Persistente estiver habilitado para um usuário por política, o ambiente do Servidor de Chat Persistente aparecerá em seu cliente.
  
A política global é criada automaticamente quando você implanta o Servidor de Chat Persistente e pode ser configurada, mas não excluída. Como a política global se aplica a todos os usuários, ela não precisa ser definida por usuário.
  
Você pode criar e configurar várias políticas de site e usuário que, juntamente com a política global, habilitam os usuários para o Servidor de Chat Persistente. As políticas do Servidor de Chat Persistente do Pool e do site substituem a política global do Servidor de Chat Persistente, mas somente para usuários desse site. As políticas de usuário substituem as políticas global, de pool e de site para os usuários aos quais a política de usuário é atribuída.
  
> [!NOTE]
> Para configurar e usar o Servidor de Chat Persistente, primeiro você deve usar o Construtor de Topologias para adicionar suporte ao Servidor de Chat Persistente à topologia e, em seguida, publicar a topologia. Para obter detalhes, [consulte Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md). 
  
## <a name="tasks-that-you-can-perform"></a>Tarefas que podem ser executadas

Você pode executar as seguintes tarefas na página Política de **Chat** Persistente: habilitar a política do Servidor de Chat Persistente; gerenciar a política do Servidor de Chat Persistente.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Para configurar a Política Global para Chat Persistente

1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar**, selecione o painel de controle Skype for Business Server ou abra uma janela do navegador e insira a URL do administrador.
    
3. Em Skype for Business Server Painel de Controle, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.
    
4. Clique em **Global** na lista de políticas, clique em **Editar** e clique em **Mostrar detalhes**.
    
5. Em **Editar Política de Chat Persistente - Global**, faça o seguinte:
    
   - Em **Nome**, especifique um novo nome para a política global, se você não quiser usar o padrão de Global.
    
   - Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política global  _para centralSiteName_).
    
   - Para controlar o Chat Persistente para todos os sites e usuários não controlados especificamente por meio de uma política de site ou de uma política de usuário, selecione ou desempure a caixa de seleção **Habilitar Chat Persistente** .
    
6. Clique em **Confirmar**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Para criar uma política de Chat Persistente para um site

Para cada site implantado, você pode criar uma política de Chat Persistente específica do site.
  
A configuração da política de local substitui a política global, mas apenas para o local específico e coberto por essa política.
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar**, selecione o painel de controle Skype for Business Server ou abra uma janela do navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Política de Chat Persistente**.
    
4. Clique em **Novo** e, em seguida, em **Política de site**.
    
5. Em **Selecionar um Site**, clique no site para o qual a política será aplicada.
    
6. Em **Nova Política de Chat Persistente**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para a nova política de site (por exemplo, Redmond).
    
   - Em **Descrição**, forneça detalhes sobre o que é a política de site (por exemplo, política de sala de chat para Redmond).
    
   - Para controlar o Chat Persistente para todos os sites não controlados especificamente por meio de uma política de site, marque ou desmarque a caixa de seleção **Habilitar Chat Persistente**.
    
7. Clique em **Confirmar**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>Para criar uma política de usuário para Chat Persistente

No painel Skype for Business Server controle, você define políticas de usuário que podem ser atribuídas aos usuários em **Usuários**.
  
A política de usuário substitui a política global e as políticas de site, mas somente para os usuários específicos atribuídos à política de usuário.
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar**, selecione o painel de controle Skype for Business Server ou abra uma janela do navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Política de Chat Persistente**.
    
4. Clique em **Novo** e, em seguida, em **Política de usuário**.
    
5. Em **Nova Política de Chat Persistente**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para a nova política de usuário.
    
   - Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política de Chat Persistente para usuário específico).
    
   - Para controlar o Chat Persistente para todos os usuários que não são especificamente controlados por meio de uma política de usuário, selecione ou desempure a caixa de seleção **Habilitar Chat Persistente** .
    
6. Clique em **Confirmar**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Para aplicar uma política de usuário de Chat Persistente a uma conta de usuário

Se um usuário tiver sido habilitado para Skype for Business Server, você poderá aplicar políticas apropriadas a usuários específicos para habilita-los ou desabilitá-los para o Servidor de Chat Persistente.
  
Use o procedimento neste tópico para aplicar uma política de usuário de Chat Persistente criada anteriormente a uma ou mais contas de usuário ou grupos de usuários.
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar**, selecione o painel de controle Skype for Business Server ou abra uma janela do navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.
    
4. Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.
    
5. Em **Editar Usuário do Lync Server em** **Política de Chat Persistente**, selecione a política de usuário de Chat Persistente que você deseja aplicar.
    
    > [!NOTE]
    > As **\<Automatic\>** configurações aplicam a política efetiva padrão. Essas configurações são aplicadas automaticamente pelo servidor.
  
6. Clique em **Confirmar**.
    

