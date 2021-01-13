---
title: Configurar os complementos para salas de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Resumo: Saiba como configurar os complementos para salas de chat do Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 1aca54f3db1229527256d1e2801cb057f4f79387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815072"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="c3882-103">Configurar os complementos para salas de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c3882-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c3882-104">**Resumo:** Saiba como configurar os complementos para salas de chat do Servidor de Chat Persistente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c3882-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c3882-105">Os complementos são usados para estender a experiência na sala associando URLs a salas de chat.</span><span class="sxs-lookup"><span data-stu-id="c3882-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="c3882-106">Essas URLs aparecem no painel de extensibilidade da conversa do cliente.</span><span class="sxs-lookup"><span data-stu-id="c3882-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="c3882-107">Um complemento típico pode incluir uma URL apontando para um aplicativo Silverlight que intercepta quando uma cotação das ações é postada em uma sala de chat e mostra o histórico de ações no painel de extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="c3882-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="c3882-108">Outros exemplos incluem o URL do OneNote 2013 na sala de chat como um suplemento para incluir algum contexto compartilhado, como o "Mais lembrado" ou "Assunto do dia."</span><span class="sxs-lookup"><span data-stu-id="c3882-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="c3882-109">Para que os usuários possam ver um complemento no cliente, você deve adicioná-lo à lista de complementos registrados, e os Gerentes ou Criadores de sala de chat precisam associar salas ao complemento.</span><span class="sxs-lookup"><span data-stu-id="c3882-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c3882-110">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c3882-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c3882-111">A mesma funcionalidade está disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="c3882-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="c3882-112">Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="c3882-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="c3882-113">Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c3882-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="c3882-114">Configurar os complementos para salas de chat usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="c3882-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="c3882-115">Para configurar os complementos para salas de chat usando o Painel de Controle:</span><span class="sxs-lookup"><span data-stu-id="c3882-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="c3882-116">A partir de uma conta de usuário atribuída à função CsPersistentChatAdministrator ou CsAdministrator, faça logon em qualquer computador em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="c3882-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c3882-117">No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.</span><span class="sxs-lookup"><span data-stu-id="c3882-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="c3882-118">Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Suplemento**.</span><span class="sxs-lookup"><span data-stu-id="c3882-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="c3882-119">Para várias implantações de pool de Servidor de Chat Persistente, selecione o pool apropriado na lista drop-down.</span><span class="sxs-lookup"><span data-stu-id="c3882-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="c3882-120">Na página **Suplementos**, clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c3882-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="c3882-121">Em **Selecionar um Serviço,** selecione o serviço correspondente ao pool de Servidor de Chat Persistente onde você precisa criar o Add-in.</span><span class="sxs-lookup"><span data-stu-id="c3882-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="c3882-122">Os suplementos não podem ser movidos de um pool para outro ou compartilhado entre pools diferentes.</span><span class="sxs-lookup"><span data-stu-id="c3882-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="c3882-123">Em **Suplementos novos**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c3882-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="c3882-124">Em **Nome**, especifique um nome para o novo suplemento.</span><span class="sxs-lookup"><span data-stu-id="c3882-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="c3882-125">Em **URL**, especifique o  URL que deve ser associada ao suplemento.</span><span class="sxs-lookup"><span data-stu-id="c3882-125">In **URL**, specify the URL to be associated with the add-in.</span></span> <span data-ttu-id="c3882-126">As URLs são limitadas aos protocolos http e https.</span><span class="sxs-lookup"><span data-stu-id="c3882-126">URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="c3882-127">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c3882-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="c3882-128">Configurar os complementos usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3882-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="c3882-129">Você pode configurar os complementos para salas de chat usando os seguintes cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3882-129">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="c3882-130">Para obter detalhes sobre sintaxe, incluindo todos os parâmetros disponíveis, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="c3882-130">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="c3882-131">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="c3882-131">**Cmdlet**</span></span>|<span data-ttu-id="c3882-132">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c3882-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c3882-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="c3882-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="c3882-134">Criar um novo add-in</span><span class="sxs-lookup"><span data-stu-id="c3882-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="c3882-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="c3882-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="c3882-136">Definir configurações para um complemento existente</span><span class="sxs-lookup"><span data-stu-id="c3882-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="c3882-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="c3882-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="c3882-138">Recuperar informações sobre os complementos</span><span class="sxs-lookup"><span data-stu-id="c3882-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="c3882-139">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="c3882-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="c3882-140">Remover um complemento</span><span class="sxs-lookup"><span data-stu-id="c3882-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="c3882-141">Criar um novo add-in</span><span class="sxs-lookup"><span data-stu-id="c3882-141">Create a new add-in</span></span>

<span data-ttu-id="c3882-142">Você pode criar um novo Add-in usando o cmdlet **New-CsPersistentChatAddin.**</span><span class="sxs-lookup"><span data-stu-id="c3882-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="c3882-143">Por exemplo, o comando a seguir cria um novo complemento (com o nome ITPersistentChatAddin) para o pool atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c3882-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="c3882-144">O parâmetro URL e o valor do http://atl-cs-001.contoso.com/itchat parâmetro especificam o local da página da Web do complemento:</span><span class="sxs-lookup"><span data-stu-id="c3882-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="c3882-145">Definir configurações para um complemento existente</span><span class="sxs-lookup"><span data-stu-id="c3882-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="c3882-146">Você pode definir configurações para um complemento existente usando o cmdlet **Set-CsPersistentChatAddIn.**</span><span class="sxs-lookup"><span data-stu-id="c3882-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="c3882-147">Por exemplo, o comando a seguir modifica a URL atribuída ao complemento de Chat Persistente ITPersistentChatAddin.</span><span class="sxs-lookup"><span data-stu-id="c3882-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="c3882-148">Nesse caso, a URL é alterada para http://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="c3882-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="c3882-149">Recuperar informações sobre os complementos</span><span class="sxs-lookup"><span data-stu-id="c3882-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="c3882-150">Você pode obter informações sobre os complementos usando o cmdlet **Get-CsPersistentChatAddin.**</span><span class="sxs-lookup"><span data-stu-id="c3882-150">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet.</span></span> <span data-ttu-id="c3882-151">Por exemplo, o comando a seguir retorna informações sobre todos os complementos de Chat Persistente configurados para uso na organização:</span><span class="sxs-lookup"><span data-stu-id="c3882-151">For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="c3882-152">Remover um complemento</span><span class="sxs-lookup"><span data-stu-id="c3882-152">Remove an add-in</span></span>

<span data-ttu-id="c3882-153">Você pode remover um Add-in usando o cmdlet **Remove-CsPersistentChatAddIn.**</span><span class="sxs-lookup"><span data-stu-id="c3882-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="c3882-154">Por exemplo, o seguinte comando remove o complemento de Chat Persistente ITChatAddin encontrado no pool atl-cs-001.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="c3882-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


