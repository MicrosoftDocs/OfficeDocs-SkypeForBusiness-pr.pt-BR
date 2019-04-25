---
title: Criar um administrador de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Resumo: Leia este tópico para saber como criar uma função de administrador de servidor de Chat persistente para habilitar a configuração inicial e o gerenciamento de serviços de Chat persistente no Skype para Business Server 2015.'
ms.openlocfilehash: fb8a222f65f6fe579d3600df15a53bb84f65de66
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225339"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Criar um administrador de Chat Persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como criar uma função de administrador de servidor de Chat persistente para habilitar a configuração inicial e o gerenciamento de serviços de Chat persistente no Skype para Business Server 2015.
  
No Skype para Business Server, os usuários que executam tarefas específicas devem ser atribuídos como membros de um ou mais grupos específicos. Controle de acesso baseado em função (RBAC) é usado para conceder privilégios atribuindo usuários a Skype predefinido para funções administrativas do servidor de negócios. Essas funções correspondem a grupos de segurança universais nos Serviços de Domínio Active Directory. Membros do grupo de segurança Persistent Chat Administrator, função CsPersistentChatAdministrator, recebem acesso para os cmdlets do servidor de Chat persistente, que podem ser executados usando o Skype para Business Server Management Shell ou o Skype para negócios Painel de controle do servidor.
  
Antes de configurar e administrar o Servidor de Chat Persistente, certifique-se de que as permissões e os direitos do usuário adequados estejam em vigor e que os usuários designados como administradores do Chat Persistente serão adicionados ao grupo de segurança Administradores do Chat Persistente.
  
> [!NOTE] 
> Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015.

## <a name="create-a-persistent-chat-administrator"></a>Criar um administrador de Chat Persistente

Para adicionar um usuário ao grupo de segurança Persistent Chat Administrator, função CsPersistentChatAdministrator, execute as seguintes etapas:
  
1. Usando uma conta que tenha permissão para modificar a associação a um grupo do Active Directory, faça logon em um computador em que os usuários e computadores do Active Directory tenham sido instalados.
    
2. Clique em Iniciar, clique em Todos os Programas, clique em Ferramentas Administrativas e, em seguida, clique em Usuários e Computadores do Active Directory.
    
3. Em Usuários e Computadores do Active Directory, expanda o nome do seu domínio e clique no contêiner de Usuários.
    
4. Clique com o botão direito no grupo de segurança CsPersistentChatAdministrator e clique em Propriedades.
    
5. Na caixa de diálogo Propriedades, na guia Membros, clique em Adicionar.
    
6. Na caixa de diálogo Selecionar Usuários, Computadores, Contatos ou Grupos, digite o nome de usuário ou nome de exibição do usuário a ser adicionado ao grupo (por exemplo, Ken Myer) na caixa Inserir os nomes de objeto a ser selecionados e clique em OK.
    
7. Na caixa de diálogo Propriedades, clique em OK.
    

