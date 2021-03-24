---
title: Página Principal do Suplemento de Chat Persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: Você pode usar a seção Adicionar da página Chat Persistente para associar URLs a salas de Chat Persistente. Essas URLs aparecem no cliente na sala de chat no painel de extensibilidade da conversa. Um administrador deve adicionar Add-ins à lista de complementos registrados, e os gerentes/Criadores de salas de chat devem associar salas a um dos complementos registrados para que os usuários possam ver essa atualização em seu cliente.
ms.openlocfilehash: a119eb677aca1cbe938ca0f4e173367e55abfa8e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099517"
---
# <a name="persistent-chat-add-in-main-page"></a><span data-ttu-id="72806-105">Página Principal do Suplemento de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="72806-105">Persistent Chat Add-in Main Page</span></span>

<span data-ttu-id="72806-106">Você pode usar a **seção Adicionar da** página Chat **Persistente** para associar URLs a salas de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="72806-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="72806-107">Essas URLs aparecem no cliente na sala de chat no painel de extensibilidade da conversa.</span><span class="sxs-lookup"><span data-stu-id="72806-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="72806-108">Um administrador deve adicionar Add-ins à lista de complementos registrados, e os gerentes/Criadores de salas de chat devem associar salas a um dos complementos registrados para que os usuários possam ver essa atualização em seu cliente.</span><span class="sxs-lookup"><span data-stu-id="72806-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="72806-109">Os suplementos são usados para estender a experiência na sala.</span><span class="sxs-lookup"><span data-stu-id="72806-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="72806-110">Um complemento típico pode incluir uma URL apontando para um aplicativo Silverlight que intercepta quando um ticker de ações é postado em uma sala de chat e mostra o histórico de ações no painel de extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="72806-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="72806-111">Outros exemplos incluem o URL do OneNote 2013 na sala de chat como um suplemento para incluir algum contexto compartilhado, como o "Mais lembrado" ou "Assunto do dia."</span><span class="sxs-lookup"><span data-stu-id="72806-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="72806-112">Para criar Complementos para salas de Chat Persistente, consulte [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="72806-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="72806-113">Se você for um Administrador de Chat Persistente, poderá criar complementos usando o painel de controle ou Windows PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="72806-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="72806-114">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="72806-114">Tasks you can perform</span></span>

<span data-ttu-id="72806-115">É possível executar as seguintes tarefas na página **Suplemento**:</span><span class="sxs-lookup"><span data-stu-id="72806-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="72806-116">Configurar os complementos para salas de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="72806-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="72806-117">Para configurar Suplementos para salas de chat</span><span class="sxs-lookup"><span data-stu-id="72806-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="72806-118">As listas a seguir descrevem os menus, comando, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="72806-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="72806-119">A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="72806-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="72806-120">No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL de Administrador.</span><span class="sxs-lookup"><span data-stu-id="72806-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="72806-121">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle, consulte [Open Lync Server Administrative Tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).</span><span class="sxs-lookup"><span data-stu-id="72806-121">For details about the different methods that you can use to start control panel, see [Open Lync Server Administrative Tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).</span></span>

3. <span data-ttu-id="72806-122">Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Suplemento**.</span><span class="sxs-lookup"><span data-stu-id="72806-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="72806-123">Para várias implantações de pool do Servidor de Chat Persistente, selecione o pool apropriado na listada.</span><span class="sxs-lookup"><span data-stu-id="72806-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="72806-124">Na página **Suplementos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="72806-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="72806-125">Em **Selecionar um Serviço,** selecione o serviço correspondente ao pool do Servidor de Chat Persistente onde você precisa criar o Add-in.</span><span class="sxs-lookup"><span data-stu-id="72806-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="72806-126">Os suplementos não podem ser movidos de um pool para outro ou compartilhado entre pools diferentes.</span><span class="sxs-lookup"><span data-stu-id="72806-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="72806-127">Em **Suplementos novos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="72806-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="72806-128">Em **Nome**, especifique um nome para o novo suplemento.</span><span class="sxs-lookup"><span data-stu-id="72806-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="72806-p107">Em **URL**, especifique o  URL que deve ser associada ao suplemento. Os URLs são limitados aos protocolos http e https.</span><span class="sxs-lookup"><span data-stu-id="72806-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="72806-131">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="72806-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="72806-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="72806-132">See also</span></span>

<span data-ttu-id="72806-133">Para obter detalhes sobre recursos e recursos do Servidor de Chat Persistente, consulte [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="72806-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>