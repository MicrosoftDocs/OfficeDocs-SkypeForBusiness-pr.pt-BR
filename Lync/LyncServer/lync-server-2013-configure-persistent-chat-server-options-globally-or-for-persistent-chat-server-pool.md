---
title: 'Lync Server 2013: configurar opções de servidor de chat persistente globalmente ou para pool de servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a9cadd23099dbcaee5c577705ca1c2e4bdf6c00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520458"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a>Configurar opções do servidor de chat persistente globalmente ou para pool de servidor de chat persistente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-06_

No painel de controle do Lync Server 2013, você pode usar a seção **configuração de chat persistente** da página **chat persistente** para definir as configurações de chat persistente globalmente, onde ela se aplica a todos os pools de servidores de chat persistente ou para um pool de servidor de chat persistente específico.

<div>


> [!NOTE]  
> Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar o suporte do servidor de chat persistente à topologia e, em seguida, publicar a topologia. Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a>Para configurar opções de chat persistente globalmente

1.  A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e insira a URL do administrador. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Você também pode usar os cmdlets do Windows PowerShell. Para obter detalhes, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.

    
    </div>

3.  Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Configuração de Chat Persistente**.

4.  Na página **configuração do chat persistente** , clique em **novo** e em **configuração do site**.
    
    <div>
    

    > [!IMPORTANT]  
    > Escolha essa opção se quiser que a configuração seja aplicada a todos os pools do servidor de chat persistente implantados no site. Clique em <STRONG>configuração do pool</STRONG> se quiser que a configuração seja aplicada a um pool de servidor de chat persistente específico.

    
    </div>

5.  Em **selecionar um site**, selecione o site a ser configurado para a configuração de site do servidor de chat persistente.

6.  Em **Nova Configuração de Chat Persistente**, faça o seguinte:
    
      - Em **Nome**, especifique um nome para a nova configuração. Por padrão, o nome do site já existe.
    
      - Em **Histórico de chat padrão**, defina o número de mensagens do chat que serão processadas para cada sala na primeira solicitação. Por padrão, o número é 30. Esse é o padrão global, e os administradores podem desabilitar o histórico de chat por categoria.
        
        <div>
        

        > [!IMPORTANT]  
        > O servidor de chat persistente armazenará em cache essas mensagens na memória, portanto, se você aumentar esse número, mais mensagens serão armazenadas em cache. Sempre é possível acessar conteúdo histórico por meio da pesquisa. O número padrão simplesmente determina o número máximo de mensagens que você vê inicialmente ao se conectar a uma sala de chat.

        
        </div>
    
      - Em **Tamanho máximo do arquivo (KB)**, selecione o tamanho máximo do arquivo de cada histórico de chat. Por padrão, o número é 20 MB (20.000 KB). Esse é o tamanho máximo para um arquivo que pode ser carregado em qualquer sala de chat no sistema (para a qual o carregamento de arquivos é habilitado por sua configuração correspondente de **Categoria**).
        
        <div>
        

        > [!IMPORTANT]  
        > Essa configuração é imposta no servidor porque aplicativos personalizados ou clientes de chat de grupo anterior usando o servidor de chat de grupo do Office Communications Server 2007 R2 &nbsp; ou o Lync server 2010, o chat de grupo podem postar arquivos para uma sala. O cliente Lync 2013 não tem o recurso de carregamento/download de arquivos, portanto, se você tiver uma implantação pura do Lync 2013 ou um cliente do Lync 2013, não será possível postar arquivos em uma sala de chat do servidor de chat persistente.

        
        </div>
    
      - Em **Limite de atualização de participantes**, selecione o limite de atualizações de participantes. Servidor de chat persistente envia informações de lista (quem está conectado a uma sala de chat) para todos os participantes até que o número de usuários conectados atinja esse número. Por padrão, o número é 75. Este limite indica o número máximo de participantes em uma determinada sala além da qual o servidor de chat persistente interrompe o envio de atualizações de lista para clientes conectados sobre quem está presente na sala.
    
      - (Opcional). Em **URL de Gerenciamento da Sala**, selecione a URL de gerenciamento de sala. Essa é a URL para um gerenciamento de sala personalizada baseada na Web. Se não for necessário personalizar o gerenciamento da sala, e você simplesmente usar a configuração padrão, deixe essa opção em branco. Após a URL ser definida, ela é aplicada como URL de gerenciamento de sala interna e externa.
        
        Se quiser personalizar sua experiência de criação de sala e incluir seu fluxo de trabalho de negócios específico, você pode criar uma solução de gerenciamento de sala personalizada usando o SDK (Software Development Kit) do servidor de chat persistente, hospedá-lo em algum lugar e colocar a URL aqui. Essa URL é enviada para o cliente de modo que quando um usuário tenta exibir ou criar uma sala, ele ou ela é direcionado à sua solução de gerenciamento de sala personalizada.

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Para configurar opções de chat persistente para um pool de servidor de chat persistente específico

1.  A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e insira a URL do administrador. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Você também pode usar os cmdlets do Windows PowerShell. Para obter detalhes, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.

    
    </div>

3.  Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Configuração de Chat Persistente**.

4.  Na página **Configuração de Chat Persistente**, clique em **Novo** e clique em **Configuração de pool**.

5.  Em **selecionar um serviço**, selecione o serviço associado ao pool do servidor de chat persistente a ser configurado.

6.  Em **Nova Configuração de Chat Persistente**, faça o seguinte:
    
      - Em **Nome**, especifique um nome para a nova configuração. Por padrão, o nome do pool de sites já existe.
    
      - Em **Histórico de chat padrão**, defina o número de mensagens do chat que serão processadas para cada sala na primeira solicitação. Por padrão, o número é 30. Esse é o padrão global, e os administradores podem desabilitar o histórico de chat por categoria.
        
        <div>
        

        > [!IMPORTANT]  
        > O servidor de chat persistente armazenará em cache essas mensagens na memória, portanto, se você aumentar esse número, mais mensagens serão armazenadas em cache. Sempre é possível acessar conteúdo histórico por meio da pesquisa. O número padrão simplesmente determina o número máximo de mensagens que você vê inicialmente ao se conectar a uma sala de chat.

        
        </div>
    
      - Em **Tamanho máximo do arquivo (KB)**, selecione o tamanho máximo do arquivo de cada histórico de chat. Por padrão, o número é 20 MB (20.000 KB). Esse é o tamanho máximo para um arquivo que pode ser carregado em qualquer sala de chat no sistema (para a qual o carregamento de arquivos é habilitado por sua configuração correspondente de **Categoria**).
        
        <div>
        

        > [!IMPORTANT]  
        > Essa configuração é imposta no servidor porque os aplicativos personalizados ou os clientes de chat de grupo anterior (Office Communications Server 2007 R2 &nbsp; Group Chat Server ou o Lync server 2010, o chat de grupo) podem postar arquivos a uma sala. O cliente Lync 2013 não tem o recurso de carregamento/download de arquivos, portanto, se você tiver uma implantação pura do Lync 2013 ou um cliente do Lync 2013, não será possível postar arquivos em uma sala de chat do servidor de chat persistente.

        
        </div>
    
      - Em **Limite de atualização de participantes**, selecione o limite de atualizações de participantes. Servidor de chat persistente envia informações de lista (quem está conectado a uma sala de chat) para todos os participantes até que o número de usuários conectados atinja esse número. Por padrão, o número é 75. Este limite indica o número máximo de participantes em uma determinada sala além da qual o servidor de chat persistente interrompe o envio de atualizações de lista para clientes conectados sobre quem está presente na sala.
    
      - Em **URL de gerenciamento da sala**, selecione a URL de gerenciamento da sala. Esta é a URL para uma implantação de gerenciamento de sala baseado na Web. Se você não precisa personalizar um gerenciamento de sala e apenas usa a configuração padrão, deixe esta opção em branco.
        
        Se quiser personalizar sua experiência de criação de sala e incluir seu fluxo de trabalho de negócios específico, você pode criar uma solução de gerenciamento de sala personalizada usando o SDK (Software Development Kit) do servidor de chat persistente, hospedá-lo em algum lugar e colocar a URL aqui. Esta URL é enviada para o cliente para que quando um usuário tentar exibir/criar uma sala, ele ou ela seja direcionado para sua solução de gerenciamento de sala personalizada.

7.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

