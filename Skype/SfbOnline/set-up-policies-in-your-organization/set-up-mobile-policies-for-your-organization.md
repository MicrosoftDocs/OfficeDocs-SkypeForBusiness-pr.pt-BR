---
title: Configurar políticas móveis para sua organização
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: Você pode configurar como os usuários se conectam ao Skype for Business online usando o aplicativo Skype for Business em dispositivos móveis, como um recurso que permite aos usuários fazer e receber chamadas no celular usando o número de telefone comercial dele em vez do número de telefone celular deles. As políticas de mobilidade também podem ser usadas para exigir conexões Wi-Fi ao fazer ou receber chamadas.
ms.openlocfilehash: ac8f94cb7203b3b0ee4698969db0b76cb1e31a49
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776256"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="dc8ac-104">Configurar políticas móveis para sua organização</span><span class="sxs-lookup"><span data-stu-id="dc8ac-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="dc8ac-p102">Você pode configurar como os usuários se conectam ao Skype for Business online usando o aplicativo Skype for Business em dispositivos móveis, como um recurso que permite aos usuários fazer e receber chamadas no celular usando o número de telefone comercial dele em vez do número de telefone celular deles. As políticas de mobilidade também podem ser usadas para exigir conexões Wi-Fi ao fazer ou receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-p102">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="dc8ac-107">As configurações da política móvel podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **set-CsMobilityPolicy** para modificar as configurações de uma política existente.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="dc8ac-108">Definir suas políticas de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="dc8ac-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="dc8ac-109">Para todas as configurações de política de dispositivo móvel no Skype for Business Online, você deve usar o Windows PowerShell e **não pode usar** o **centro de administração do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="dc8ac-110">Verificar e iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc8ac-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="dc8ac-111">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="dc8ac-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="dc8ac-112">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="dc8ac-113">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="dc8ac-p103">Se você não tiver a versão 3,0 ou superior, será necessário baixar e instalar atualizações para o Windows PowerShell. Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0. Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="dc8ac-p104">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="dc8ac-120">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="dc8ac-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="dc8ac-121">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="dc8ac-121">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="dc8ac-122">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="dc8ac-123">Na janela do **Windows PowerShell** , conecte-se ao seu Microsoft 365 ou ao Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="dc8ac-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
        > [!NOTE]
        > <span data-ttu-id="dc8ac-124">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="dc8ac-125">Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="dc8ac-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="dc8ac-126">Requerer uma conexão WiFi para vídeo para um usuário</span><span class="sxs-lookup"><span data-stu-id="dc8ac-126">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="dc8ac-127">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="dc8ac-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="dc8ac-128">Veja mais no cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="dc8ac-128">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="dc8ac-129">Para conceder a nova política criada para todos os usuários de sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="dc8ac-129">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="dc8ac-130">Veja mais no cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="dc8ac-130">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="dc8ac-131">Se você já tiver criado uma política, poderá usar o cmdlet [set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para fazer alterações na política existente e usar o cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar a configuração aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-131">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="dc8ac-132">Impedir que um usuário use o app Skype for Business</span><span class="sxs-lookup"><span data-stu-id="dc8ac-132">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="dc8ac-133">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="dc8ac-133">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="dc8ac-134">Veja mais no cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="dc8ac-134">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="dc8ac-135">Para conceder a nova política criada para o Marble Amos, execute:</span><span class="sxs-lookup"><span data-stu-id="dc8ac-135">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="dc8ac-136">Veja mais no cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="dc8ac-136">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="dc8ac-137">Se você já tiver criado uma política, poderá usar o cmdlet [set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar a configuração aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-137">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="dc8ac-138">Impedir que um usuário faça chamadas IP usando um dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="dc8ac-138">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="dc8ac-139">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="dc8ac-139">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="dc8ac-140">Veja mais no cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="dc8ac-140">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="dc8ac-141">Para conceder a nova política criada para todos os usuários de sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="dc8ac-141">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="dc8ac-142">Veja mais no cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="dc8ac-142">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="dc8ac-143">Se você já tiver criado uma política, poderá usar o cmdlet [set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para fazer alterações na política existente e usar o cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar a configuração aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-143">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="dc8ac-144">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="dc8ac-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="dc8ac-145">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-145">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="dc8ac-146">Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-146">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="dc8ac-147">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="dc8ac-147">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="dc8ac-148">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="dc8ac-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="dc8ac-149">Seis motivos pelos quais você pode querer usar o Windows PowerShell para gerenciar o Office 365</span><span class="sxs-lookup"><span data-stu-id="dc8ac-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="dc8ac-150">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está usando alterações de configuração para muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="dc8ac-150">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="dc8ac-151">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="dc8ac-151">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="dc8ac-152">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc8ac-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="dc8ac-153">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="dc8ac-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="dc8ac-154">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="dc8ac-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="dc8ac-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="dc8ac-155">Related topics</span></span>
[<span data-ttu-id="dc8ac-156">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="dc8ac-156">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="dc8ac-157">Bloquear transferências de arquivo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="dc8ac-157">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="dc8ac-158">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="dc8ac-158">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="dc8ac-159">Configurar políticas de conferência em sua organização</span><span class="sxs-lookup"><span data-stu-id="dc8ac-159">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
