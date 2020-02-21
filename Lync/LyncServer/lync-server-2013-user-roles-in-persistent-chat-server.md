---
title: 'Lync Server 2013: funções de usuário no servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7d01b15c035b3f14a0f2d6dba92719d7f885437
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a>Funções de usuário no servidor de chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-03-19_

Servidor de chat persistente fornece o conceito de membros permitidos/negados, que se aplicam a categorias de chat persistente e controles que podem acessar salas em uma determinada categoria.

<div>


> [!IMPORTANT]  
> Membros permitidos/negados em uma categoria não é o mesmo que uma função de <STRONG>membro</STRONG> , que se aplica a uma sala de chat persistente.<BR>As pesquisas exibem todas as salas de chat abertas e fechadas das quais o usuário que fez a pesquisa está na lista de membros permitidos/negados. Salas secretas não são exibidas a menos que o usuário que fez a pesquisa seja membro de uma delas. O usuário pode pesquisar apenas as salas das quais ele já é membro ou às quais ele pode solicitar associação.



</div>

A lógica principal do conceito de membros permitidos/negados sem baseia em paredes éticas. Por exemplo, é comum que instituições bancárias e financeiras tenham limites éticos que impeçam que comerciantes e analistas compartilhem comunicações enquanto implementam políticas e convenções. Para tratar desse requisito, um administrador pode criar categorias de modo que uma categoria permita que salas sejam criadas e usadas por comerciantes e a outra categoria, por analistas. Com isso, uma restrição é projetada no sistema proibindo a adição de um usuário como membro de uma sala se a categoria pai impedir isso.

A seguir estão as quatro funções de usuário do servidor de chat persistente:

  - **Criador:** Usuários que têm permissões para criar salas de chat. Esses usuários estão na lista Criadores de certas categorias: eles podem criar salas de chat nessa categoria e podem também atribuir associações de acordo com a categoria e atribuir gerentes para que administrem a sala de chat. O usuário que cria uma sala de chat é automaticamente adicionado como gerente da sala.
    
    <div>
    

    > [!NOTE]  
    > A função de criador simplesmente concede direitos de criação de salas de chat. É a promoção automática a gerente que permite que o criador refine melhor as associações, os gerentes e assim por diante nos serviços de chat criados.

    
    </div>
    
    Esta função existe para lhe dar a opção de controlar quem cria salas de chat em sua organização, particularmente se quiser gerenciar centralmente a criação de salas de chat para impor políticas e convenções e, subsequentemente, delegar o gerenciamento das salas de chat a outros usuários na organização.

  - **Gerente:** Usuários que gerenciam Propriedades de uma sala de chat. Os gerentes de sala de chat podem modificar a lista de membros (adicionar ou remover membros) e modificar a lista de gerentes da sala de chat (adicionar ou remover gerentes). Os gerentes de sala de chat podem adicionar a si próprios à lista de membros ou de apresentadores (para salas de auditório) para que possam participar da sala de chat. Os gerentes de sala de chat também podem desabilitar as salas de chat (os administradores podem consultar as salas de chat desabilitadas e exclui-las permanentemente). Os gerentes podem alterar todas as propriedades de uma sala de chat, à exceção da respectiva categoria. Somente o administrador de chat persistente pode alterar a categoria após a criação da sala de chat.
    
    <div>
    

    > [!IMPORTANT]  
    > Se o gerente for também o criador em outra categoria, ele poderá alterar a categoria para uma em que ele esteja autorizado a criar salas.

    
    </div>

  - **Membro:** Usuários que são membros de uma sala de chat. Esses usuários podem ver as salas de chat no diretório (mesmo que a sala de bate-papo seja secreta), bem como inscrever-se na sala de chat (incluindo as opções de metadados como mensagens não lidas, filtros egos e filtros de palavra-chave) e participar da sala de chat (podem postar, a menos que a sala é uma sala auditório em que apenas os apresentadores podem postar, obter conteúdo e Pesquisar. Os usuários que não são membros da sala de chat podem pesquisar a sala de chat se estiverem na lista de membros permitidos da categoria, mas precisarão solicitar acesso para participar dessas salas de chat para acessar o conteúdo. (Não há nenhuma solicitação de acesso ou aprovação no sistema; elas são feitas externamente por email, telefone ou outras formas de contato.)

  - **Apresentador:** Usuários que podem postar em uma sala do auditório.

<div>


> [!NOTE]  
> Servidor de chat persistente permite que os usuários criem e gerenciem a sala de chat de um site específico. No entanto, os usuários não podem criar ou gerenciar salas de chat em outros sites dentro da mesma topologia. Certifique-se de especificar os criadores e gerentes de sala de chat para todos os sites em sua organização.



</div>

As funções a seguir são funções de administrador para o servidor de chat persistente:

  - **Administrador de chat persistente (CsPersistentChatAdministrator):** Esta é uma nova função RBAC (controle de acesso baseado em função) para administrar e gerenciar o servidor de chat persistente. Os usuários ou grupos de segurança designados como CsPersistentChatAdministrator podem administrar o servidor de chat persistente usando cmdlets do Windows PowerShell remotamente (ou seja, de um computador diferente do servidor de chat persistente). Servidor de chat persistente verifica se o administrador de chat persistente é membro do grupo local de administrador local RTC no servidor de front-end do servidor de chat persistente.
    
    A função CsPersistentChatAdministrator permite gerenciar salas de chat (modificar todas as propriedades, inclusive associações, gerentes, categorias, marcar salas como desabilitadas), bem como criar e gerenciar categorias de sala de chat que definem quem pode criar e acessar as salas de chat. Os administradores também podem marcar salas de chat como desabilitadas e limpar salas de chat que não estão mais ativas. Os administradores não estão sujeitos às restrições dos criadores ou membros permitidos. Eles podem criar qualquer tipo de sala de chat e adicionar a si próprios como membros de qualquer sala. Os administradores também podem modificar e gerenciar a configuração de chat persistente (Propriedades de pool, configurações globais e configuração de conformidade) e também podem planejar e implementar a migração de uma implantação de servidor de chat de grupo mais antiga para o Lync Server 2013 chat persistente Do.

  - **Administrador do Lync:** Administrador corporativo geral do Lync Server 2013 responsável pela implantação.

  - **Gerenciador de operações:** Usuário responsável por gerenciar as operações diárias.

  - **Desenvolvedores e parceiros de terceiros:** Desenvolvedores terceirizados estendem o sistema, em particular, fornecendo uma solução de parede ética para conversas de grupo, suporte e ferramentas de conformidade, clientes Web/móveis e uma estrutura para o desenvolvimento de bot.

</div>

<span> </span>

</div>

</div>

</div>

