---
title: Categorias de chat persistente, salas de chat e funções de usuário no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Resumo: Leia este tópico para saber mais sobre categorias, salas de chat e funções de usuário e administrador para servidor de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: bffdebdf6bbb57165b902026083de5628cdbc404
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418466"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Categorias de chat persistente, salas de chat e funções de usuário no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber mais sobre categorias, salas de chat e funções de usuário e administrador para servidor de chat persistente no Skype for Business Server 2015.
  
Você pode controlar o acesso a salas de chat criando categorias de sala de chat e especificando o acesso às categorias e salas de chat em cada categoria. Você também pode especificar diversas funções de administrador. Este tópico descreve: 
  
- Categorias para organizar salas de chat
    
- Salas de chat e funções de usuário
    
- Funções de administrador

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Categorias para organizar salas de chat

As categorias permitem que você organize salas de chat e controle quais usuários e grupos têm permissão para criar ou ingressar nas salas de chat em cada categoria. Cada uma delas tem propriedades associadas que determinam as opções disponíveis para as salas de chat naquela categoria. Você controla o acesso a determinada categoria especificando se um usuário tem seu acesso Permitido ou Negado.
  
A lógica principal do conceito de Membros Permitidos e Negados é baseada em paredes éticas. Por exemplo, é comum que instituições bancárias e financeiras tenham limites éticos que impeçam investidores e analistas de compartilharem comunicações enquanto implementam políticas e convenções. Para cumprir esse requisito, um administrador pode criar categorias de modo que uma categoria permita que salas sejam criadas e usadas por investidores e a outra categoria, por analistas. Os usuários não poderão ser adicionados como membro de uma sala de chat se a categoria pai impedir isso.
  
> [!IMPORTANT]
> Os membros permitidos e negados em uma categoria não são iguais a uma função de **membro** , que se aplica a uma sala de chat persistente. > pesquisas exibem todas as salas de chat abertas e fechadas para as quais o usuário que está realizando a pesquisa está na lista de membros permitidos e negados. Salas secretas não são exibidas, a menos que o usuário que fez a pesquisa seja membro de uma delas. O usuário pode pesquisar apenas as salas das quais ele já é membro ou às quais ele pode solicitar associação. 
  
## <a name="chat-rooms-and-user-roles"></a>Salas de chat e funções de usuário

Além dos membros permitidos e negados para categorias, você também pode controlar o acesso a salas de chat especificando as seguintes funções de usuário: criador, gerente, membro e apresentador.
  
- **Criador**: usuários que têm permissão para criar salas de chat. Esses usuários estão na lista Criadores de certas categorias: eles podem criar salas de chat naquela categoria e também atribuir associações de acordo com a categoria, bem como atribuir gerentes para administrarem a sala de chat. O usuário que cria uma sala de chat é automaticamente adicionado como gerente da sala.
    
    > [!NOTE]
    > A função de criador simplesmente concede direitos de criação de salas de chat. É a promoção automática a gerente que permite que o criador refine melhor as associações, os gerentes e assim por diante nos serviços de chat criados. 
  
    Esta função existe para lhe dar a opção de controlar quem cria salas de chat em sua organização, particularmente se quiser gerenciar centralmente a criação de salas de chat para impor políticas e convenções e, subsequentemente, delegar o gerenciamento das salas de chat a outros usuários na organização.
    
- **Gerente**: usuários que gerenciam as propriedades de uma sala de chat. Os gerentes de sala de chat podem modificar a lista de membros (adicionar e remover membros) e modificar a lista de gerentes da sala de chat (adicionar e remover gerentes). Os gerentes de sala de chat podem adicionar a si próprios à lista de membros ou de apresentadores (para salas de auditório) para que possam participar da sala de chat. Os gerentes de sala de chat também podem desabilitar as salas de chat (os administradores podem consultar as salas de chat desabilitadas e excluí-las permanentemente). Os gerentes podem alterar todas as propriedades de uma sala de chat, exceto sua categoria. Somente o administrador de chat persistente pode alterar a categoria após a criação da sala de chat.
    
    > [!IMPORTANT]
    > Se o gerente for também o criador em outra categoria, ele poderá alterar a categoria para que esteja autorizado a criar salas. 
  
- **Membro**: usuários que são membros de uma sala de chat. Esses usuários podem ver as salas de chat no diretório (mesmo se a sala de chat for secreta), bem como assinar a sala de chat (incluindo opções de metadados, como mensagens não lidas, filtros ego e filtros de palavra-chave) e participar da sala de chat (pode postar, a menos que a sala é uma sala Auditorium em que somente os apresentadores podem postar, obter conteúdo e Pesquisar). Os usuários que não são membros da sala de chat podem pesquisar a sala de chat se estiverem na lista de membros permitidos da categoria, mas precisarão solicitar acesso para participar dessas salas de chat para acessar o conteúdo. (Não há nenhum acesso de solicitação ou aprovações embutidas no sistema; elas são feitas externamente por email, telefone ou outras formas de contato.)
    
- **Apresentador**: usuários que podem postar em uma sala de auditório.
    
## <a name="administrator-roles"></a>Funções de administrador

Estas são as funções de administrador do servidor de chat persistente:
  
- **Administrador de chat persistente**: a função de administrador de chat persistente pode gerenciar salas de chat (modifique todas as propriedades, incluindo associação, gerentes, categorias, marcar salas como desabilitadas), bem como criar e gerenciar categorias de sala de chat que definem quem pode criar e acessar salas de chat. Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active. Administrators are not subject to the Creators or Allowed Members restrictions. Administrators can create any kind of chat room and add themselves as a member to any chat room. Os administradores também podem modificar e gerenciar a configuração de chat persistente (Propriedades do pool, configurações globais e configuração de conformidade) e também podem planejar e implementar a migração de uma implantação mais antiga do servidor de chat em grupo para o Skype for Business Server 2015 Servidor de chat persistente.
    
    Administradores de chat persistentes podem administrar o servidor de chat persistente usando cmdlets do Windows PowerShell remotamente (ou seja, de um computador que não seja o servidor de chat persistente). O servidor de chat persistente verifica se o administrador de chat persistente é um membro do grupo local de administrador do RTC local no servidor de front-end do servidor de chat persistente.
    
- **Administrador do Skype for Business server 2015**: administrador corporativo geral do Skype for business Server 2015 responsável pela implantação.
    
- **Gerente de operações**: usuário responsável por gerenciar as operações diárias.
    
- **Desenvolvedores e parceiros terceirizados**: desenvolvedores terceirizados ampliam o sistema, especialmente ao fornecerem uma solução de parede ética para conversas em grupo, ferramentas de conformidade e suporte, clientes móveis/Web e uma estrutura para desenvolvimento de bot.
    
## <a name="for-more-information"></a>Para obter mais informações

Para mais informações sobre configuração e gerenciamento de salas de chat e funções de usuário, consulte os seguintes tópicos:
  
- [Criar um administrador de Chat Persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Gerenciar categorias no Servidor de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/categories.md)
    
- [Gerenciar salas de chat no Servidor de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/chat-rooms.md)
    

