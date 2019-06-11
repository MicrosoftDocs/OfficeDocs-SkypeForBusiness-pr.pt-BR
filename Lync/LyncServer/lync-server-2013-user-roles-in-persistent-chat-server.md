---
title: 'Lync Server 2013: funções de usuário no servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36f84f71ca5253d28d9182acc9279010127ee6f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a>Funções de usuário no servidor de chat persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-03-19_

O servidor de chat persistente fornece o conceito de membros permitidos/negados, que se aplicam a categorias de chat persistentes e controles que podem acessar salas em uma categoria específica.

<div>


> [!IMPORTANT]  
> Os membros permitidos/negados em uma categoria não são iguais a uma função de <STRONG>membro</STRONG> , que se aplica a uma sala de chat persistente.<BR>Pesquisas exibem todas as salas de chat abertas e fechadas para as quais o usuário que está realizando a pesquisa está na lista de membros permitidos/recusados. Salas secretas não são exibidas, a menos que o usuário que fez a pesquisa seja membro de uma delas. O usuário pode pesquisar apenas as salas das quais ele já é membro ou às quais ele pode solicitar associação.



</div>

O motivo principal para o conceito de membros permitidos/negados é paredes éticas. Por exemplo, é comum que instituições bancárias e financeiras tenham limites éticos que impeçam investidores e analistas de compartilharem comunicações enquanto implementam políticas e convenções. Para cumprir esse requisito, um administrador pode criar categorias de modo que uma categoria permita que salas sejam criadas e usadas por investidores e a outra categoria, por analistas. Com essa restrição, o sistema proíbe a adição de um usuário como membro da sala se a categoria pai a impedir.

Veja a seguir as quatro funções de usuário do servidor de chat persistente:

  - **Criador:** Usuários que têm permissões para criar salas de chat. Esses usuários estão na lista Criadores de certas categorias: eles podem criar salas de chat naquela categoria e também atribuir associações de acordo com a categoria, bem como atribuir gerentes para administrarem a sala de chat. O usuário que cria uma sala de chat é automaticamente adicionado como gerente da sala.
    
    <div>
    

    > [!NOTE]  
    > A função de criador simplesmente concede direitos de criação de salas de chat. É a promoção automática a gerente que permite que o criador refine melhor as associações, os gerentes e assim por diante nos serviços de chat criados.

    
    </div>
    
    Esta função existe para lhe dar a opção de controlar quem cria salas de chat em sua organização, particularmente se quiser gerenciar centralmente a criação de salas de chat para impor políticas e convenções e, subsequentemente, delegar o gerenciamento das salas de chat a outros usuários na organização.

  - **Gerente:** Usuários que gerenciam Propriedades de uma sala de chat. Os gerentes de sala de chat podem modificar a lista de membros (adicionar e remover membros) e modificar a lista de gerentes da sala de chat (adicionar e remover gerentes). Os gerentes de sala de chat podem adicionar a si próprios à lista de membros ou de apresentadores (para salas de auditório) para que possam participar da sala de chat. Os gerentes de sala de chat também podem desabilitar as salas de chat (os administradores podem consultar as salas de chat desabilitadas e excluí-las permanentemente). Os gerentes podem alterar todas as propriedades de uma sala de chat, exceto sua categoria. Somente o administrador de chat persistente pode alterar a categoria após a criação da sala de chat.
    
    <div>
    

    > [!IMPORTANT]  
    > Se o gerente for também o criador em outra categoria, ele poderá alterar a categoria para que esteja autorizado a criar salas.

    
    </div>

  - **Membro:** Usuários que são membros de uma sala de chat. Esses usuários podem ver as salas de chat no diretório (mesmo se a sala de chat for secreta), bem como assinar a sala de chat (incluindo opções de metadados, como mensagens não lidas, filtros ego e filtros de palavra-chave) e participar da sala de chat (pode postar, a menos que a sala é uma sala Auditorium em que somente os apresentadores podem postar, obter conteúdo e Pesquisar). Os usuários que não são membros da sala de chat podem pesquisar a sala de chat se estiverem na lista de membros permitidos da categoria, mas precisarão solicitar acesso para participar dessas salas de chat para acessar o conteúdo. (Não há nenhum acesso de solicitação ou aprovações embutidas no sistema; elas são feitas externamente por email, telefone ou outras formas de contato.)

  - **Apresentador:** Usuários que podem postar em uma sala de Auditorium.

<div>


> [!NOTE]  
> O servidor de chat persistente permite que os usuários criem e gerenciem a sala de chat para um site específico. No entanto, os usuários não podem criar ou gerenciar salas de chat em outros sites na mesma topologia. Certifique-se de especificar os criadores e gerentes da sala de chat para todos os sites da sua organização.



</div>

As funções a seguir são funções de administrador para o servidor de chat persistente:

  - **Administrador de chat persistente (CsPersistentChatAdministrator):** Esta é uma nova função de controle de acesso baseado em função (RBAC) para administrar e gerenciar o servidor de chat persistente. Os usuários ou grupos de segurança designados como CsPersistentChatAdministrator são capazes de administrar o servidor de chat persistente usando cmdlets do Windows PowerShell remotamente (ou seja, de um computador que não seja o servidor de chat persistente). O servidor de chat persistente verifica se o administrador de chat persistente é membro do grupo local de administrador local do RTC no servidor de front-end do servidor de chat persistente.
    
    A função CsPersistentChatAdministrator pode gerenciar salas de chat (modifique todas as propriedades, incluindo associação, gerentes, categorias, marcar salas como desabilitadas), bem como criar e gerenciar categorias de salas de chat que definem quem pode criar e acessar salas de chat. Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active. Administrators are not subject to the Creators or Allowed Members restrictions. Administrators can create any kind of chat room and add themselves as a member to any chat room. Os administradores também podem modificar e gerenciar a configuração de chat persistente (Propriedades de pool, configurações globais e configuração de conformidade) e também podem planejar e implementar a migração de uma implantação de servidor de chat de grupo mais antiga para o Lync Server 2013 chat persistente Servidor.

  - **Administrador do Lync:** Administrador corporativo geral do Lync Server 2013 responsável pela implantação.

  - **Gerenciador de operações:** Usuário responsável por gerenciar operações do dia a dia.

  - **Desenvolvedores e parceiros de terceiros:** Desenvolvedores de terceiros estendem o sistema, em particular, fornecendo uma solução de parede ética para conversas em grupo, suporte e ferramentas de conformidade, clientes da Web/móveis e uma estrutura para o desenvolvimento de bot.

</div>

<span> </span>

</div>

</div>

</div>

