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
f1keywords: None
ms.custom:
- Setup
description: A ajuda de políticas de cliente determina os recursos do Skype for Business Online que são disponibilizados para os usuários; por exemplo, você pode dar a alguns usuários o direito de transferir arquivos enquanto nega este direito a outros usuários.
ms.openlocfilehash: da0640d2fb9f9fe30e29c1f58ed232350422fff4
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221175"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="ee23e-103">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="ee23e-103">Set up client policies for your organization</span></span>

<span data-ttu-id="ee23e-104">A ajuda de políticas de cliente determina os recursos do Skype for Business Online que são disponibilizados para os usuários; por exemplo, você pode dar a alguns usuários o direito de transferir arquivos enquanto nega este direito a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="ee23e-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="ee23e-105">As configurações de política de cliente podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **set-CsClientPolicy** para modificar as configurações de uma política existente.</span><span class="sxs-lookup"><span data-stu-id="ee23e-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="ee23e-106">Definir suas políticas de cliente</span><span class="sxs-lookup"><span data-stu-id="ee23e-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="ee23e-107">Para todas as configurações de política de cliente no Skype for Business Online, você deve usar o Windows PowerShell e **não pode usar** o **centro de administração do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="ee23e-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="ee23e-108">Verificar e iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee23e-108">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="ee23e-109">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="ee23e-109">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="ee23e-110">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ee23e-110">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ee23e-111">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ee23e-111">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="ee23e-112">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee23e-112">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="ee23e-113">Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0.</span><span class="sxs-lookup"><span data-stu-id="ee23e-113">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="ee23e-114">Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="ee23e-114">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="ee23e-p102">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="ee23e-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="ee23e-118">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="ee23e-118">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="ee23e-119">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ee23e-119">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="ee23e-120">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ee23e-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ee23e-121">Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="ee23e-121">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ee23e-122">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="ee23e-122">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="ee23e-123">Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ee23e-123">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="ee23e-124">Desativar emoticons e notificações de presença e evitar o salvamento de mensagens de chat</span><span class="sxs-lookup"><span data-stu-id="ee23e-124">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="ee23e-125">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="ee23e-125">To create a new policy for these settings, run:</span></span>
    
> 
>   ```
>   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
>   ```

  <span data-ttu-id="ee23e-126">Veja mais no cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ee23e-126">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="ee23e-127">Para conceder a nova política criada para todos os usuários de sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="ee23e-127">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
>   ```
>   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
>   ```

  <span data-ttu-id="ee23e-128">Veja mais no cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ee23e-128">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="ee23e-129">Se você já tiver criado uma política, poderá usar o cmdlet [set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) para aplicar as configurações aos usuários.</span><span class="sxs-lookup"><span data-stu-id="ee23e-129">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="ee23e-130">Habilitar URLs ou hyperlinks para tornarem-se clicáveis nas mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="ee23e-130">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="ee23e-131">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="ee23e-131">To create a new policy for these settings, run:</span></span>
    
> 
>   ```
>   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
>   ```

  <span data-ttu-id="ee23e-132">Veja mais no cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ee23e-132">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="ee23e-133">Para conceder a nova política criada para todos os usuários de sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="ee23e-133">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
>   ```
>   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
>   ```

  <span data-ttu-id="ee23e-134">Veja mais no cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ee23e-134">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
<span data-ttu-id="ee23e-135">Se você já tiver criado uma política, poderá usar o cmdlet [set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) para aplicar as configurações aos usuários.</span><span class="sxs-lookup"><span data-stu-id="ee23e-135">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="ee23e-136">Impedir a exibição de contatos recentes</span><span class="sxs-lookup"><span data-stu-id="ee23e-136">Prevent showing recent contacts</span></span>

- <span data-ttu-id="ee23e-137">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="ee23e-137">To create a new policy for these settings, run:</span></span>
  > 
  > ```
  > New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  > ```

  <span data-ttu-id="ee23e-138">Veja mais no cmdlet [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ee23e-138">See more on the [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="ee23e-139">Para conceder a nova política criada para o Marble Amos, execute:</span><span class="sxs-lookup"><span data-stu-id="ee23e-139">To grant the new policy you created to Amos Marble, run:</span></span>
  > 
  > ```
  > Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  > ```

  <span data-ttu-id="ee23e-140">Veja mais no cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .</span><span class="sxs-lookup"><span data-stu-id="ee23e-140">See more on the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="ee23e-141">Se você já tiver criado uma política, poderá usar o cmdlet [set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) para aplicar as configurações aos usuários.</span><span class="sxs-lookup"><span data-stu-id="ee23e-141">If you have already created a policy, you can use the [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ee23e-142">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ee23e-142">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="ee23e-143">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="ee23e-143">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ee23e-144">Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="ee23e-144">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="ee23e-145">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ee23e-145">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ee23e-146">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ee23e-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ee23e-147">Seis motivos pelos quais você pode querer usar o Windows PowerShell para gerenciar o Office 365</span><span class="sxs-lookup"><span data-stu-id="ee23e-147">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ee23e-p104">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ee23e-p104">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ee23e-150">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee23e-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ee23e-151">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ee23e-151">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ee23e-152">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ee23e-152">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="ee23e-153">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ee23e-153">Related topics</span></span>
[<span data-ttu-id="ee23e-154">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="ee23e-154">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="ee23e-155">Bloquear transferências de arquivo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="ee23e-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="ee23e-156">Configurar políticas de conferência em sua organização</span><span class="sxs-lookup"><span data-stu-id="ee23e-156">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
