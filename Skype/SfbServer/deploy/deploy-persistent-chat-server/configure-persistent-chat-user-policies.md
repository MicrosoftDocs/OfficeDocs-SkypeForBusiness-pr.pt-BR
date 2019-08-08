---
title: Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumo: Leia este tópico para saber como criar políticas iniciais de usuário para o servidor de chat persistente no Skype for Business Server 2015. Políticas de usuário de chat persistente determinam se os usuários podem ou não acesso a salas de chat.'
ms.openlocfilehash: 83d6b49372f695be1a4db516eda6c7be357beed3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239752"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como criar políticas iniciais de usuário para o servidor de chat persistente no Skype for Business Server 2015. Políticas de usuário de chat persistente determinam se os usuários podem ou não acesso a salas de chat.
  
Você pode gerenciar políticas de usuário do servidor de chat persistente nos seguintes níveis: global, site ou usuário. Inicialmente, você configura a política global para habilitar configurações de Chat Persistente para todos os usuários na sua implantação, e então cria políticas adicionais de site e usuário para controlar se o Chat Persistente está ativado para sites e usuários específicos.
  
Este tópico inclui as seguintes seções:
  
- Configurar a política global
    
- Criar uma política de site
    
- Criar uma política de usuário
    
- Aplicar uma política a um usuário ou grupo de usuários
    
> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.

## <a name="configure-the-global-policy"></a>Configurar a política global

Para configurar a política global:
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.
    
3. No painel de controle do Skype for Business Server, clique em **chat persistente**e, em seguida, clique em **política de chat persistente**.
    
4. Clique em **Global** na lista de políticas, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.
    
5. Em **Editar Política de Chat Persistent - Global**, siga este procedimento: 
    
   - Em **Nome**, especifique um novo nome para a política global, se não desejar usar o padrão Global.
    
   - Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política global para _centralSiteName_).
    
   - Para controlar o chat persistente para todos os sites e usuários não controlados especificamente por meio de uma política de site ou política de usuário, marque ou desmarque a caixa de seleção **habilitar chat persistente** .
    
6. Clique em **Confirmar**.
    
## <a name="create-a-site-policy"></a>Criar uma política de site

Para cada site implantado, é possível criar uma política de Chat Persistente específica do site. A configuração no site substitui a política global, mas somente para o site específico coberto pela política de site. Para criar uma política de site:
  
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
    
## <a name="create-a-user-policy"></a>Criar uma política de usuário

Você pode criar políticas específicas de usuário que substituem a política global e quaisquer políticas de site ao qual o usuário pertence. Para criar uma política de usuário:
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.
    
4. Clique em **Novo** e em **Política de usuário**.
    
5. Em **Nova Política de Chat Persistente**, siga este procedimento:
    
   - Em **Nome**, especifique um nome para a nova política de usuário.
    
   - Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política de chat persistente para um usuário específico).
    
   - Para controlar o chat persistente para todos os usuários que não são controlados especificamente por meio de uma política de usuário, marque ou desmarque a caixa de seleção **habilitar chat persistente** .
    
6. Clique em **Confirmar**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Aplicar uma política a uma conta de usuário

Após criar as políticas, você pode aplicá-las a uma conta de usuário da seguinte forma:
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.
    
3. Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.
    
4. Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.
    
5. Em **Editar o usuário do Skype for Business Server** na **política de chat persistente**, selecione a política de usuário de chat persistente que você deseja aplicar.
    
    > [!NOTE]
    > As ** \<configurações\> automáticas** aplicam a política em vigor padrão. Essas configurações são aplicadas automaticamente pelo servidor.
  
6. Clique em **Confirmar**.
    

