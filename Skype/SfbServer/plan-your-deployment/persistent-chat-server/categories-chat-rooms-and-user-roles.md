---
title: Categorias de chat persistente, salas de chat e funções de usuário no Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Resumo: Leia este tópico para saber mais sobre categorias, salas de bate-papo e funções de administrador e usuário para o servidor de bate-papo persistente no Skype para Business Server 2015.'
ms.openlocfilehash: 0a65d5d8944d28ba834fac461051f23fcdd98800
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898856"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Categorias de chat persistente, salas de chat e funções de usuário no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber mais sobre categorias, salas de bate-papo e funções de administrador e usuário para o servidor de bate-papo persistente no Skype para Business Server 2015.
  
Você pode controlar o acesso a salas de chat criando categorias de sala de chat e especificando o acesso às categorias e salas de chat em cada categoria. Você também pode especificar diversas funções de administrador. Este tópico descreve: 
  
- Categorias para organizar salas de chat
    
- Salas de chat e funções de usuário
    
- Funções de administrador

> [!NOTE] 
> Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Categorias para organizar salas de chat

As categorias permitem que você organize salas de chat e controle quais usuários e grupos têm permissão para criar ou ingressar nas salas de chat em cada categoria. Cada uma delas tem propriedades associadas que determinam as opções disponíveis para as salas de chat naquela categoria. Você controla o acesso a determinada categoria especificando se um usuário tem seu acesso Permitido ou Negado.
  
A lógica principal do conceito de Membros Permitidos e Negados é baseada em paredes éticas. Por exemplo, é comum que instituições bancárias e financeiras tenham limites éticos que impeçam investidores e analistas de compartilharem comunicações enquanto implementam políticas e convenções. Para cumprir esse requisito, um administrador pode criar categorias de modo que uma categoria permita que salas sejam criadas e usadas por investidores e a outra categoria, por analistas. Os usuários não poderão ser adicionados como membro de uma sala de chat se a categoria pai impedir isso.
  
> [!IMPORTANT]
> Membros permitidos e negados em uma categoria não são iguais uma função de **membro** , que se aplica ao room.> Chat persistente e exibição de pesquisas todas abrir e fechado para que o usuário que está executando a pesquisa está no permitidos de salas de chat e lista de membros negados. Salas secretas não são exibidas, a menos que o usuário que fez a pesquisa seja membro de uma delas. O usuário pode pesquisar apenas as salas das quais ele já é membro ou às quais ele pode solicitar associação. 
  
## <a name="chat-rooms-and-user-roles"></a>Salas de chat e funções de usuário

Além dos permitidos e membros negados para categorias, você também pode controlar o acesso a salas de bate-papo, especificando as seguintes funções de usuário: criador, gerente, membro e apresentador.
  
- **Criador**: usuários que têm permissão para criar salas de chat. Esses usuários estão na lista Criadores de certas categorias: eles podem criar salas de chat naquela categoria e também atribuir associações de acordo com a categoria, bem como atribuir gerentes para administrarem a sala de chat. O usuário que cria uma sala de chat é automaticamente adicionado como gerente da sala.
    
    > [!NOTE]
    > A função de criador simplesmente concede direitos de criação de salas de chat. É a promoção automática a gerente que permite que o criador refine melhor as associações, os gerentes e assim por diante nos serviços de chat criados. 
  
    Esta função existe para lhe dar a opção de controlar quem cria salas de chat em sua organização, particularmente se quiser gerenciar centralmente a criação de salas de chat para impor políticas e convenções e, subsequentemente, delegar o gerenciamento das salas de chat a outros usuários na organização.
    
- **Gerente**: usuários que gerenciam as propriedades de uma sala de chat. Os gerentes de sala de chat podem modificar a lista de membros (adicionar e remover membros) e modificar a lista de gerentes da sala de chat (adicionar e remover gerentes). Os gerentes de sala de chat podem adicionar a si próprios à lista de membros ou de apresentadores (para salas de auditório) para que possam participar da sala de chat. Os gerentes de sala de chat também podem desabilitar as salas de chat (os administradores podem consultar as salas de chat desabilitadas e excluí-las permanentemente). Os gerentes podem alterar todas as propriedades de uma sala de chat, exceto sua categoria. Somente o administrador de Chat persistente pode alterar a categoria após ter sido criada na sala de chat.
    
    > [!IMPORTANT]
    > Se o gerente for também o criador em outra categoria, ele poderá alterar a categoria para que esteja autorizado a criar salas. 
  
- **Membro**: usuários que são membros de uma sala de bate-papo. Esses usuários podem ver as salas de bate-papo no diretório (mesmo se a sala de bate-papo for secreta), bem como assine a sala de chat (incluindo as opções de metadados, como mensagens não lidas, ego filtros e filtros de palavra-chave) e participar na sala de chat (pode postar, a menos que a sala é uma sala de auditório, onde apenas os apresentadores podem postar, obter conteúdo e de pesquisa). Os usuários que não são membros da sala de chat podem pesquisar a sala de bate-papo se estiverem na lista de membros permitidos da categoria, mas precisará solicitar acesso a ingressar estas salas de chat para acessar o conteúdo. (Nenhum solicitar acesso ou aprovações internas do sistema; esses são feitas externamente por email, telefone ou outros formulários de contato).
    
- **Apresentador**: usuários que podem postar em uma sala de auditório.
    
## <a name="administrator-roles"></a>Funções de administrador

Estas são as funções de administrador para o servidor de Chat persistente:
  
- **Administrador de Chat persistente**: função de administrador de Chat persistente a, bem como criar e gerenciar categorias de sala de chat que definem quem pode gerenciar salas de chat (modificar todas as propriedades, incluindo a associação, gerentes, categorias, salas de marca como disabled), pode criar e acessar as salas de bate-papo. Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active. Administrators are not subject to the Creators or Allowed Members restrictions. Administrators can create any kind of chat room and add themselves as a member to any chat room. Os administradores podem também modificar e gerenciar a configuração de Chat persistente (Propriedades do pool, as configurações globais e configuração de conformidade) e pode também pretende e implementar a migração de uma implantação de servidor de Chat de grupo mais antiga para Skype para Business Server 2015 Servidor de Chat persistente.
    
    Administradores de Chat persistente são capazes de administrar o servidor de Chat persistente usando cmdlets do Windows PowerShell remotamente (ou seja, de um computador diferente do servidor de Chat persistente). Servidor de Chat persistente verifica que Persistent Chat Administrator é um membro do grupo local administrador RTC Local em Persistent Chat Server servidor Front-End.
    
- **Skype para Business Server 2015 administrador**: administrador empresarial global do Skype para Business Server 2015 responsável pela implantação.
    
- **Gerente de operações**: usuário responsável por gerenciar as operações diárias.
    
- **Desenvolvedores e parceiros terceirizados**: desenvolvedores terceirizados ampliam o sistema, especialmente ao fornecerem uma solução de parede ética para conversas em grupo, ferramentas de conformidade e suporte, clientes móveis/Web e uma estrutura para desenvolvimento de bot.
    
## <a name="for-more-information"></a>Para obter mais informações

Para mais informações sobre configuração e gerenciamento de salas de chat e funções de usuário, consulte os seguintes tópicos:
  
- [Criar um administrador de Chat Persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Gerenciar categorias no Servidor de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/categories.md)
    
- [Gerenciar salas de chat no Servidor de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/chat-rooms.md)
    

