---
title: "Configurar políticas de celular para sua organização"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: "Você pode configurar o como os usuários se conectam à Skype para Business Online usando o Skype para aplicativos de negócios em dispositivos móveis, como um recurso que permite que os usuários façam e recebam chamadas telefônicas em seu telefone móvel usando seu número de telefone de trabalho em vez de nu seu telefone celular número. As políticas de mobilidade também podem ser usadas para requerer conexões Wi-Fi ao fazer ou receber chamadas."
ms.openlocfilehash: 904da369a4218b0b41112c97a1fed9de03c47c3b
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="7a2b7-104">Configurar políticas de celular para sua organização</span><span class="sxs-lookup"><span data-stu-id="7a2b7-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="7a2b7-105">Você pode configurar o como os usuários se conectam à Skype para Business Online usando o Skype para aplicativos de negócios em dispositivos móveis, como um recurso que permite que os usuários façam e recebam chamadas telefônicas em seu telefone móvel usando seu número de telefone de trabalho em vez de nu seu telefone celular número.</span><span class="sxs-lookup"><span data-stu-id="7a2b7-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="7a2b7-106">As políticas de mobilidade também podem ser usadas para requerer conexões Wi-Fi ao fazer ou receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="7a2b7-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="7a2b7-107">Configurações de diretiva móveis podem ser configuradas no momento em que uma diretiva é criada ou você pode usar o cmdlet **Set-CsMobilityPolicy** para modificar as configurações de uma diretiva existente.</span><span class="sxs-lookup"><span data-stu-id="7a2b7-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="7a2b7-108">Definir suas políticas de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="7a2b7-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="7a2b7-109">Para todas as configurações de diretiva móvel no Skype para Business Online, você deve usar o Windows PowerShell e você **não pode usar** o **Skype para centro de administração de negócios**.</span><span class="sxs-lookup"><span data-stu-id="7a2b7-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="7a2b7-110">Verificar e iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a2b7-110">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="7a2b7-111">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="7a2b7-111">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="7a2b7-112">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7a2b7-112">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="7a2b7-113">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7a2b7-113">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="7a2b7-p103">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="7a2b7-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="7a2b7-p104">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="7a2b7-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="7a2b7-120">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="7a2b7-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="7a2b7-121">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="7a2b7-121">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="7a2b7-122">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7a2b7-122">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="7a2b7-123">Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="7a2b7-123">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7a2b7-124">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="7a2b7-124">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="7a2b7-125">Se você quiser obter mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Conectando-se ao Skype para negócios Online usando o Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="7a2b7-125">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="7a2b7-126">Requerer uma conexão WiFi para vídeo para um usuário</span><span class="sxs-lookup"><span data-stu-id="7a2b7-126">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="7a2b7-127">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="7a2b7-127">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```
  <span data-ttu-id="7a2b7-128">Consulte obter mais informações sobre o cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7a2b7-128">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="7a2b7-129">Para conceder a nova política que você criou para todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="7a2b7-129">To grant the new policy you created to all of the users in your organization, run:</span></span>
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```
  <span data-ttu-id="7a2b7-130">Consulte obter mais informações sobre o cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7a2b7-130">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="7a2b7-131">Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) para fazer alterações à diretiva existente e, em seguida, use o cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) para aplicar a configuração para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="7a2b7-131">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="7a2b7-132">Impedir que um usuário use o app Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7a2b7-132">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="7a2b7-133">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="7a2b7-133">To create a new policy for these settings, run:</span></span>
```
New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
```
  <span data-ttu-id="7a2b7-134">Consulte obter mais informações sobre o cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7a2b7-134">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="7a2b7-135">Para conceder a nova política que você criou para Mármore Amos, execute:</span><span class="sxs-lookup"><span data-stu-id="7a2b7-135">To grant the new policy you created to Amos Marble, run:</span></span>  
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```
  <span data-ttu-id="7a2b7-136">Consulte obter mais informações sobre o cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7a2b7-136">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="7a2b7-137">Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) para fazer alterações à diretiva existente e, em seguida, use o cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) para aplicar a configuração para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="7a2b7-137">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="7a2b7-138">Impedir que um usuário faça chamadas IP usando um dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="7a2b7-138">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="7a2b7-139">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="7a2b7-139">To create a new policy for these settings, run:</span></span>
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```
  <span data-ttu-id="7a2b7-140">Consulte obter mais informações sobre o cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7a2b7-140">See more on the [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="7a2b7-141">Para conceder a nova política que você criou para todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="7a2b7-141">To grant the new policy you created to all of the users in your organization, run:</span></span>
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

  <span data-ttu-id="7a2b7-142">Consulte obter mais informações sobre o cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .</span><span class="sxs-lookup"><span data-stu-id="7a2b7-142">See more on the [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet.</span></span>
    
<span data-ttu-id="7a2b7-143">Se você já tiver criado uma política, você pode usar o cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) para fazer alterações à diretiva existente e, em seguida, use o cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) para aplicar a configuração para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="7a2b7-143">If you have already created a policy, you can use the [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7a2b7-144">Quer saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7a2b7-144">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="7a2b7-p105">O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="7a2b7-p105">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7a2b7-148">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7a2b7-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="7a2b7-149">Seis motivos para usar o Windows PowerShell para gerenciar o Office 365 </span><span class="sxs-lookup"><span data-stu-id="7a2b7-149">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="7a2b7-p106">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="7a2b7-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="7a2b7-152">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7a2b7-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="7a2b7-153">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7a2b7-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7a2b7-154">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7a2b7-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="7a2b7-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7a2b7-155">Related topics</span></span>
[<span data-ttu-id="7a2b7-156">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="7a2b7-156">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="7a2b7-157">Transferências de arquivos ponto a ponto de bloqueio</span><span class="sxs-lookup"><span data-stu-id="7a2b7-157">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="7a2b7-158">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="7a2b7-158">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="7a2b7-159">Configurar políticas de conferência na sua organização</span><span class="sxs-lookup"><span data-stu-id="7a2b7-159">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

