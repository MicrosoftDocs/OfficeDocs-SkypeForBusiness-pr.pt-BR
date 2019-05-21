---
title: Criar um administrador de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Resumo: Leia este tópico para saber como criar uma função de administrador de servidor de chat persistente para habilitar a configuração e o gerenciamento iniciais de serviços de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 1b593f1de776f1896d43bab35a15af7b6bcf7245
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273879"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Criar um administrador de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como criar uma função de administrador de servidor de chat persistente para habilitar a configuração e o gerenciamento iniciais de serviços de chat persistente no Skype for Business Server 2015.
  
No Skype for Business Server, os usuários que executam tarefas específicas devem ser atribuídos como membros de um ou mais grupos específicos. O controle de acesso baseado em função (RBAC) é usado para conceder privilégios atribuindo usuários a funções administrativas predefinidas do Skype for Business Server. Essas funções correspondem a grupos de segurança universais nos Serviços de Domínio Active Directory. Os membros do grupo de segurança de administrador de chat persistente, CsPersistentChatAdministrator, recebem acesso aos cmdlets do servidor de chat persistente, que podem ser executados usando o Shell de gerenciamento do Skype for Business Server ou o Skype for Business Painel de controle do servidor.
  
Antes de configurar e administrar o Servidor de Chat Persistente, certifique-se de que as permissões e os direitos do usuário adequados estejam em vigor e que os usuários designados como administradores do Chat Persistente serão adicionados ao grupo de segurança Administradores do Chat Persistente.
  
> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [jornada do Skype for Business para o Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.

## <a name="create-a-persistent-chat-administrator"></a>Criar um administrador de Chat Persistente

Para adicionar um usuário ao grupo de segurança de administrador de chat persistente, CsPersistentChatAdministrator, execute as seguintes etapas:
  
1. Usando uma conta que tenha permissão para modificar a associação a um grupo do Active Directory, faça logon em um computador em que os usuários e computadores do Active Directory tenham sido instalados.
    
2. Clique em Iniciar, clique em Todos os Programas, clique em Ferramentas Administrativas e, em seguida, clique em Usuários e Computadores do Active Directory.
    
3. Em Usuários e Computadores do Active Directory, expanda o nome do seu domínio e clique no contêiner de Usuários.
    
4. Clique com o botão direito no grupo de segurança CsPersistentChatAdministrator e clique em Propriedades.
    
5. Na caixa de diálogo Propriedades, na guia Membros, clique em Adicionar.
    
6. Na caixa de diálogo Selecionar Usuários, Computadores, Contatos ou Grupos, digite o nome de usuário ou nome de exibição do usuário a ser adicionado ao grupo (por exemplo, Ken Myer) na caixa Inserir os nomes de objeto a ser selecionados e clique em OK.
    
7. Na caixa de diálogo Propriedades, clique em OK.
    

