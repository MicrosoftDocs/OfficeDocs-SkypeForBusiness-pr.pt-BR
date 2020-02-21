---
title: 'Lync Server 2013: configurar categorias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb70397514589ac6f3cc74d84a6ae7509c9baa5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-categories-in-lync-server-2013"></a>Configurar categorias no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-06_

No painel de controle do Lync Server 2013, você pode usar a seção **categoria** da página **chat persistente** para configurar categorias. Uma categoria de sala de chat persistente é uma estrutura lógica para organizar as salas de chat. Uma categoria define um conjunto padrão de listas de controle de acesso (ACLs) para controle dos usuários e dos grupos de usuários que podem criar ou ingressar em salas de chat. É possível usar as categorias para aplicar paredes éticas entre diferentes subdivisões dentro de suas organizações.

As categorias de sala de chat podem conter salas de chat, mas nenhuma outra categoria. Cada categoria descreve seu conteúdo com metadados, como Nome e Descrição. Além disso, a categoria possui propriedades as quais podem ser definidas para controlar o comportamento das salas de bate-papo pertencentes, como se as salas de bate-papo permitissem Convites ou Envio de arquivo ou contém Histórico de bate-papo.

<div>

## <a name="to-configure-categories-for-chat-rooms"></a>Para configurar as categorias para salas de chat

1.  A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e insira a URL do administrador. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Você também pode usar os cmdlets do Windows PowerShell. Para obter detalhes, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.

    
    </div>

3.  Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Categoria**.
    
    Para várias implantações de pool do servidor de chat persistente, selecione o pool apropriado na lista suspensa.

4.  Na página **Categoria**, clique em **Novo** ou **Editar**.

5.  Em **selecionar um serviço**, selecione o serviço correspondente ao pool do servidor de chat persistente no qual a categoria precisa ser criada. O serviço é o pool do servidor de chat persistente que usa o chat persistente (cliente) para identificar a qual pool a categoria pertence. Uma categoria pode pertencer apenas a um pool de servidores de chat persistente e não pode ser movida para outra ou compartilhada com outro pool.

6.  Em **Nova Categoria**, faça o seguinte:
    
    1.  Em **Nome**, especifique um nome para a nova categoria de sala.
    
    2.  Em **Descrição**, forneça uma descrição detalhada da categoria de sala (por exemplo, uma categoria de sala para Contoso).
    
    3.  Para controlar se os convites podem ser habilitados para salas de chat que pertencem a essa categoria, marque ou desmarque a caixa de seleção **Habilitar convites**. Se for marcada, as salas nessa categoria poderão ter os convites ativados ou desativados; se for desmarcada, as salas nessa categoria não terão permissão para enviar convites. Se uma sala tiver convites em, quando um novo membro for adicionado a uma sala, ele receberá uma notificação da nova sala em seu cliente de chat persistente.
    
    4.  Para controlar os carregamentos de arquivo nas salas de chat que pertencem a essa categoria, marque ou desmarque a caixa de seleção **Habilitar carregamento de arquivo**. Se for marcada, as salas dessa categoria poderão habilitar ou desabilitar os carregamentos de arquivo; se for desmarcada, as salas dessa categoria não terão permissão para carregamentos de arquivo.
        
        <div>
        

        > [!IMPORTANT]  
        > Essa configuração é imposta no servidor porque aplicativos personalizados ou clientes de chat de grupo anterior que usam o servidor de chat de grupo&nbsp;do Office Communications Server 2007 R2 ou o Lync Server 2010, o chat de grupo podem postar arquivos para uma sala. O cliente Lync 2013 não tem o recurso de carregamento/download de arquivos, portanto, se você tiver uma implantação pura do Lync 2013 ou um cliente do Lync 2013, não será possível postar arquivos em uma sala de chat do servidor de chat persistente.

        
        </div>
    
    5.  Para controlar o histórico do chat, marque ou desmarque a caixa de seleção **habilitar histórico de chat** . Se for marcada, as salas de chats se tornarão persistentes; caso contrário, as mensagens de chat não serão persistentes. Se a conformidade for habilitada, salas de chats serão salvas em conformidade, mas os usuários não poderão acessar mensagens mais antigas. Essa opção pode ser usada para salas designadas para colaboração em tempo real e ad hoc que não precisam de persistência do histórico de chat.

7.  Em **Editar Categoria**, faça o seguinte:
    
      - Em **Associação**, na seção **Membros permitidos** , adicione ou remova usuários e outras entidades de segurança de serviços de domínio do Active Directory (usuários, grupos de distribuição, unidades organizacionais e assim por diante) que podem ser adicionados como membros de salas de chat pertencentes à categoria. As entidades permitidas por uma categoria podem pesquisar por salas na categoria (a menos que uma sala esteja oculta, caso o qual apenas membros da sala podem pesquisar por ela no diretório).
    
      - Em **Associação**, na seção **Membros negados** , adicione ou remova usuários e outras entidades de segurança do Active Directory associadas aos membros sendo negados da sala.
    
      - Em **Associação**, na seção **criadores** , adicione ou remova usuários e outras entidades de segurança do Active Directory associadas aos criadores para a categoria. Um criador é um usuário com permissões para criar salas de chat e atribuir gerentes e membros de sala de chat.

8.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

