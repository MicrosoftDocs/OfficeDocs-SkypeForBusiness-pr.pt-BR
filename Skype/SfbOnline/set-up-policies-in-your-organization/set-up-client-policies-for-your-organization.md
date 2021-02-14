---
title: Configurar políticas de clientes para sua organização
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: A ajuda de políticas de cliente determina os recursos do Skype for Business Online que são disponibilizados para os usuários; por exemplo, você pode dar a alguns usuários o direito de transferir arquivos enquanto nega este direito a outros usuários.
ms.openlocfilehash: 3a7dd7a2840a4e94abe88c472e6dc5b0e1720704
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814350"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="8937d-103">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="8937d-103">Set up client policies for your organization</span></span>

<span data-ttu-id="8937d-104">A ajuda de políticas de cliente determina os recursos do Skype for Business Online que são disponibilizados para os usuários; por exemplo, você pode dar a alguns usuários o direito de transferir arquivos enquanto nega este direito a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="8937d-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="8937d-105">As configurações de política de cliente podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **Set-CsClientPolicy** para modificar as configurações de uma política existente.</span><span class="sxs-lookup"><span data-stu-id="8937d-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="8937d-106">Definir suas políticas de cliente</span><span class="sxs-lookup"><span data-stu-id="8937d-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="8937d-107">Para todas as configurações de política de cliente no Skype for Business Online, você deve usar o Windows PowerShell e não pode **usar** o Centro de **administração do Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="8937d-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="8937d-108">Verificar e iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8937d-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="8937d-109">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="8937d-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="8937d-110">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8937d-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="8937d-111">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8937d-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="8937d-p101">Se você não tiver a versão 3.0 ou superior, será necessário baixar e instalar atualizações para o Windows PowerShell. Confira [o Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="8937d-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="8937d-115">Você também precisará instalar o módulo do Windows PowerShell para Teams que permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="8937d-115">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="8937d-116">Se precisar saber mais, confira Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx)em uma única janela do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8937d-116">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="8937d-117">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8937d-117">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="8937d-118">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="8937d-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="8937d-119">Na janela **do Windows PowerShell,** conecte-se ao Microsoft 365 ou ao Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="8937d-119">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8937d-120">No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="8937d-120">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
    >
    > <span data-ttu-id="8937d-121">Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="8937d-121">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```powershell
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session 
       ```
<span data-ttu-id="8937d-122">Se quiser saber mais sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx) em uma única janela do Windows PowerShell ou Configurar seu computador para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="8937d-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="8937d-123">Desabilitar emoticons e notificações de presença e impedir o salvar de IMs</span><span class="sxs-lookup"><span data-stu-id="8937d-123">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="8937d-124">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="8937d-124">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="8937d-125">Veja mais no [cmdlet New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)</span><span class="sxs-lookup"><span data-stu-id="8937d-125">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="8937d-126">Para conceder a nova política criada a todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="8937d-126">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="8937d-127">Veja mais no [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="8937d-127">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="8937d-128">Se você já criou uma política, pode usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar as configurações aos usuários.</span><span class="sxs-lookup"><span data-stu-id="8937d-128">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="8937d-129">Habilitar URLs ou hyperlinks para tornarem-se clicáveis nas mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="8937d-129">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="8937d-130">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="8937d-130">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="8937d-131">Veja mais no [cmdlet New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)</span><span class="sxs-lookup"><span data-stu-id="8937d-131">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="8937d-132">Para conceder a nova política criada a todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="8937d-132">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="8937d-133">Veja mais no [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="8937d-133">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="8937d-134">Se você já criou uma política, pode usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar as configurações aos usuários.</span><span class="sxs-lookup"><span data-stu-id="8937d-134">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="8937d-135">Impedir a exibição de contatos recentes</span><span class="sxs-lookup"><span data-stu-id="8937d-135">Prevent showing recent contacts</span></span>

- <span data-ttu-id="8937d-136">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="8937d-136">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="8937d-137">Veja mais no [cmdlet New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)</span><span class="sxs-lookup"><span data-stu-id="8937d-137">See more on the [New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="8937d-138">Para conceder a nova política criada ao Amos Marble, execute:</span><span class="sxs-lookup"><span data-stu-id="8937d-138">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="8937d-139">Veja mais no [cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)</span><span class="sxs-lookup"><span data-stu-id="8937d-139">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="8937d-140">Se você já criou uma política, pode usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar as configurações aos usuários.</span><span class="sxs-lookup"><span data-stu-id="8937d-140">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="8937d-141">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="8937d-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="8937d-142">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="8937d-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8937d-143">Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="8937d-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="8937d-144">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="8937d-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8937d-145">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8937d-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="8937d-146">Seis motivos pelos quais você pode querer usar o Windows PowerShell para gerenciar o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="8937d-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="8937d-147">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="8937d-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="8937d-148">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="8937d-148">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="8937d-149">Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8937d-149">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="8937d-150">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8937d-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="8937d-151">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8937d-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="8937d-152">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8937d-152">Related topics</span></span>
[<span data-ttu-id="8937d-153">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="8937d-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="8937d-154">Bloquear transferências de arquivo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="8937d-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="8937d-155">Configurar políticas de conferência em sua organização</span><span class="sxs-lookup"><span data-stu-id="8937d-155">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
