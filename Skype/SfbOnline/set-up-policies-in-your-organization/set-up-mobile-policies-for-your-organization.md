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
description: Você pode configurar como seus usuários se conectam ao Skype for Business Online usando o aplicativo Skype for Business em dispositivos móveis, como um recurso que permite que os usuários façam e recebam chamadas telefônicas no celular usando o número de telefone comercial em vez do número de telefone celular. As políticas de mobilidade também podem ser usadas para exigir Wi-Fi conexões ao fazer ou receber chamadas.
ms.openlocfilehash: 5094a536a636300ea70a7d358e24ee5c0f511379
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814740"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="64ad7-104">Configurar políticas móveis para sua organização</span><span class="sxs-lookup"><span data-stu-id="64ad7-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="64ad7-p102">Você pode configurar como seus usuários se conectam ao Skype for Business Online usando o aplicativo Skype for Business em dispositivos móveis, como um recurso que permite que os usuários façam e recebam chamadas telefônicas no celular usando o número de telefone comercial em vez do número de telefone celular. As políticas de mobilidade também podem ser usadas para exigir Wi-Fi conexões ao fazer ou receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="64ad7-p102">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="64ad7-107">As configurações de política móvel podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **Set-CsMobilityPolicy** para modificar as configurações de uma política existente.</span><span class="sxs-lookup"><span data-stu-id="64ad7-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="64ad7-108">Definir suas políticas de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="64ad7-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="64ad7-109">Para todas as configurações de política móvel no Skype for Business Online, você deve usar o Windows PowerShell e não pode **usar** o Centro de **administração do Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="64ad7-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="64ad7-110">Verificar e iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="64ad7-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="64ad7-111">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="64ad7-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="64ad7-112">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="64ad7-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="64ad7-113">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="64ad7-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="64ad7-p103">Se você não tiver a versão 3.0 ou superior, será necessário baixar e instalar atualizações para o Windows PowerShell. Confira [o Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="64ad7-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="64ad7-117">Você também precisará instalar o módulo do Windows PowerShell para Teams que permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="64ad7-117">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="64ad7-118">Se precisar saber mais, confira Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx)em uma única janela do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64ad7-118">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="64ad7-119">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="64ad7-119">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="64ad7-120">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="64ad7-120">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="64ad7-121">Na janela **do Windows PowerShell,** conecte-se ao Microsoft 365 ou ao Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="64ad7-121">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
       > [!NOTE]
       > <span data-ttu-id="64ad7-122">No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="64ad7-122">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
       >
       > <span data-ttu-id="64ad7-123">Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="64ad7-123">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="64ad7-124">Se quiser saber mais sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx) em uma única janela do Windows PowerShell ou Configurar seu computador para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="64ad7-124">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="64ad7-125">Requerer uma conexão WiFi para vídeo para um usuário</span><span class="sxs-lookup"><span data-stu-id="64ad7-125">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="64ad7-126">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="64ad7-126">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="64ad7-127">Veja mais no cmdlet [New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)</span><span class="sxs-lookup"><span data-stu-id="64ad7-127">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="64ad7-128">Para conceder a nova política criada a todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="64ad7-128">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="64ad7-129">Veja mais no cmdlet [Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)</span><span class="sxs-lookup"><span data-stu-id="64ad7-129">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="64ad7-130">Se você já criou uma política, pode usar o cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para fazer alterações na política existente e usar o cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar a configuração aos usuários.</span><span class="sxs-lookup"><span data-stu-id="64ad7-130">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="64ad7-131">Impedir que um usuário use o app Skype for Business</span><span class="sxs-lookup"><span data-stu-id="64ad7-131">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="64ad7-132">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="64ad7-132">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="64ad7-133">Veja mais no cmdlet [New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)</span><span class="sxs-lookup"><span data-stu-id="64ad7-133">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="64ad7-134">Para conceder a nova política criada ao Amos Marble, execute:</span><span class="sxs-lookup"><span data-stu-id="64ad7-134">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="64ad7-135">Veja mais no cmdlet [Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)</span><span class="sxs-lookup"><span data-stu-id="64ad7-135">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="64ad7-136">Se você já criou uma política, pode usar o cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar a configuração aos usuários.</span><span class="sxs-lookup"><span data-stu-id="64ad7-136">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="64ad7-137">Impedir que um usuário faça chamadas IP usando um dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="64ad7-137">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="64ad7-138">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="64ad7-138">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="64ad7-139">Veja mais no cmdlet [New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)</span><span class="sxs-lookup"><span data-stu-id="64ad7-139">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="64ad7-140">Para conceder a nova política criada a todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="64ad7-140">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="64ad7-141">Veja mais no cmdlet [Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)</span><span class="sxs-lookup"><span data-stu-id="64ad7-141">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="64ad7-142">Se você já criou uma política, pode usar o cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para fazer alterações na política existente e usar o cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar a configuração aos usuários.</span><span class="sxs-lookup"><span data-stu-id="64ad7-142">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="64ad7-143">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="64ad7-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="64ad7-144">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="64ad7-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="64ad7-145">Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="64ad7-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="64ad7-146">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="64ad7-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="64ad7-147">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="64ad7-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="64ad7-148">Seis motivos pelos quais você pode querer usar o Windows PowerShell para gerenciar o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="64ad7-148">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="64ad7-149">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="64ad7-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="64ad7-150">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="64ad7-150">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="64ad7-151">Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="64ad7-151">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="64ad7-152">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="64ad7-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="64ad7-153">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="64ad7-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="64ad7-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="64ad7-154">Related topics</span></span>
[<span data-ttu-id="64ad7-155">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="64ad7-155">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="64ad7-156">Bloquear transferências de arquivo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="64ad7-156">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="64ad7-157">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="64ad7-157">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="64ad7-158">Configurar políticas de conferência em sua organização</span><span class="sxs-lookup"><span data-stu-id="64ad7-158">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
