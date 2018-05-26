---
title: Suplemento de Chat Persistente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: Você pode usar a seção Add-in da página Chat persistente para associar URLs salas de Chat persistente. Essas URLs aparecem no cliente na sala de chat no painel de extensão da conversa. Um administrador precisa adicionar Suplementos à lista de suplementos registrados, e os gerentes/Criadores de sala de chat precisam associar salas a um dos suplementos registrados antes de os usuários poderem ver essa atualização em seu cliente.
ms.openlocfilehash: b9b10c7c4b055c694d58b6cfda9b1e2a84739483
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2018
---
# <a name="persistent-chat-add-in"></a><span data-ttu-id="526a9-105">Suplemento de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="526a9-105">Persistent Chat Add-in</span></span>
 
<span data-ttu-id="526a9-106">Você pode usar a seção **Add-in** da página **Chat persistente** para associar URLs salas de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="526a9-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="526a9-107">Essas URLs aparecem no cliente na sala de chat no painel de extensão da conversa.</span><span class="sxs-lookup"><span data-stu-id="526a9-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="526a9-108">Um administrador precisa adicionar Suplementos à lista de suplementos registrados, e os gerentes/Criadores de sala de chat precisam associar salas a um dos suplementos registrados antes de os usuários poderem ver essa atualização em seu cliente.</span><span class="sxs-lookup"><span data-stu-id="526a9-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>
  
<span data-ttu-id="526a9-109">Os suplementos são usados para estender a experiência na sala.</span><span class="sxs-lookup"><span data-stu-id="526a9-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="526a9-110">Um suplemento típico pode incluir uma URL que aponta para um aplicativo Silverlight que intercepta quando um registrador de cotações é postado em uma sala de bate-papo e mostra o histórico de estoque no painel de extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="526a9-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="526a9-111">Outros exemplos incluem a URL do OneNote 2013 na sala de chat como um suplemento para incluir algum contexto compartilhado, como o "Mais lembrado" ou "Assunto do dia."</span><span class="sxs-lookup"><span data-stu-id="526a9-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
<span data-ttu-id="526a9-112">Para criar suplementos para salas de Chat persistente, consulte [Configurar suplementos para salas de Chat persistente no Skype para Business Server 2015](../../../manage/persistent-chat/configure-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="526a9-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="526a9-113">Se você for um administrador de Chat persistente, você pode criar suplementos usando o painel de controle ou os cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="526a9-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="526a9-114">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="526a9-114">Tasks that you can perform</span></span>

<span data-ttu-id="526a9-115">É possível executar as seguintes tarefas na página **Suplemento**:</span><span class="sxs-lookup"><span data-stu-id="526a9-115">You can perform the following tasks on the **Add-in** page:</span></span>
  
- [<span data-ttu-id="526a9-116">Configurar suplementos para salas de Chat persistente no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="526a9-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../../manage/persistent-chat/configure-add-ins.md)
    
## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="526a9-117">Para configurar Suplementos para as salas de chat</span><span class="sxs-lookup"><span data-stu-id="526a9-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="526a9-118">As listas a seguir descrevem os menus, comando, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="526a9-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
1. <span data-ttu-id="526a9-119">A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.</span><span class="sxs-lookup"><span data-stu-id="526a9-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="526a9-120">No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="526a9-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="526a9-121">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle, consulte [Abrir ferramentas administrativas do Lync Server](http://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span><span class="sxs-lookup"><span data-stu-id="526a9-121">For details about the different methods that you can use to start the control panel, see [Open Lync Server Administrative Tools](http://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>
    
3. <span data-ttu-id="526a9-122">Na barra de navegação esquerda, clique em **Chat Persistente** e depois em **Suplemento**.</span><span class="sxs-lookup"><span data-stu-id="526a9-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="526a9-123">Para várias implantações de pool de servidor de Chat persistente, selecione o pool apropriado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="526a9-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="526a9-124">Na página **Suplementos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="526a9-124">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="526a9-125">Em **Selecionar um serviço**, selecione o serviço correspondente para o pool do servidor de Chat persistente onde você precisa criar o suplemento.</span><span class="sxs-lookup"><span data-stu-id="526a9-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="526a9-126">Os Suplementos não podem ser movidos de um pool a outro nem compartilhado entre pools diferentes.</span><span class="sxs-lookup"><span data-stu-id="526a9-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="526a9-127">Em **Suplementos novos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="526a9-127">In **New Add-in**, do the following:</span></span>
    
  - <span data-ttu-id="526a9-128">Em **Nome**, especifique um nome para o novo suplemento.</span><span class="sxs-lookup"><span data-stu-id="526a9-128">In **Name**, specify a name for the new add-in.</span></span>
    
  - <span data-ttu-id="526a9-p107">Em **URL**, especifique a URL que deve ser associada ao suplemento. As URLs são limitadas aos protocolos http e https.</span><span class="sxs-lookup"><span data-stu-id="526a9-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>
    
7. <span data-ttu-id="526a9-131">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="526a9-131">Click **Commit**.</span></span>
    
### 

<span data-ttu-id="526a9-132">Para obter detalhes sobre os recursos de servidor de Chat persistente e recursos, consulte [Plan for Persistent Chat Server in Skype para Business Server 2015](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server na Skype para Business Server 2015](../../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [Gerenciar o servidor de Chat persistente no Skype para Business Server 2015](../../../manage/persistent-chat/persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="526a9-132">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../../manage/persistent-chat/persistent-chat.md).</span></span>
  

