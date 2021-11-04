---
title: Categorias de chat persistente, salas de chat e funções de usuário Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Resumo: leia este tópico para saber mais sobre categorias, salas de chat e funções de usuário e administrador para o Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 0c468092016fae578e3c96987fed88b37db9d1c0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765209"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Categorias de chat persistente, salas de chat e funções de usuário Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber mais sobre categorias, salas de chat e funções de usuário e administrador para o Servidor de Chat Persistente no Skype for Business Server 2015.
  
Você pode controlar o acesso às salas de chat criando categorias de sala de chat e especificando o acesso a categorias e salas de chat em categorias. Você também pode especificar várias funções de administrador. Este tópico descreve: 
  
- Categorias para organizar salas de chat
    
- Salas de chat e funções de usuário
    
- Funções de administrador

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Categorias para organizar salas de chat

As categorias permitem que você organize salas de chat e controle quais usuários e grupos têm permissão para criar ou ingressar nas salas de chat dentro dessas categorias. Cada categoria tem propriedades associadas que determinam as opções disponíveis para as salas de chat dentro da categoria. Você controla o acesso a uma categoria específica especificando se um usuário é Acesso Permitido ou Negado.
  
A principal lógica para o conceito de Membros Permitidos e Negados são as paredes éticas. Por exemplo, é comum que instituições bancárias e financeiras tenham limites éticos que impeçam que comerciantes e analistas compartilhem comunicações enquanto implementam políticas e convenções. Para tratar desse requisito, um administrador pode criar categorias de modo que uma categoria permita que salas sejam criadas e usadas por comerciantes e a outra categoria, por analistas. Os usuários não poderão ser adicionados como membros de uma sala de chat se a categoria pai a impedir.
  
> [!IMPORTANT]
> Membros permitidos e negados em uma categoria não são iguais **a** uma função Membro, que se aplica a uma sala de Chat Persistente.> As pesquisas exibem todas as salas de chat abertas e fechadas para as quais o usuário que executa a pesquisa está na lista de membros Permitido e Negado. Salas secretas não são exibidas a menos que o usuário que fez a pesquisa seja membro de uma delas. O usuário pode pesquisar apenas as salas das quais ele já é membro ou às quais ele pode solicitar associação. 
  
## <a name="chat-rooms-and-user-roles"></a>Salas de chat e funções de usuário

Além dos Membros Permitidos e Negados para categorias, você também pode controlar o acesso às salas de chat especificando as seguintes funções de usuário: Criador, Gerente, Membro e Apresentador.
  
- **Criador**: usuários que têm permissão para criar salas de chat. Esses usuários estão na lista Criadores de certas categorias: eles podem criar salas de chat nessa categoria e podem também atribuir associações de acordo com a categoria e atribuir gerentes para que administrem a sala de chat. O usuário que cria uma sala de chat é automaticamente adicionado como gerente da sala.
    
    > [!NOTE]
    > A função de criador simplesmente concede direitos de criação de salas de chat. É a promoção automática a gerente que permite que o criador refine melhor as associações, os gerentes e assim por diante nos serviços de chat criados. 
  
    Esta função existe para lhe dar a opção de controlar quem cria salas de chat em sua organização, particularmente se quiser gerenciar centralmente a criação de salas de chat para impor políticas e convenções e, subsequentemente, delegar o gerenciamento das salas de chat a outros usuários na organização.
    
- **Gerente**: usuários que gerenciam as propriedades de uma sala de chat. Os gerentes de sala de chat podem modificar a lista de membros (adicionar ou remover membros) e modificar a lista de gerentes da sala de chat (adicionar ou remover gerentes). Os gerentes de sala de chat podem adicionar a si próprios à lista de membros ou de apresentadores (para salas de auditório) para que possam participar da sala de chat. Os gerentes de sala de chat também podem desabilitar as salas de chat (os administradores podem consultar as salas de chat desabilitadas e exclui-las permanentemente). Os gerentes podem alterar todas as propriedades de uma sala de chat, à exceção da respectiva categoria. Somente o Administrador de Chat Persistente pode alterar a categoria após a criação da sala de chat.
    
    > [!IMPORTANT]
    > Se o gerente for também o criador em outra categoria, ele poderá alterar a categoria para uma em que ele esteja autorizado a criar salas. 
  
- **Membro**: usuários que são membros de uma sala de chat. Esses usuários podem ver as salas de chat no diretório (mesmo que a sala de chat seja secreta), bem como se inscrever na sala de chat (incluindo opções de metadados, como mensagens não lidas, filtros de ego e filtros de palavra-chave) e participar da sala de chat (pode postar, a menos que a sala seja uma sala de auditório onde somente apresentadores podem postar,  obter conteúdo e pesquisa). Os usuários que não são membros da sala de chat podem pesquisar pela sala de chat se eles estão na lista Membros Permitidos da categoria, mas precisam solicitar acesso para ingressar nessas salas de chat para acessar o conteúdo. (Não há acesso à solicitação ou aprovações internas no sistema; elas são feitas externamente por email, telefone ou outras formas de contato.)
    
- **Apresentador**: usuários que podem postar em uma sala de auditório.
    
## <a name="administrator-roles"></a>Funções de administrador

A seguir estão as funções de administrador para o Servidor de Chat Persistente:
  
- Administrador **de Chat Persistente**: a função administrador de chat persistente pode gerenciar salas de chat (modificar todas as propriedades, incluindo associação, gerentes, categorias, salas de marcação como desabilitadas), bem como criar e gerenciar categorias de sala de chat que definem quem pode criar e acessar salas de chat. Os administradores também podem marcar salas de chat como desabilitadas e limpar salas de chat que não estão mais ativas. Os administradores não estão sujeitos às restrições dos criadores ou membros permitidos. Eles podem criar qualquer tipo de sala de chat e adicionar a si próprios como membros de qualquer sala. Os administradores também podem modificar e gerenciar a configuração de Chat Persistente (propriedades do pool, configurações globais e configuração de conformidade) e também podem planejar e implementar a migração de uma implantação mais antiga do Servidor de Chat de Grupo para Skype for Business Server Servidor de Chat Persistente 2015.
    
    Os administradores de Chat Persistente são capazes de administrar o Servidor de Chat Persistente usando Windows PowerShell cmdlets remotamente (ou seja, de um computador diferente do Servidor de Chat Persistente). O Servidor de Chat Persistente verifica se o Administrador de Chat Persistente é membro do grupo local de administrador local RTC no Servidor front-end do Servidor de Chat Persistente.
    
- **Skype for Business Server 2015 Administrador**: Administrador corporativo geral do Skype for Business Server 2015 responsável pela implantação.
    
- **Gerente de operações**: usuário responsável por gerenciar as operações diárias.
    
- **Desenvolvedores e parceiros terceirizados**: os desenvolvedores terceirizados ampliam o sistema, fornecendo especialmente uma solução de parede ética para conversas em grupo, suporte e ferramentas de conformidade, clientes móveis/da Web e uma estrutura de desenvolvimento de bot.
    
## <a name="for-more-information"></a>Para saber mais

Para obter mais informações sobre como configurar e gerenciar salas de chat e funções de usuário, consulte os seguintes tópicos:
  
- [Criar um administrador de Chat Persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Gerenciar categorias no Servidor de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/categories.md)
    
- [Gerenciar salas de chat no Servidor de Chat Persistente no Skype for Business Server 2015](../../manage/persistent-chat/chat-rooms.md)
    

