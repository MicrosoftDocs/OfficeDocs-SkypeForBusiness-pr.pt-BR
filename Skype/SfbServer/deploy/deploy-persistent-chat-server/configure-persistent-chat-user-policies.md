---
title: Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumo: Leia este tópico para saber como criar políticas de usuário iniciais para o Servidor de Chat Persistente no Skype for Business Server 2015. As políticas de usuário de Chat Persistente determinam se os usuários têm permissão ou não para acessar salas de chat.'
ms.openlocfilehash: 531146a55b0282db191f503ef39e9be9e4d5f879
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802111"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como criar políticas iniciais de usuário para o Servidor de Chat Persistente no Skype for Business Server 2015. As políticas de usuário de Chat Persistente determinam se os usuários têm permissão ou não para acessar salas de chat.
  
Você pode gerenciar as políticas de usuário do Servidor de Chat Persistente nos seguintes níveis: global, site ou usuário. Inicialmente, você configura a política global para habilitar as configurações de Chat Persistente para todos os usuários em sua implantação e, em seguida, cria políticas adicionais de usuário e site para controlar se o Chat Persistente está ativado para usuários e sites específicos.
  
Este tópico contém as seguintes seções:
  
- Configurar a política global
    
- Criar uma política de site
    
- Criar uma política de usuário
    
- Aplicar uma política a um usuário ou grupo de usuários
    
> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here) Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.

## <a name="configure-the-global-policy"></a>Configurar a política global

Para configurar a política global:
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.
    
3. No Painel de Controle do Skype for Business Server, clique em **Chat Persistente** e em Política de **Chat Persistente.**
    
4. Clique em **Global** na lista de políticas, clique em **Editar** e clique em **Mostrar detalhes**.
    
5. Em **Editar Política de Chat Persistente - Global**, faça o seguinte: 
    
   - Em **Nome**, especifique um novo nome para a política global, se você não quiser usar o padrão de Global.
    
   - Em **Descrição,** forneça detalhes sobre a política de usuário (por exemplo, política global  _para centralSiteName_).
    
   - Para controlar o Chat Persistente para todos os sites e usuários não controlados especificamente por meio de uma política de site ou de usuário, marque ou des marque a caixa de seleção Habilitar **Chat** Persistente.
    
6. Clique em **Confirmar**.
    
## <a name="create-a-site-policy"></a>Criar uma política de site

Para cada site implantado, você pode criar uma política de Chat Persistente específica do site. A configuração da política de local substitui a política global, mas apenas para o local específico e coberto por essa política. Para criar uma política de site:
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.
    
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
    
2. No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Política de Chat Persistente**.
    
4. Clique em **Novo** e, em seguida, em **Política de usuário**.
    
5. Em **Nova Política de Chat Persistente**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para a nova política de usuário.
    
   - Em **Descrição,** forneça detalhes sobre a política de usuário (por exemplo, política de Chat Persistente para usuário específico).
    
   - Para controlar o Chat Persistente para todos os usuários que não são controlados especificamente por meio de uma política de usuário, marque ou des limpe a caixa de seleção **Habilitar Chat** Persistente.
    
6. Clique em **Confirmar**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Aplicar uma política a uma conta de usuário

Depois de criar políticas, você pode aplicá-las a uma conta de usuário da seguinte forma:
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.
    
3. Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.
    
4. Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.
    
5. Em **Editar Usuário do Skype for Business Server em** Política de Chat **Persistente,** selecione a política de usuário de Chat Persistente que você deseja aplicar.
    
    > [!NOTE]
    > As **\<Automatic\>** configurações aplicam a política efetiva padrão. Essas configurações são aplicadas automaticamente pelo servidor.
  
6. Clique em **Confirmar**.
    

