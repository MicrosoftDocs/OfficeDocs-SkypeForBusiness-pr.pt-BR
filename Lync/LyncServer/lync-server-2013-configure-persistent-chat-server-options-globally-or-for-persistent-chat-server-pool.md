---
title: 'Lync Server 2013: Configurar opções do Servidor de Chat Persistente globalmente ou para pool do Servidor de Chat Persistente'
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
ms.openlocfilehash: 86ee77dd34e3a43ea62ac6cffaf4af952b1c447e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a>Configurar opções do Servidor de Chat Persistente globalmente ou para pool do Servidor de Chat Persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-06_

No painel de controle do Lync Server 2013, você pode usar a seção **configuração de chat persistente** da página de **chat persistente** para definir configurações de chat persistente globalmente, onde ela se aplica a todos os pools de servidores de chat persistentes, ou para um pool de servidor de chat persistente específico.

<div>


> [!NOTE]  
> Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar suporte a servidor de chat persistente à topologia e, em seguida, publicar a topologia. Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a>Para configurar as opções de chat persistente globalmente

1.  A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.

2.  No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e, em seguida, insira a URL de administração. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Você também pode usar cmdlets do Windows PowerShell. Para obter detalhes, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.

    
    </div>

3.  Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Configuração do Chat Persistente**.

4.  Na página **configuração de chat persistente** , clique em **novo** e, em seguida, clique em **configuração do site**.
    
    <div>
    

    > [!IMPORTANT]  
    > Escolha esta opção se quiser que a configuração seja aplicada a todos os pools de servidores de chat persistentes implantados no site. Clique em <STRONG>configuração de pool</STRONG> se desejar que a configuração seja aplicada a um pool específico do servidor de chat persistente.

    
    </div>

5.  Em **selecionar um site**, selecione o site a ser configurado para a configuração de site do servidor de chat persistente.

6.  Em **Nova Configuração de Chat Persistente**, siga este procedimento:
    
      - Em **Nome**, especifique um nome para a nova configuração. Por padrão, o nome do site já existe.
    
      - Em **Histórico de chat padrão**, defina o número de mensagens de chat que serão processadas para cada sala após a primeira solicitação. Por padrão, esse número é 30. Esse é o padrão global, e os administradores podem desabilitar o histórico de chat por categoria.
        
        <div>
        

        > [!IMPORTANT]  
        > O servidor de chat persistente armazenará essas mensagens em cache na memória, portanto, se você aumentar esse número, mais mensagens serão armazenadas em cache. Você sempre pode acessar o conteúdo histórico por meio da pesquisa. O número padrão simplesmente determina o número máximo de mensagens que você vê inicialmente ao conectar-se a uma sala de chat.

        
        </div>
    
      - Em **Tamanho máximo do arquivo (KB)**, selecione o tamanho máximo de arquivo de cada histórico de chat. Por padrão, o número é 20 MB (20.000 KB). Esse é o tamanho máximo de arquivo que pode ser carregado em qualquer sala de chat no sistema (para a qual os carregamentos de arquivo estão habilitados pela configuração de **Categoria** correspondente).
        
        <div>
        

        > [!IMPORTANT]  
        > Essa configuração é imposta no servidor porque aplicativos personalizados ou clientes de chat em grupo anterior que usam o servidor de chat de&nbsp;grupo do Office Communications Server 2007 R2 ou o Lync Server 2010, o chat em grupo podem postar arquivos para uma sala. O cliente do Lync 2013 não tem recurso de carregamento/download de arquivo, portanto, se você tiver uma implantação do Lync 2013 ou do Lync 2013, não será possível postar arquivos em uma sala de chat do servidor de chat persistente.

        
        </div>
    
      - Em **Limite de atualizações do participante**, selecione o limite para atualizações de participantes. O servidor de chat persistente envia informações da lista (quem está conectado a uma sala de chat) a todos os participantes até que o número de usuários conectados atinja esse número. Por padrão, o número é 75. Esse limite indica o número máximo de participantes em uma determinada sala além da qual o servidor de chat persistente interrompe o envio de atualizações da lista para clientes conectados sobre quem está presente na sala.
    
      - (Opcional.) Em **URL de gerenciamento de salas**, selecione a URL de gerenciamento de salas. Essa é a URL para o gerenciamento personalizado de salas baseado na Web. Se você não precisar personalizar o gerenciamento e usar apenas a configuração padrão, deixe essa opção em branco. Uma vez definida a URL, ela será aplicada como a URL interna e externa de gerenciamento de salas.
        
        Se você quiser personalizar a experiência de criação da sala e incluir seu fluxo de trabalho de negócios específico, poderá criar uma solução de gerenciamento de sala personalizada usando o SDK (Kit de desenvolvimento de software) do servidor de chat persistente, hospedá-lo em algum lugar e colocar a URL aqui. Essa URL será enviada para o cliente de modo que, quando um usuário tentar exibir ou criar uma sala, ele será direcionado para sua solução personalizada de gerenciamento de salas.

7.  Clique em **Confirmar**.

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Para configurar opções de chat persistente para um pool de servidor de chat persistente específico

1.  A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.

2.  No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e, em seguida, insira a URL de administração. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Você também pode usar cmdlets do Windows PowerShell. Para obter detalhes, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.

    
    </div>

3.  Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Configuração do Chat Persistente**.

4.  Na página **Configuração do Chat Persistente**, clique em **Novo** e, em seguida, clique em **Configuração do pool**.

5.  Em **selecionar um serviço**, selecione o serviço associado ao pool de servidores de chat persistente a ser configurado.

6.  Em **Nova Configuração de Chat Persistente**, siga este procedimento:
    
      - Em **Nome**, especifique um nome para a nova configuração. Por padrão, o nome do pool do site já existe.
    
      - Em **Histórico de chat padrão**, defina o número de mensagens de chat que serão processadas para cada sala após a primeira solicitação. Por padrão, esse número é 30. Esse é o padrão global, e os administradores podem desabilitar o histórico de chat por categoria.
        
        <div>
        

        > [!IMPORTANT]  
        > O servidor de chat persistente armazenará essas mensagens em cache na memória, portanto, se você aumentar esse número, mais mensagens serão armazenadas em cache. Você sempre pode acessar o conteúdo histórico por meio da pesquisa. O número padrão simplesmente determina o número máximo de mensagens que você vê inicialmente ao conectar-se a uma sala de chat.

        
        </div>
    
      - Em **Tamanho máximo do arquivo (KB)**, selecione o tamanho máximo de arquivo de cada histórico de chat. Por padrão, o número é 20 MB (20.000 KB). Esse é o tamanho máximo de arquivo que pode ser carregado em qualquer sala de chat no sistema (para a qual os carregamentos de arquivo estão habilitados pela configuração de **Categoria** correspondente).
        
        <div>
        

        > [!IMPORTANT]  
        > Essa configuração é imposta no servidor porque aplicativos personalizados ou clientes de chat em grupo anterior (servidor de chat de grupo do&nbsp;Office Communications Server 2007 R2 ou Lync Server 2010, chat em grupo) podem postar arquivos para uma sala. O cliente do Lync 2013 não tem recurso de carregamento/download de arquivo, portanto, se você tiver uma implantação do Lync 2013 ou do Lync 2013, não será possível postar arquivos em uma sala de chat do servidor de chat persistente.

        
        </div>
    
      - Em **Limite de atualizações do participante**, selecione o limite para atualizações de participantes. O servidor de chat persistente envia informações da lista (quem está conectado a uma sala de chat) a todos os participantes até que o número de usuários conectados atinja esse número. Por padrão, o número é 75. Esse limite indica o número máximo de participantes em uma determinada sala além da qual o servidor de chat persistente interrompe o envio de atualizações da lista para clientes conectados sobre quem está presente na sala.
    
      - Em **URL de gerenciamento de salas**, selecione a URL de gerenciamento de salas. Essa é a URL para uma implantação de gerenciamento de salas baseado na Web. Se você não precisar personalizar o gerenciamento e usar apenas a configuração padrão, deixe essa opção em branco.
        
        Se você quiser personalizar a experiência de criação da sala e incluir seu fluxo de trabalho de negócios específico, poderá criar uma solução de gerenciamento de sala personalizada usando o SDK (Kit de desenvolvimento de software) do servidor de chat persistente, hospedá-lo em algum lugar e colocar a URL aqui. Essa URL será enviada para o cliente de modo que, quando um usuário tentar exibir ou criar uma sala, ele será direcionado para sua solução personalizada de gerenciamento de salas.

7.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

