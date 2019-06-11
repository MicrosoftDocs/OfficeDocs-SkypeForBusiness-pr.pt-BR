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

# <a name="configure-categories-in-lync-server-2013"></a><span data-ttu-id="e83f9-102">Configurar categorias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e83f9-102">Configure categories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e83f9-103">_**Tópico da última modificação:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e83f9-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e83f9-104">No painel de controle do Lync Server 2013, você pode usar a seção **categoria** da página de **chat persistente** para configurar categorias.</span><span class="sxs-lookup"><span data-stu-id="e83f9-104">In Lync Server 2013 Control Panel, you can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="e83f9-105">Uma categoria de sala de chat persistente é uma estrutura lógica para organizar salas de chat.</span><span class="sxs-lookup"><span data-stu-id="e83f9-105">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="e83f9-106">Uma categoria define um conjunto padrão de listas de controle de acesso (ACLs) para controle dos usuários e dos grupos de usuários que podem criar ou ingressar em salas de chat.</span><span class="sxs-lookup"><span data-stu-id="e83f9-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="e83f9-107">É possível usar as categorias para aplicar paredes éticas entre diferentes subdivisões dentro de suas organizações.</span><span class="sxs-lookup"><span data-stu-id="e83f9-107">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>

<span data-ttu-id="e83f9-108">As categorias de sala de chat podem conter salas de chat, mas nenhuma outra categoria.</span><span class="sxs-lookup"><span data-stu-id="e83f9-108">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="e83f9-109">Cada categoria descreve o conteúdo com metadados, como Name e Description.</span><span class="sxs-lookup"><span data-stu-id="e83f9-109">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="e83f9-110">Além disso, a categoria tem propriedades as quais podem ser definidas para controlar o comportamento das salas de bate-papo pertencentes, como se as salas de chat permitissem  Invitations ou File Uploads ou contivessem Chat History.</span><span class="sxs-lookup"><span data-stu-id="e83f9-110">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span>

<div>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="e83f9-111">Para configurar categorias salas de bate-papo</span><span class="sxs-lookup"><span data-stu-id="e83f9-111">To configure categories for chat rooms</span></span>

1.  <span data-ttu-id="e83f9-112">A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.</span><span class="sxs-lookup"><span data-stu-id="e83f9-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e83f9-113">No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.</span><span class="sxs-lookup"><span data-stu-id="e83f9-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="e83f9-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e83f9-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e83f9-115">Você também pode usar cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e83f9-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="e83f9-116">Para obter detalhes, consulte Configurando o <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="e83f9-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="e83f9-117">Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Categoria**.</span><span class="sxs-lookup"><span data-stu-id="e83f9-117">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="e83f9-118">Para várias implantações de pool do servidor de chat persistente, selecione o pool apropriado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="e83f9-118">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="e83f9-119">Na página **Categoria**, clique em **Novo** ou **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e83f9-119">On the **Category** page, click **New** or **Edit**.</span></span>

5.  <span data-ttu-id="e83f9-120">Em **selecionar um serviço**, selecione o serviço correspondente ao pool de servidores de chat persistente em que a categoria precisa ser criada.</span><span class="sxs-lookup"><span data-stu-id="e83f9-120">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="e83f9-121">O serviço é o pool persistente do servidor de chat que o chat (cliente) persistente usa para identificar a qual pool a categoria pertence.</span><span class="sxs-lookup"><span data-stu-id="e83f9-121">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="e83f9-122">Uma categoria pode pertencer a apenas um pool de servidor de chat persistente e não pode ser movida para outra ou compartilhada com outro pool.</span><span class="sxs-lookup"><span data-stu-id="e83f9-122">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

6.  <span data-ttu-id="e83f9-123">Em **Nova categoria**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e83f9-123">In **New Category**, do the following:</span></span>
    
    1.  <span data-ttu-id="e83f9-124">Em  **Nome**, especifique um nome para a nova categoria de sala.</span><span class="sxs-lookup"><span data-stu-id="e83f9-124">In **Name**, specify a name for the new room category.</span></span>
    
    2.  <span data-ttu-id="e83f9-125">Em  **Descrição**, forneça uma descrição detalhada para a categoria da sala (por exemplo, uma categoria de sala para Contoso).</span><span class="sxs-lookup"><span data-stu-id="e83f9-125">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
    3.  <span data-ttu-id="e83f9-126">Para controlar se os convites podem ser ativados por salas de chat que pertencem a tal categoria, selecione ou limpe a caixa de marcação **Habilitar convites**.</span><span class="sxs-lookup"><span data-stu-id="e83f9-126">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="e83f9-127">Se marcado, as salas nesta categoria poderão ter convites ativados ou desativados; em caso de não marcado, as salas nessa categoria não podem ter convite.</span><span class="sxs-lookup"><span data-stu-id="e83f9-127">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="e83f9-128">Se uma sala tem convites em, quando um novo membro é adicionado a uma sala, ele recebe uma notificação da nova sala em seu cliente de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e83f9-128">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
    4.  <span data-ttu-id="e83f9-p107">Para controlar o envio de arquivo nas salas de chat pertencentes a esta categoria, selecione ou desmarque a caixa de seleção **Habilitar carregamento de arquivo**. Se estiver marcada, as salas desta categoria podem habilitar ou desabilitar carregamentos de arquivos; se estiver desmarcada, as salas nesta categoria não podem ter arquivos carregados.</span><span class="sxs-lookup"><span data-stu-id="e83f9-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="e83f9-131">Essa configuração é imposta no servidor porque aplicativos personalizados ou clientes de chat em grupo anterior que usam o servidor de chat de grupo&nbsp;do Office Communications Server 2007 R2 ou o Lync Server 2010, o chat em grupo podem postar arquivos para uma sala.</span><span class="sxs-lookup"><span data-stu-id="e83f9-131">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="e83f9-132">O cliente do Lync 2013 não tem recurso de carregamento/download de arquivo, portanto, se você tiver uma implantação do Lync 2013 ou do Lync 2013, não será possível postar arquivos em uma sala de chat do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e83f9-132">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="e83f9-133">Para controlar o histórico de chats, marque ou desmarque a caixa de seleção **habilitar histórico de chats** .</span><span class="sxs-lookup"><span data-stu-id="e83f9-133">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="e83f9-134">Se marcada, as salas de chat se tornam persistentes; caso contrário, as mensagens de chat não são persistentes.</span><span class="sxs-lookup"><span data-stu-id="e83f9-134">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="e83f9-135">Se a conformidade estiver habilitada, as salas de chat serão salvas em conformidade, mas os usuários não poderão acessar mensagens antigas.</span><span class="sxs-lookup"><span data-stu-id="e83f9-135">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="e83f9-136">Essa opção pode ser utilizada para salas designadas para colaborações em tempo real e ad hoc que não precisam do histórico de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e83f9-136">This option can be used for rooms designated for real-time, ad hoc collaborations that don’t need chat history to be persisted.</span></span>

7.  <span data-ttu-id="e83f9-137">Em  **Editar categoria**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e83f9-137">In **Edit Category**, do the following:</span></span>
    
      - <span data-ttu-id="e83f9-138">Em **Associação**, na seção **Membros permitidos** , adicione ou remova usuários e outros princípios de serviços de domínio do Active Directory (usuários, grupos de distribuição, unidades organizacionais e assim por diante) que podem ser adicionados como membros de salas de chat pertencente à categoria.</span><span class="sxs-lookup"><span data-stu-id="e83f9-138">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="e83f9-139">As entidades permitidas por uma categoria podem pesquisar por salas na categoria (a menos que uma sala esteja oculta, caso o qual apenas membros da sala podem pesquisar por ela no diretório).</span><span class="sxs-lookup"><span data-stu-id="e83f9-139">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
      - <span data-ttu-id="e83f9-140">Em **Associação**, na seção **Membros negados** , adicione ou remova usuários e outras entidades de segurança do Active Directory associadas a membros sendo negados da sala.</span><span class="sxs-lookup"><span data-stu-id="e83f9-140">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
      - <span data-ttu-id="e83f9-141">Em **Associação**, na seção **criadores** , adicione ou remova usuários e outras entidades de segurança do Active Directory associadas aos criadores para a categoria.</span><span class="sxs-lookup"><span data-stu-id="e83f9-141">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="e83f9-142">Um criador é um usuário que tem permissões de criar salas de chat e atribuir gerentes e membros de sala de chat.</span><span class="sxs-lookup"><span data-stu-id="e83f9-142">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>

8.  <span data-ttu-id="e83f9-143">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e83f9-143">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

