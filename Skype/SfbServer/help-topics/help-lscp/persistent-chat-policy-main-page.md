---
title: Página Principal da Política de Chat Persistente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: Você pode usar a página política de Chat persistente do grupo de Chat persistente para gerenciar diretivas em um nível global, de inclusive configurar a política global de padrão e criando um ou mais sites e usuário diretivas adicionais para sua implantação de pool, site ou usuário. Se um usuário estiver habilitado para o servidor de Chat persistente por diretiva, o ambiente de servidor de Chat persistente aparece em seu cliente.
ms.openlocfilehash: 14d600c558a7a72887aa7ff3e349857115e8a792
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-policy-main-page"></a>Página Principal da Política de Chat Persistente
 
Você pode usar a página **Política de Chat Persistente** do grupo **Chat Persistente** para gerenciar políticas no nível global, de pool ou de usuário, inclusive para configurar a política global padrão e criar uma ou mais políticas de usuário e de site para sua implantação. Se um usuário estiver habilitado para o servidor de Chat persistente por diretiva, o ambiente de servidor de Chat persistente aparece em seu cliente.
  
> [!NOTE]
> Na topologia, as políticas de site do servidor de Chat persistente se aplicam globalmente, por pool do usuário, ou por site do usuário ou por usuário. 
  
A política global é criada automaticamente quando você implantar o servidor de Chat persistente, e ele pode ser configurado, mas não excluído. Porque a política global se aplica a todos os usuários, ele não tem que ser definida por usuário.
  
Você pode criar e configurar várias políticas de site e de usuário que, juntamente com a política global, habilitar usuários para o servidor de Chat persistente. Políticas de Persistent Chat Server pool e site substituem a política de servidor de Chat persistente global, mas somente para usuários do site. As políticas de usuário substituem as políticas globais, de pool e de site para os usuários aos quais são atribuídas.
  
> [!NOTE]
> Para configurar e usar o servidor de Chat persistente, você deve primeiro usar o construtor de topologias para adicionar suporte ao servidor de Chat persistente à topologia e, em seguida, publique a topologia. Para obter detalhes, consulte [Adicionar servidor de Chat persistente para seu Skype para a topologia de negócios Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md). 
  
## <a name="tasks-that-you-can-perform"></a>Tarefas que você pode executar

Você pode executar as seguintes tarefas na página **Política de Chat Persistente**: habilitar e gerenciar a política de Servidor de Chat Persistente.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Para configurar a política Global para o Chat persistente

1. Em uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.
    
3. No painel de controle do servidor de negócios do Skype, clique em **Chat persistente**e clique em **Política de Chat persistente**.
    
4. Clique em **Global** na lista de políticas, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.
    
5. Em **Editar Política de Chat Persistent - Global**, siga este procedimento:
    
  - Em **Nome**, especifique um novo nome para a política global, se não desejar usar o padrão Global.
    
  - Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política Global para _centralSiteName_).
    
  - Para controlar o Chat persistente para todos os sites e usuários não especificamente controlados através de uma política de site ou usuário, marque ou desmarque a caixa de seleção **Habilitar Chat persistente** .
    
6. Clique em **Confirmar**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Para criar uma política de Chat persistente para um site

Para cada site implantado, você pode criar uma política de Chat persistente.
  
A configuração da política de site substitui a política global, mas somente para o site específico coberto pela política de site.
  
1. Em uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.
    
4. Clique em **Novo** e, em seguida, clique em **Política de site**.
    
5. Em **Selecionar um Site**, clique no site ao qual a política deverá ser aplicada.
    
6. Em **Nova Política de Chat Persistente**, siga este procedimento:
    
  - Em **Nome**, especifique um nome para a nova política de site (por exemplo, Redmond).
    
  - Em **Descrição**, forneça detalhes sobre a política de site (por exemplo, política de sala de chat de Redmond).
    
  - Para controlar o Chat Persistente para todos os sites não controlados especificamente por meio de uma política de site, marque ou desmarque a caixa de seleção **Habilitar Chat Persistente**.
    
7. Clique em **Confirmar**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>Para criar uma política de usuário para o Chat persistente

No Skype para painel de controle do Business Server, você define as políticas de usuário que podem ser atribuídas aos usuários em **usuários**.
  
A política de usuário substitui as políticas globais e de site, mas apenas para os usuários específicos aos quais ela é atribuída.
  
1. Em uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.
    
4. Clique em **Novo** e em **Política de usuário**.
    
5. Em **Nova Política de Chat Persistente**, siga este procedimento:
    
  - Em **Nome**, especifique um nome para a nova política de usuário.
    
  - Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política de Chat persistente para usuário específico).
    
  - Para controlar o Chat persistente para todos os usuários que não são especificamente controlados através de uma política de usuário, marque ou desmarque a caixa de seleção **Habilitar Chat persistente** .
    
6. Clique em **Confirmar**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Para aplicar uma política de usuário de Chat persistente para uma conta de usuário

Se um usuário tiver sido habilitado para Skype para a empresa, você pode aplicar as políticas adequadas a usuários específicos para habilitar ou desabilitá-las para o servidor de Chat persistente.
  
Use o procedimento neste tópico para aplicar uma política de usuário de Chat persistente criada anteriormente para uma ou mais contas de usuário ou grupos de usuários.
  
1. Em uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.
    
4. Na tabela que lista os resultados da pesquisa, clique na conta de usuário, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.
    
5. Em **Editar usuário do Lync Server** , em **política de Chat persistente**, selecione a política de usuário de Chat persistente que você deseja aplicar.
    
    > [!NOTE]
    > O ** \<automática\> ** configurações se aplicam a diretiva padrão de efetiva. Essas configurações são aplicadas automaticamente pelo servidor.
  
6. Clique em **Confirmar**.
    

