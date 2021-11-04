---
title: Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumo: leia este tópico para saber como criar políticas de usuário iniciais para o Servidor de Chat Persistente no Skype for Business Server 2015. As políticas de usuário de Chat Persistente determinam se os usuários têm ou não permissão de acesso às salas de chat.'
ms.openlocfilehash: c77782ed1aeef1b7696ab7b00b5bbfcc9c00f421
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778891"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como criar políticas de usuário iniciais para o Servidor de Chat Persistente no Skype for Business Server 2015. As políticas de usuário de Chat Persistente determinam se os usuários têm ou não permissão de acesso às salas de chat.
  
Você pode gerenciar políticas de usuário do Servidor de Chat Persistente nos seguintes níveis: global, site ou usuário. Inicialmente, você configura a política global para habilitar as configurações de Chat Persistente para todos os usuários em sua implantação e, em seguida, criar políticas de site e usuário adicionais para controlar se o Chat Persistente está ativado para usuários e sites específicos.
  
Este tópico contém as seguintes seções:
  
- Configurar a política global
    
- Criar uma política de site
    
- Criar uma política de usuário
    
- Aplicar uma política a um usuário ou grupo de usuários
    
> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015.

## <a name="configure-the-global-policy"></a>Configurar a política global

Para configurar a política global:
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar,** selecione o painel de controle Skype for Business Server ou abra uma janela do navegador e insira a URL do administrador.
    
3. Em Skype for Business Server Painel de Controle, clique em **Chat Persistente** e, em seguida, clique em Política de **Chat Persistente.**
    
4. Clique em **Global** na lista de políticas, clique em **Editar** e clique em **Mostrar detalhes**.
    
5. Em **Editar Política de Chat Persistente - Global**, faça o seguinte: 
    
   - Em **Nome**, especifique um novo nome para a política global, se você não quiser usar o padrão de Global.
    
   - Em **Descrição,** forneça detalhes sobre o que é a política de usuário (por exemplo, política global  _para centralSiteName_).
    
   - Para controlar o Chat Persistente para todos os sites e usuários não controlados especificamente por meio de uma política de site ou de uma política de usuário, selecione ou desempure a caixa de seleção **Habilitar Chat Persistente.**
    
6. Clique em **Confirmar**.
    
## <a name="create-a-site-policy"></a>Criar uma política de site

Para cada site implantado, você pode criar uma política de Chat Persistente específica do site. A configuração da política de local substitui a política global, mas apenas para o local específico e coberto por essa política. Para criar uma política de site:
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar,** selecione o painel de controle Skype for Business Server ou abra uma janela do navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Política de Chat Persistente**.
    
4. Clique em **Novo** e, em seguida, em **Política de site**.
    
5. Em **Selecionar um Site**, clique no site para o qual a política será aplicada.
    
6. Em **Nova Política de Chat Persistente**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para a nova política de site (por exemplo, Redmond).
    
   - Em **Descrição**, forneça detalhes sobre o que é a política de site (por exemplo, política de sala de chat para Redmond).
    
   - Para controlar o Chat Persistente para todos os sites não controlados especificamente por meio de uma política de site, marque ou desmarque a caixa de seleção **Habilitar Chat Persistente**.
    
7. Clique em **Confirmar**.
    
## <a name="create-a-user-policy"></a>Criar uma política de usuário

Você pode criar políticas específicas do usuário que substituem a política global e quaisquer políticas de site às quais o usuário pertence. Para criar uma política de usuário:
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar,** selecione o painel de controle Skype for Business Server ou abra uma janela do navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Política de Chat Persistente**.
    
4. Clique em **Novo** e, em seguida, em **Política de usuário**.
    
5. Em **Nova Política de Chat Persistente**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para a nova política de usuário.
    
   - Em **Descrição,** forneça detalhes sobre o que é a política de usuário (por exemplo, política de Chat Persistente para usuário específico).
    
   - Para controlar o Chat Persistente para todos os usuários que não são especificamente controlados por meio de uma política de usuário, selecione ou desempure a caixa de seleção **Habilitar Chat Persistente.**
    
6. Clique em **Confirmar**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Aplicar uma política a uma conta de usuário

Depois de criar políticas, você pode aplicá-las a uma conta de usuário da seguinte forma:
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar,** selecione o painel de controle Skype for Business Server ou abra uma janela do navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.
    
4. Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.
    
5. Em **Editar Skype for Business Server Usuário em** Política de Chat **Persistente,** selecione a política de usuário de Chat Persistente que você deseja aplicar.
    
    > [!NOTE]
    > As **\<Automatic\>** configurações aplicam a política efetiva padrão. Essas configurações são aplicadas automaticamente pelo servidor.
  
6. Clique em **Confirmar**.
    

