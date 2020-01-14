---
title: 'Lync Server 2013: Configurar opções do Servidor de Chat Persistente globalmente ou para pool do Servidor de Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fedd0d1adb4149c3dc2ea41c5321259f571524f
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a><span data-ttu-id="41e87-102">Configurar opções do Servidor de Chat Persistente globalmente ou para pool do Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41e87-102">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41e87-103">_**Tópico da última modificação:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="41e87-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="41e87-104">No painel de controle do Lync Server 2013, você pode usar a seção **configuração de chat persistente** da página de **chat persistente** para definir configurações de chat persistente globalmente, onde ela se aplica a todos os pools de servidores de chat persistentes, ou para um pool de servidor de chat persistente específico.</span><span class="sxs-lookup"><span data-stu-id="41e87-104">In Lync Server 2013 Control Panel, you can use the **Persistent Chat Configuration** section of the **Persistent Chat** page to configure Persistent Chat settings globally where it applies to all Persistent Chat Server pools, or for a specific Persistent Chat Server pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41e87-105">Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar suporte a servidor de chat persistente à topologia e, em seguida, publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="41e87-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="41e87-106">Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="41e87-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="41e87-107">Para configurar as opções de chat persistente globalmente</span><span class="sxs-lookup"><span data-stu-id="41e87-107">To configure Persistent Chat options globally</span></span>

1.  <span data-ttu-id="41e87-108">A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.</span><span class="sxs-lookup"><span data-stu-id="41e87-108">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="41e87-109">No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.</span><span class="sxs-lookup"><span data-stu-id="41e87-109">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="41e87-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="41e87-110">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="41e87-111">Você também pode usar cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41e87-111">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="41e87-112">Para obter detalhes, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="41e87-112">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="41e87-113">Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Configuração do Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="41e87-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="41e87-114">Na página **configuração de chat persistente** , clique em **novo** e, em seguida, clique em **configuração do site**.</span><span class="sxs-lookup"><span data-stu-id="41e87-114">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="41e87-115">Escolha esta opção se quiser que a configuração seja aplicada a todos os pools de servidores de chat persistentes implantados no site.</span><span class="sxs-lookup"><span data-stu-id="41e87-115">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="41e87-116">Clique em <STRONG>configuração de pool</STRONG> se desejar que a configuração seja aplicada a um pool específico do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="41e87-116">Click <STRONG>Pool Configuration</STRONG> if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>

    
    </div>

5.  <span data-ttu-id="41e87-117">Em **selecionar um site**, selecione o site a ser configurado para a configuração de site do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="41e87-117">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>

6.  <span data-ttu-id="41e87-118">Em **Nova Configuração de Chat Persistente**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="41e87-118">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="41e87-p105">Em **Nome**, especifique um nome para a nova configuração. Por padrão, o nome do site já existe.</span><span class="sxs-lookup"><span data-stu-id="41e87-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
      - <span data-ttu-id="41e87-p106">Em **Histórico de chat padrão**, defina o número de mensagens de chat que serão processadas para cada sala após a primeira solicitação. Por padrão, esse número é 30. Esse é o padrão global, e os administradores podem desabilitar o histórico de chat por categoria.</span><span class="sxs-lookup"><span data-stu-id="41e87-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="41e87-124">O servidor de chat persistente armazenará essas mensagens em cache na memória, portanto, se você aumentar esse número, mais mensagens serão armazenadas em cache.</span><span class="sxs-lookup"><span data-stu-id="41e87-124">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="41e87-125">Você sempre pode acessar o conteúdo histórico por meio da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="41e87-125">You can always access historical content by search.</span></span> <span data-ttu-id="41e87-126">O número padrão simplesmente determina o número máximo de mensagens que você vê inicialmente ao conectar-se a uma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="41e87-126">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="41e87-p108">Em **Tamanho máximo do arquivo (KB)**, selecione o tamanho máximo de arquivo de cada histórico de chat. Por padrão, o número é 20 MB (20.000 KB). Esse é o tamanho máximo de arquivo que pode ser carregado em qualquer sala de chat no sistema (para a qual os carregamentos de arquivo estão habilitados pela configuração de **Categoria** correspondente).</span><span class="sxs-lookup"><span data-stu-id="41e87-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="41e87-130">Essa configuração é imposta no servidor porque aplicativos personalizados ou clientes de chat em grupo anterior que usam o servidor de chat de&nbsp;grupo do Office Communications Server 2007 R2 ou o Lync Server 2010, o chat em grupo podem postar arquivos para uma sala.</span><span class="sxs-lookup"><span data-stu-id="41e87-130">This setting is enforced on the server because custom applications or previous Group Chat clients using Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="41e87-131">O cliente do Lync 2013 não tem recurso de carregamento/download de arquivo, portanto, se você tiver uma implantação do Lync 2013 ou do Lync 2013, não será possível postar arquivos em uma sala de chat do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="41e87-131">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="41e87-132">Em **Limite de atualizações do participante**, selecione o limite para atualizações de participantes.</span><span class="sxs-lookup"><span data-stu-id="41e87-132">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="41e87-133">O servidor de chat persistente envia informações da lista (quem está conectado a uma sala de chat) a todos os participantes até que o número de usuários conectados atinja esse número.</span><span class="sxs-lookup"><span data-stu-id="41e87-133">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="41e87-134">Por padrão, o número é 75.</span><span class="sxs-lookup"><span data-stu-id="41e87-134">By default, the number is 75.</span></span> <span data-ttu-id="41e87-135">Esse limite indica o número máximo de participantes em uma determinada sala além da qual o servidor de chat persistente interrompe o envio de atualizações da lista para clientes conectados sobre quem está presente na sala.</span><span class="sxs-lookup"><span data-stu-id="41e87-135">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="41e87-p111">(Opcional.) Em **URL de gerenciamento de salas**, selecione a URL de gerenciamento de salas. Essa é a URL para o gerenciamento personalizado de salas baseado na Web. Se você não precisar personalizar o gerenciamento e usar apenas a configuração padrão, deixe essa opção em branco. Uma vez definida a URL, ela será aplicada como a URL interna e externa de gerenciamento de salas.</span><span class="sxs-lookup"><span data-stu-id="41e87-p111">(Optional.) In **Room management URL**, select the room management URL. This is the URL for a web-based custom room management. If you don’t need to customize room management, and you simply use the default setting, leave this option blank. After the URL is set, it is applied as both the internal and external room management URL.</span></span>
        
        <span data-ttu-id="41e87-140">Se você quiser personalizar a experiência de criação da sala e incluir seu fluxo de trabalho de negócios específico, poderá criar uma solução de gerenciamento de sala personalizada usando o SDK (Kit de desenvolvimento de software) do servidor de chat persistente, hospedá-lo em algum lugar e colocar a URL aqui.</span><span class="sxs-lookup"><span data-stu-id="41e87-140">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="41e87-141">Essa URL será enviada para o cliente de modo que, quando um usuário tentar exibir ou criar uma sala, ele será direcionado para sua solução personalizada de gerenciamento de salas.</span><span class="sxs-lookup"><span data-stu-id="41e87-141">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="41e87-142">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="41e87-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="41e87-143">Para configurar opções de chat persistente para um pool de servidor de chat persistente específico</span><span class="sxs-lookup"><span data-stu-id="41e87-143">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1.  <span data-ttu-id="41e87-144">A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.</span><span class="sxs-lookup"><span data-stu-id="41e87-144">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="41e87-145">No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.</span><span class="sxs-lookup"><span data-stu-id="41e87-145">From the **Start** menu, select the Lync Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="41e87-146">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="41e87-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="41e87-147">Você também pode usar cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41e87-147">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="41e87-148">Para obter detalhes, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="41e87-148">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="41e87-149">Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Configuração do Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="41e87-149">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>

4.  <span data-ttu-id="41e87-150">Na página **Configuração do Chat Persistente**, clique em **Novo** e, em seguida, clique em **Configuração do pool**.</span><span class="sxs-lookup"><span data-stu-id="41e87-150">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>

5.  <span data-ttu-id="41e87-151">Em **selecionar um serviço**, selecione o serviço associado ao pool de servidores de chat persistente a ser configurado.</span><span class="sxs-lookup"><span data-stu-id="41e87-151">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>

6.  <span data-ttu-id="41e87-152">Em **Nova Configuração de Chat Persistente**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="41e87-152">In **New Persistent Chat Configuration**, do the following:</span></span>
    
      - <span data-ttu-id="41e87-p115">Em **Nome**, especifique um nome para a nova configuração. Por padrão, o nome do pool do site já existe.</span><span class="sxs-lookup"><span data-stu-id="41e87-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
      - <span data-ttu-id="41e87-p116">Em **Histórico de chat padrão**, defina o número de mensagens de chat que serão processadas para cada sala após a primeira solicitação. Por padrão, esse número é 30. Esse é o padrão global, e os administradores podem desabilitar o histórico de chat por categoria.</span><span class="sxs-lookup"><span data-stu-id="41e87-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="41e87-158">O servidor de chat persistente armazenará essas mensagens em cache na memória, portanto, se você aumentar esse número, mais mensagens serão armazenadas em cache.</span><span class="sxs-lookup"><span data-stu-id="41e87-158">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="41e87-159">Você sempre pode acessar o conteúdo histórico por meio da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="41e87-159">You can always access historical content by search.</span></span> <span data-ttu-id="41e87-160">O número padrão simplesmente determina o número máximo de mensagens que você vê inicialmente ao conectar-se a uma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="41e87-160">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="41e87-p118">Em **Tamanho máximo do arquivo (KB)**, selecione o tamanho máximo de arquivo de cada histórico de chat. Por padrão, o número é 20 MB (20.000 KB). Esse é o tamanho máximo de arquivo que pode ser carregado em qualquer sala de chat no sistema (para a qual os carregamentos de arquivo estão habilitados pela configuração de **Categoria** correspondente).</span><span class="sxs-lookup"><span data-stu-id="41e87-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="41e87-164">Essa configuração é imposta no servidor porque aplicativos personalizados ou clientes de chat em grupo anterior (servidor de chat de grupo do&nbsp;Office Communications Server 2007 R2 ou Lync Server 2010, chat em grupo) podem postar arquivos para uma sala.</span><span class="sxs-lookup"><span data-stu-id="41e87-164">This setting is enforced on the server because custom applications or previous Group Chat clients (Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat) can post files to a room.</span></span> <span data-ttu-id="41e87-165">O cliente do Lync 2013 não tem recurso de carregamento/download de arquivo, portanto, se você tiver uma implantação do Lync 2013 ou do Lync 2013, não será possível postar arquivos em uma sala de chat do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="41e87-165">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
      - <span data-ttu-id="41e87-166">Em **Limite de atualizações do participante**, selecione o limite para atualizações de participantes.</span><span class="sxs-lookup"><span data-stu-id="41e87-166">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="41e87-167">O servidor de chat persistente envia informações da lista (quem está conectado a uma sala de chat) a todos os participantes até que o número de usuários conectados atinja esse número.</span><span class="sxs-lookup"><span data-stu-id="41e87-167">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="41e87-168">Por padrão, o número é 75.</span><span class="sxs-lookup"><span data-stu-id="41e87-168">By default, the number is 75.</span></span> <span data-ttu-id="41e87-169">Esse limite indica o número máximo de participantes em uma determinada sala além da qual o servidor de chat persistente interrompe o envio de atualizações da lista para clientes conectados sobre quem está presente na sala.</span><span class="sxs-lookup"><span data-stu-id="41e87-169">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
      - <span data-ttu-id="41e87-p121">Em **URL de gerenciamento de salas**, selecione a URL de gerenciamento de salas. Essa é a URL para uma implantação de gerenciamento de salas baseado na Web. Se você não precisar personalizar o gerenciamento e usar apenas a configuração padrão, deixe essa opção em branco.</span><span class="sxs-lookup"><span data-stu-id="41e87-p121">In **Room management URL**, select the room management URL. This is the URL for a web-based room management deployment. If you don’t need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
        
        <span data-ttu-id="41e87-173">Se você quiser personalizar a experiência de criação da sala e incluir seu fluxo de trabalho de negócios específico, poderá criar uma solução de gerenciamento de sala personalizada usando o SDK (Kit de desenvolvimento de software) do servidor de chat persistente, hospedá-lo em algum lugar e colocar a URL aqui.</span><span class="sxs-lookup"><span data-stu-id="41e87-173">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="41e87-174">Essa URL será enviada para o cliente de modo que, quando um usuário tentar exibir ou criar uma sala, ele será direcionado para sua solução personalizada de gerenciamento de salas.</span><span class="sxs-lookup"><span data-stu-id="41e87-174">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>

7.  <span data-ttu-id="41e87-175">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="41e87-175">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

