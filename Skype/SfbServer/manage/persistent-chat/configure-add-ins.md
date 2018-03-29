---
title: Configurar suplementos para salas de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Resumo: Saiba como configurar suplementos para salas de chat Persistent Chat Server na Skype para Business Server 2015.'
ms.openlocfilehash: dbd1eba6cf73783d02b502930f271ada93e28145
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="1121e-103">Configurar suplementos para salas de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1121e-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1121e-104">**Resumo:** Aprenda a configurar suplementos para salas de chat Persistent Chat Server no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1121e-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1121e-105">Os suplementos são usados para estender a experiência na sala por meio da associação de URLs com salas de chat.</span><span class="sxs-lookup"><span data-stu-id="1121e-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="1121e-106">Essas URLs aparecem no painel de extensibilidade da conversa do cliente.</span><span class="sxs-lookup"><span data-stu-id="1121e-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="1121e-107">Um suplemento típico pode incluir uma URL que aponta para um aplicativo Silverlight que intercepta quando um registrador de cotações é postado em uma sala de bate-papo e mostra o histórico de estoque no painel de extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="1121e-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="1121e-108">Outros exemplos incluem a URL do OneNote 2013 na sala de chat como um suplemento para incluir algum contexto compartilhado, como o "Mais lembrado" ou "Assunto do dia."</span><span class="sxs-lookup"><span data-stu-id="1121e-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="1121e-109">Antes que os usuários possam ver um suplemento em um cliente, você deve adicionar o suplemento à lista de suplementos registrados, e Gerentes ou Criadores de salas de chat precisam associar as salas com os suplementos.</span><span class="sxs-lookup"><span data-stu-id="1121e-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="1121e-110">Configure suplementos para salas de chat usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="1121e-110">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="1121e-111">Para configurar suplementos para salas de chat usando o Painel de Controle:</span><span class="sxs-lookup"><span data-stu-id="1121e-111">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="1121e-112">A partir de uma conta de usuário com a função CsPersistentChatAdministrator ou CsAdministrator atribuída, faça o logon em qualquer computador na sua implementação interna.</span><span class="sxs-lookup"><span data-stu-id="1121e-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1121e-113">No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="1121e-113">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="1121e-114">Na barra de navegação esquerda, clique em **Chat Persistente** e depois em **Suplemento**.</span><span class="sxs-lookup"><span data-stu-id="1121e-114">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="1121e-115">Para várias implantações de pool de servidor de Chat persistente, selecione o pool apropriado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="1121e-115">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="1121e-116">Na página **Suplementos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="1121e-116">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="1121e-117">Em **Selecionar um serviço**, selecione o serviço correspondente para o pool do servidor de Chat persistente onde você precisa criar o suplemento.</span><span class="sxs-lookup"><span data-stu-id="1121e-117">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="1121e-118">Os Suplementos não podem ser movidos de um pool a outro nem compartilhado entre pools diferentes.</span><span class="sxs-lookup"><span data-stu-id="1121e-118">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="1121e-119">Em **Suplementos novos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1121e-119">In **New Add-in**, do the following:</span></span>
    
  - <span data-ttu-id="1121e-120">Em **Nome**, especifique um nome para o novo suplemento.</span><span class="sxs-lookup"><span data-stu-id="1121e-120">In **Name**, specify a name for the new add-in.</span></span>
    
  - <span data-ttu-id="1121e-p103">Em **URL**, especifique a URL que deve ser associada ao suplemento. As URLs são limitadas aos protocolos http e https.</span><span class="sxs-lookup"><span data-stu-id="1121e-p103">In **URL**, specify the URL to be associated with the add-in. URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="1121e-123">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1121e-123">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="1121e-124">Configure suplementos usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1121e-124">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="1121e-125">Você pode configurar suplementos para salas de chat usando os seguintes cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1121e-125">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="1121e-126">Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros disponíveis, consulte [Skype do Shell de gerenciamento do Business Server 2015](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="1121e-126">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
<span data-ttu-id="1121e-127">| |</span><span class="sxs-lookup"><span data-stu-id="1121e-127"></span></span>
|<span data-ttu-id="1121e-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="1121e-128">**Cmdlet**</span></span>|<span data-ttu-id="1121e-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1121e-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1121e-130">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="1121e-130">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="1121e-131">Criar um novo suplemento</span><span class="sxs-lookup"><span data-stu-id="1121e-131">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="1121e-132">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="1121e-132">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="1121e-133">Definir configurações para um suplemento existente</span><span class="sxs-lookup"><span data-stu-id="1121e-133">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="1121e-134">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="1121e-134">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="1121e-135">Recuperar informações sobre suplementos</span><span class="sxs-lookup"><span data-stu-id="1121e-135">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="1121e-136">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="1121e-136">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="1121e-137">Remover um suplemento</span><span class="sxs-lookup"><span data-stu-id="1121e-137">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="1121e-138">Criar um novo suplemento</span><span class="sxs-lookup"><span data-stu-id="1121e-138">Create a new add-in</span></span>

<span data-ttu-id="1121e-139">Você pode criar um novo suplemento usando o cmdlet **New-CsPersistentChatAddin** .</span><span class="sxs-lookup"><span data-stu-id="1121e-139">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="1121e-140">Por exemplo, o comando a seguir cria um novo suplemento (com o nome ITPersistentChatAddin) para o pool atl-cs-001.contoso.com. O parâmetro de URL e o valor do parâmetro http://atl-cs-001.contoso.com/itchat especifique o local da página da Web do suplemento:</span><span class="sxs-lookup"><span data-stu-id="1121e-140">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com. The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="1121e-141">Definir configurações para um suplemento existente</span><span class="sxs-lookup"><span data-stu-id="1121e-141">Configure settings for an existing add-in</span></span>

<span data-ttu-id="1121e-142">Você pode definir configurações para um suplemento existente usando o cmdlet **Set-CsPersistentChatAddIn**.</span><span class="sxs-lookup"><span data-stu-id="1121e-142">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="1121e-143">Por exemplo, o seguinte comando modifica a URL atribuída ao suplemento do Chat Persistente ITPersistentChatAddin.</span><span class="sxs-lookup"><span data-stu-id="1121e-143">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="1121e-144">Nesse caso, a URL é alterada parahttp://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="1121e-144">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="1121e-145">Recuperar informações sobre suplementos</span><span class="sxs-lookup"><span data-stu-id="1121e-145">Retrieve information about add-ins</span></span>

<span data-ttu-id="1121e-p106">Você pode obter informações sobre suplementos usando o cmdlet **Get-CsPersistentChatAddin**. Por exemplo, o seguinte comando retorna informações sobre todos os suplementos de Chat Persistente configurados para uso na organização:</span><span class="sxs-lookup"><span data-stu-id="1121e-p106">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet. For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="1121e-148">Remover um suplemento</span><span class="sxs-lookup"><span data-stu-id="1121e-148">Remove an add-in</span></span>

<span data-ttu-id="1121e-149">Você pode remover um suplemento usando o cmdlet **Remove-CsPersistentChatAddIn** .</span><span class="sxs-lookup"><span data-stu-id="1121e-149">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="1121e-150">Por exemplo, o seguinte comando remove o suplemento do Chat Persistente ITChatAddin encontrado no pool atl-cs-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="1121e-150">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


