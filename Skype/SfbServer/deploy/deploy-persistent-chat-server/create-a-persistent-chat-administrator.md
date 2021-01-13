---
title: Criar um administrador de Chat Persistente no Skype for Business Server 2015
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
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Resumo: Leia este tópico para saber como criar uma função de administrador de Servidor de Chat Persistente para habilitar a configuração inicial e o gerenciamento de serviços de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: eea989b0284353e193ebf99a0be99b2d0811e532
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802091"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Criar um administrador de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como criar uma função de administrador de Servidor de Chat Persistente para habilitar a configuração inicial e o gerenciamento de serviços de Chat Persistente no Skype for Business Server 2015.
  
No Skype for Business Server, os usuários que executam tarefas específicas devem ser atribuídos como membros de um ou mais grupos específicos. Role-Based Controle de Acesso (RBAC) é usado para conceder privilégios atribuindo usuários a funções administrativas predefinidos do Skype for Business Server. Essas funções correspondem a grupos de segurança universais nos Serviços de Domínio Active Directory. Os membros do grupo de segurança Administrador de Chat Persistente, CsPersistentChatAdministrator, têm acesso aos cmdlets do Servidor de Chat Persistente, que podem ser executados usando o Shell de Gerenciamento do Skype for Business Server ou o Painel de Controle do Skype for Business Server.
  
Antes de configurar e administrar o Servidor de Chat Persistente, certifique-se de que os direitos e permissões de usuário apropriados estão em uso e que todos os usuários que atuarão como administradores de Chat Persistente sejam adicionados ao grupo de segurança Administrador de Chat Persistente.
  
> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here) Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.

## <a name="create-a-persistent-chat-administrator"></a>Criar um administrador de Chat Persistente

Para adicionar um usuário ao grupo de segurança Administrador de Chat Persistente, CsPersistentChatAdministrator, execute as seguintes etapas:
  
1. Usando uma conta que tenha permissão para modificar a associação de um grupo do Active Directory, faça logoff em um computador em que os Usuários e Computadores do Active Directory tenham sido instalados.
    
2. Clique em Iniciar, clique em Todos os Programas, clique em Ferramentas Administrativas e, em seguida, clique em Usuários e Computadores do Active Directory.
    
3. Em Usuários e Computadores do Active Directory, expanda o nome do seu domínio e clique no contêiner de Usuários.
    
4. Clique com o botão direito do mouse no grupo de segurança CsPersistentChatAdministrator e clique em Propriedades.
    
5. Na caixa de diálogo Propriedades, na guia Membros, clique em Adicionar.
    
6. Na caixa de diálogo Selecionar Usuários, Computadores, Contatos ou Grupos, digite o nome de usuário ou nome de exibição do usuário a ser adicionado ao grupo na caixa Digite os nomes de objeto a serem selecionados e clique em OK.
    
7. Na caixa de diálogo Propriedades, clique em OK.
    

