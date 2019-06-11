---
title: 'Lync Server 2013: Configurar categorias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310d0b2e32c8a21f00e20593a408df260eb80e32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a>Configurar categorias no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-06_

No painel de controle do Lync Server 2013, você pode usar a seção **categoria** da página de **chat persistente** para configurar categorias. Uma categoria de sala de chat persistente é uma estrutura lógica para organizar salas de chat. Uma categoria define um conjunto padrão de listas de controle de acesso (ACLs) para controle dos usuários e dos grupos de usuários que podem criar ou ingressar em salas de chat. É possível usar as categorias para aplicar paredes éticas entre diferentes subdivisões dentro de suas organizações.

As categorias de sala de chat podem conter salas de chat, mas nenhuma outra categoria. Cada categoria descreve o conteúdo com metadados, como Name e Description. Além disso, a categoria tem propriedades as quais podem ser definidas para controlar o comportamento das salas de bate-papo pertencentes, como se as salas de chat permitissem  Invitations ou File Uploads ou contivessem Chat History.

<div>

## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar categorias salas de bate-papo

1.  A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.

2.  No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e, em seguida, insira a URL de administração. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Você também pode usar cmdlets do Windows PowerShell. Para obter detalhes, consulte Configurando o <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.

    
    </div>

3.  Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Categoria**.
    
    Para várias implantações de pool do servidor de chat persistente, selecione o pool apropriado na lista suspensa.

4.  Na página **Categoria**, clique em **Novo** ou **Editar**.

5.  Em **selecionar um serviço**, selecione o serviço correspondente ao pool de servidores de chat persistente em que a categoria precisa ser criada. O serviço é o pool persistente do servidor de chat que o chat (cliente) persistente usa para identificar a qual pool a categoria pertence. Uma categoria pode pertencer a apenas um pool de servidor de chat persistente e não pode ser movida para outra ou compartilhada com outro pool.

6.  Em **Nova categoria**, faça o seguinte:
    
    1.  Em  **Nome**, especifique um nome para a nova categoria de sala.
    
    2.  Em  **Descrição**, forneça uma descrição detalhada para a categoria da sala (por exemplo, uma categoria de sala para Contoso).
    
    3.  Para controlar se os convites podem ser ativados por salas de chat que pertencem a tal categoria, selecione ou limpe a caixa de marcação **Habilitar convites**. Se marcado, as salas nesta categoria poderão ter convites ativados ou desativados; em caso de não marcado, as salas nessa categoria não podem ter convite. Se uma sala tem convites em, quando um novo membro é adicionado a uma sala, ele recebe uma notificação da nova sala em seu cliente de chat persistente.
    
    4.  Para controlar o envio de arquivo nas salas de chat pertencentes a esta categoria, selecione ou desmarque a caixa de seleção **Habilitar carregamento de arquivo**. Se estiver marcada, as salas desta categoria podem habilitar ou desabilitar carregamentos de arquivos; se estiver desmarcada, as salas nesta categoria não podem ter arquivos carregados.
        
        <div>
        

        > [!IMPORTANT]  
        > Essa configuração é imposta no servidor porque aplicativos personalizados ou clientes de chat em grupo anterior que usam o servidor de chat de grupo&nbsp;do Office Communications Server 2007 R2 ou o Lync Server 2010, o chat em grupo podem postar arquivos para uma sala. O cliente do Lync 2013 não tem recurso de carregamento/download de arquivo, portanto, se você tiver uma implantação do Lync 2013 ou do Lync 2013, não será possível postar arquivos em uma sala de chat do servidor de chat persistente.

        
        </div>
    
    5.  Para controlar o histórico de chats, marque ou desmarque a caixa de seleção **habilitar histórico de chats** . Se marcada, as salas de chat se tornam persistentes; caso contrário, as mensagens de chat não são persistentes. Se a conformidade estiver habilitada, as salas de chat serão salvas em conformidade, mas os usuários não poderão acessar mensagens antigas. Essa opção pode ser utilizada para salas designadas para colaborações em tempo real e ad hoc que não precisam do histórico de chat persistente.

7.  Em  **Editar categoria**, faça o seguinte:
    
      - Em **Associação**, na seção **Membros permitidos** , adicione ou remova usuários e outros princípios de serviços de domínio do Active Directory (usuários, grupos de distribuição, unidades organizacionais e assim por diante) que podem ser adicionados como membros de salas de chat pertencente à categoria. As entidades permitidas por uma categoria podem pesquisar por salas na categoria (a menos que uma sala esteja oculta, caso o qual apenas membros da sala podem pesquisar por ela no diretório).
    
      - Em **Associação**, na seção **Membros negados** , adicione ou remova usuários e outras entidades de segurança do Active Directory associadas a membros sendo negados da sala.
    
      - Em **Associação**, na seção **criadores** , adicione ou remova usuários e outras entidades de segurança do Active Directory associadas aos criadores para a categoria. Um criador é um usuário que tem permissões de criar salas de chat e atribuir gerentes e membros de sala de chat.

8.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

