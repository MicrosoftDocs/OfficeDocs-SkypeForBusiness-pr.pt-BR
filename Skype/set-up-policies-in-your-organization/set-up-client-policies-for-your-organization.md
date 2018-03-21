---
title: "Configurar políticas de cliente para sua organização"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "A ajuda de políticas de cliente determina os recursos do Skype for Business Online que são disponibilizados para os usuários; por exemplo, você pode dar a alguns usuários o direito de transferir arquivos enquanto nega este direito a outros usuários."
ms.openlocfilehash: 82fa2c828af9aed01652870ea5d3db02ca8248c3
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="b9e62-103">Configurar políticas de cliente para sua organização</span><span class="sxs-lookup"><span data-stu-id="b9e62-103">Set up client policies for your organization</span></span>

<span data-ttu-id="b9e62-104">A ajuda de políticas de cliente determina os recursos do Skype for Business Online que são disponibilizados para os usuários; por exemplo, você pode dar a alguns usuários o direito de transferir arquivos enquanto nega este direito a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="b9e62-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="b9e62-105">Configurações de diretiva do cliente podem ser configuradas no momento em que uma diretiva é criada ou você pode usar o cmdlet **Set-CsClientPolicy** para modificar as configurações de uma diretiva existente.</span><span class="sxs-lookup"><span data-stu-id="b9e62-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="b9e62-106">Definir suas políticas de cliente</span><span class="sxs-lookup"><span data-stu-id="b9e62-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="b9e62-107">Para todas as configurações de diretiva de cliente no Skype para Business Online, você deve usar o Windows PowerShell e você **não pode usar** o **Skype para centro de administração de negócios**.</span><span class="sxs-lookup"><span data-stu-id="b9e62-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="b9e62-108">Verificar e iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9e62-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="b9e62-109">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="b9e62-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="b9e62-110">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b9e62-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="b9e62-111">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b9e62-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="b9e62-p101">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="b9e62-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="b9e62-p102">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="b9e62-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="b9e62-118">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="b9e62-118">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="b9e62-119">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b9e62-119">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="b9e62-120">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="b9e62-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="b9e62-121">Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="b9e62-121">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b9e62-122">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="b9e62-122">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="b9e62-123">Se você quiser obter mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Conectando-se ao Skype para negócios Online usando o Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="b9e62-123">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="b9e62-124">Desabilitar notificações de presença e emoticons e evitam que o salvamento de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="b9e62-124">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="b9e62-125">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="b9e62-125">To create a new policy for these settings, run:</span></span>
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

  <span data-ttu-id="b9e62-126">Consulte obter mais informações sobre o cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b9e62-126">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="b9e62-127">Para conceder a nova política que você criou para todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="b9e62-127">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

  <span data-ttu-id="b9e62-128">Consulte obter mais informações sobre o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b9e62-128">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="b9e62-129">Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) para fazer alterações à diretiva existente e, em seguida, use o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) para aplicar as configurações para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="b9e62-129">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="b9e62-130">Habilitar URLs ou hyperlinks para tornarem-se clicáveis nas mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="b9e62-130">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="b9e62-131">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="b9e62-131">To create a new policy for these settings, run:</span></span>
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

  <span data-ttu-id="b9e62-132">Consulte obter mais informações sobre o cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b9e62-132">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="b9e62-133">Para conceder a nova política que você criou para todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="b9e62-133">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

  <span data-ttu-id="b9e62-134">Consulte obter mais informações sobre o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b9e62-134">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="b9e62-135">Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) para fazer alterações à diretiva existente e, em seguida, use o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) para aplicar as configurações para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="b9e62-135">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="b9e62-136">Impedir a exibição de contatos recentes</span><span class="sxs-lookup"><span data-stu-id="b9e62-136">Prevent showing recent contacts</span></span>

- <span data-ttu-id="b9e62-137">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="b9e62-137">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

  <span data-ttu-id="b9e62-138">Consulte obter mais informações sobre o cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b9e62-138">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="b9e62-139">Para conceder a nova política que você criou para Mármore Amos, execute:</span><span class="sxs-lookup"><span data-stu-id="b9e62-139">To grant the new policy you created to Amos Marble, run:</span></span>
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

  <span data-ttu-id="b9e62-140">Consulte obter mais informações sobre o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b9e62-140">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="b9e62-141">Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) para fazer alterações à diretiva existente e, em seguida, use o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) para aplicar as configurações para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="b9e62-141">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b9e62-142">Quer saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="b9e62-142">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="b9e62-p103">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b9e62-p103">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b9e62-146">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b9e62-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="b9e62-147">Seis motivos para usar o Windows PowerShell para gerenciar o Office 365 </span><span class="sxs-lookup"><span data-stu-id="b9e62-147">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="b9e62-p104">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b9e62-p104">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="b9e62-150">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9e62-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="b9e62-151">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b9e62-151">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b9e62-152">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b9e62-152">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="b9e62-153">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b9e62-153">Related topics</span></span>
[<span data-ttu-id="b9e62-154">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="b9e62-154">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="b9e62-155">Transferências de arquivos ponto a ponto de bloqueio</span><span class="sxs-lookup"><span data-stu-id="b9e62-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="b9e62-156">Configurar políticas de conferência na sua organização</span><span class="sxs-lookup"><span data-stu-id="b9e62-156">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
