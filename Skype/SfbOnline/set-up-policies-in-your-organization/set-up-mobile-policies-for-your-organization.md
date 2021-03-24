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
description: Você pode configurar como seus usuários se conectam ao Skype for Business Online usando o aplicativo Skype for Business em dispositivos móveis, como um recurso que permite que os usuários façam e recebam chamadas telefônicas no celular usando o número de telefone comercial em vez do número de telefone celular. As políticas de mobilidade também podem ser usadas para requerer conexões Wi-Fi ao fazer ou receber chamadas.
ms.openlocfilehash: b0e2f7524f300733840159eacfcf27bb54f5e815
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100487"
---
# <a name="set-up-mobile-policies-for-your-organization"></a><span data-ttu-id="9cd3a-104">Configurar políticas móveis para sua organização</span><span class="sxs-lookup"><span data-stu-id="9cd3a-104">Set up mobile policies for your organization</span></span>

<span data-ttu-id="9cd3a-105">Você pode configurar como seus usuários se conectam ao Skype for Business Online usando o aplicativo Skype for Business em dispositivos móveis, como um recurso que permite que os usuários façam e recebam chamadas telefônicas no celular usando o número de telefone comercial em vez do número de telefone celular.</span><span class="sxs-lookup"><span data-stu-id="9cd3a-105">You can set up how your users connect to Skype for Business Online using the Skype for Business app on mobile devices, such as a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number.</span></span> <span data-ttu-id="9cd3a-106">As políticas de mobilidade também podem ser usadas para requerer conexões Wi-Fi ao fazer ou receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="9cd3a-106">Mobility policies can also be used to require Wi-Fi connections when making or receiving calls.</span></span>
  
<span data-ttu-id="9cd3a-107">As configurações de política móvel podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **Set-CsMobilityPolicy** para modificar as configurações de uma política existente.</span><span class="sxs-lookup"><span data-stu-id="9cd3a-107">Mobile policy settings can be configured at the time a policy is created, or you can use the **Set-CsMobilityPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-mobile-policies"></a><span data-ttu-id="9cd3a-108">Definir suas políticas de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="9cd3a-108">Set your mobile policies</span></span>

> [!NOTE]
> <span data-ttu-id="9cd3a-109">Para todas as configurações de política móvel no Skype for Business Online, você deve usar o Windows PowerShell e não **pode usar** o Centro de administração do Skype **for Business.**</span><span class="sxs-lookup"><span data-stu-id="9cd3a-109">For all of the mobile policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="9cd3a-110">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cd3a-110">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="9cd3a-111">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="9cd3a-111">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="9cd3a-112">Se você estiver usando o último lançamento público do PowerShell Teams, não precisa instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="9cd3a-112">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="9cd3a-113">Instale o [módulo do Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="9cd3a-113">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="9cd3a-114">Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="9cd3a-114">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="9cd3a-115">Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="9cd3a-115">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a><span data-ttu-id="9cd3a-116">Requerer uma conexão WiFi para vídeo para um usuário</span><span class="sxs-lookup"><span data-stu-id="9cd3a-116">Require a WiFi connection for video for a user</span></span>

- <span data-ttu-id="9cd3a-117">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="9cd3a-117">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   <span data-ttu-id="9cd3a-118">Consulte mais no cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="9cd3a-118">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="9cd3a-119">Para conceder a nova política criada a todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="9cd3a-119">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   <span data-ttu-id="9cd3a-120">Consulte mais no cmdlet [Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="9cd3a-120">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="9cd3a-121">Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) para aplicar a configuração aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="9cd3a-121">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a><span data-ttu-id="9cd3a-122">Impedir que um usuário use o app Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9cd3a-122">Prevent a user from using the Skype for Business app</span></span>

- <span data-ttu-id="9cd3a-123">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="9cd3a-123">To create a new policy for these settings, run:</span></span>
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  <span data-ttu-id="9cd3a-124">Consulte mais no cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="9cd3a-124">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="9cd3a-125">Para conceder a nova política criada para o Amos Marble, execute:</span><span class="sxs-lookup"><span data-stu-id="9cd3a-125">To grant the new policy you created to Amos Marble, run:</span></span>  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   <span data-ttu-id="9cd3a-126">Consulte mais no cmdlet [Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="9cd3a-126">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="9cd3a-127">Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) para aplicar a configuração aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="9cd3a-127">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a><span data-ttu-id="9cd3a-128">Impedir que um usuário faça chamadas IP usando um dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="9cd3a-128">Prevent a user from making voice over IP calls using a mobile device</span></span>

- <span data-ttu-id="9cd3a-129">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="9cd3a-129">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   <span data-ttu-id="9cd3a-130">Consulte mais no cmdlet [New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="9cd3a-130">See more on the [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="9cd3a-131">Para conceder a nova política criada a todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="9cd3a-131">To grant the new policy you created to all of the users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  <span data-ttu-id="9cd3a-132">Consulte mais no cmdlet [Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)</span><span class="sxs-lookup"><span data-stu-id="9cd3a-132">See more on the [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet.</span></span>
    
<span data-ttu-id="9cd3a-133">Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) para aplicar a configuração aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="9cd3a-133">If you have already created a policy, you can use the [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet to apply the setting to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9cd3a-134">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9cd3a-134">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="9cd3a-135">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="9cd3a-135">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9cd3a-136">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="9cd3a-136">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="9cd3a-137">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="9cd3a-137">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9cd3a-138">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9cd3a-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="9cd3a-139">Seis motivos pelos quais você pode querer usar o Windows PowerShell gerenciar o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="9cd3a-139">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="9cd3a-140">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="9cd3a-140">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="9cd3a-141">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="9cd3a-141">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="9cd3a-142">[Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9cd3a-142">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="9cd3a-143">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9cd3a-143">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="9cd3a-144">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9cd3a-144">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="9cd3a-145">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9cd3a-145">Related topics</span></span>
[<span data-ttu-id="9cd3a-146">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="9cd3a-146">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="9cd3a-147">Bloquear transferências de arquivo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="9cd3a-147">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="9cd3a-148">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="9cd3a-148">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="9cd3a-149">Configurar políticas de conferência em sua organização</span><span class="sxs-lookup"><span data-stu-id="9cd3a-149">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
