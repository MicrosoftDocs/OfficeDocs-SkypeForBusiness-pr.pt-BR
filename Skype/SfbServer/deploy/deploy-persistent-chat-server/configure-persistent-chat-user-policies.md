---
title: Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumo: Leia este tópico para saber como criar políticas de usuário inicial para o servidor de Chat persistente no Skype para Business Server 2015. As diretivas de usuário de Chat persistentes determinam se ou não os usuários poderão acesso a salas de bate-papo.'
ms.openlocfilehash: 84bc1236bf8fd08063f55c9a0c3b0d63ff4eb280
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894504"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como criar políticas de usuário inicial para o servidor de Chat persistente no Skype para Business Server 2015. As diretivas de usuário de Chat persistentes determinam se ou não os usuários poderão acesso a salas de bate-papo.
  
Você pode gerenciar políticas de usuário do servidor de Chat persistente nos seguintes níveis: global, site ou usuário. Inicialmente, você configura a política global para habilitar configurações de Chat Persistente para todos os usuários na sua implantação, e então cria políticas adicionais de site e usuário para controlar se o Chat Persistente está ativado para sites e usuários específicos.
  
Este tópico inclui as seguintes seções:
  
- Configurar a política global
    
- Criar uma política de site
    
- Criar uma política de usuário
    
- Aplicar uma política a um usuário ou grupo de usuários
    
> [!NOTE] 
> Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015.

## <a name="configure-the-global-policy"></a>Configurar a política global

Para configurar a política global:
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.
    
3. No painel de controle do servidor de negócios do Skype, clique em **Chat persistente**e clique em **Política de Chat persistente**.
    
4. Clique em **Global** na lista de políticas, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.
    
5. Em **Editar Política de Chat Persistent - Global**, siga este procedimento: 
    
   - Em **Nome**, especifique um novo nome para a política global, se não desejar usar o padrão Global.
    
   - Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política Global para _centralSiteName_).
    
   - Para controlar o Chat persistente para todos os sites e usuários não especificamente controlados através de uma política de site ou usuário, marque ou desmarque a caixa de seleção **Habilitar Chat persistente** .
    
6. Clique em **Confirmar**.
    
## <a name="create-a-site-policy"></a>Criar uma política de site

Para cada site implantado, é possível criar uma política de Chat Persistente específica do site. A configuração no site substitui a política global, mas somente para o site específico coberto pela política de site. Para criar uma política de site:
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.
    
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
    
2. No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.
    
4. Clique em **Novo** e em **Política de usuário**.
    
5. Em **Nova Política de Chat Persistente**, siga este procedimento:
    
   - Em **Nome**, especifique um nome para a nova política de usuário.
    
   - Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política de Chat persistente para usuário específico).
    
   - Para controlar o Chat persistente para todos os usuários que não são especificamente controlados através de uma política de usuário, marque ou desmarque a caixa de seleção **Habilitar Chat persistente** .
    
6. Clique em **Confirmar**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Aplicar uma política a uma conta de usuário

Após criar as políticas, você pode aplicá-las a uma conta de usuário da seguinte forma:
  
1. Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.
    
2. No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.
    
3. Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.
    
4. Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.
    
5. Em **Editar Skype para usuário de servidor de negócios** em **política de Chat persistente**, selecione a política de usuário de Chat persistente que você deseja aplicar.
    
    > [!NOTE]
    > O ** \<automática\> ** configurações se aplicam a diretiva padrão de efetiva. Essas configurações são aplicadas automaticamente pelo servidor.
  
6. Clique em **Confirmar**.
    

