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
ms.openlocfilehash: 3706e6b4fafe15aa8b799170001af61b837968da
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100527"
---
# <a name="set-up-client-policies-for-your-organization"></a><span data-ttu-id="d88d5-103">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="d88d5-103">Set up client policies for your organization</span></span>

<span data-ttu-id="d88d5-104">A ajuda de políticas de cliente determina os recursos do Skype for Business Online que são disponibilizados para os usuários; por exemplo, você pode dar a alguns usuários o direito de transferir arquivos enquanto nega este direito a outros usuários.</span><span class="sxs-lookup"><span data-stu-id="d88d5-104">Client policies help determine the features of Skype for Business Online that are made available to users; for example, you might give some users the right to transfer files while denying this right to other users.</span></span>
  
<span data-ttu-id="d88d5-105">As configurações de política de cliente podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **Set-CsClientPolicy** para modificar as configurações de uma política existente.</span><span class="sxs-lookup"><span data-stu-id="d88d5-105">Client policy settings can be configured at the time a policy is created, or you can use the **Set-CsClientPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-client-policies"></a><span data-ttu-id="d88d5-106">Definir suas políticas de cliente</span><span class="sxs-lookup"><span data-stu-id="d88d5-106">Set your client policies</span></span>

> [!NOTE]
> <span data-ttu-id="d88d5-107">Para todas as configurações de política de cliente no Skype for Business Online, você deve usar o Windows PowerShell e não pode **usar** o Centro de **administração do Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="d88d5-107">For all of the client policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="start-windows-powershell"></a><span data-ttu-id="d88d5-108">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d88d5-108">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="d88d5-109">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="d88d5-109">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="d88d5-110">Se você estiver usando o último lançamento público do PowerShell Teams, não precisa instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="d88d5-110">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="d88d5-111">Instale o [módulo do Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="d88d5-111">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="d88d5-112">Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="d88d5-112">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="d88d5-113">Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="d88d5-113">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a><span data-ttu-id="d88d5-114">Desabilitar emoticons e notificações de presença e impedir a economia de IMs</span><span class="sxs-lookup"><span data-stu-id="d88d5-114">Disable emoticons and presence notifications and prevent saving of IMs</span></span>

- <span data-ttu-id="d88d5-115">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="d88d5-115">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  <span data-ttu-id="d88d5-116">Consulte mais no cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="d88d5-116">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="d88d5-117">Para conceder a nova política criada a todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="d88d5-117">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  <span data-ttu-id="d88d5-118">Consulte mais no cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="d88d5-118">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="d88d5-119">Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) para aplicar as configurações aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="d88d5-119">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a><span data-ttu-id="d88d5-120">Habilitar URLs ou hyperlinks para tornarem-se clicáveis nas mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="d88d5-120">Enable URLs or hyperlinks to be clickable in IMs</span></span>

- <span data-ttu-id="d88d5-121">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="d88d5-121">To create a new policy for these settings, run:</span></span>
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  <span data-ttu-id="d88d5-122">Consulte mais no cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="d88d5-122">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="d88d5-123">Para conceder a nova política criada a todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="d88d5-123">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  <span data-ttu-id="d88d5-124">Consulte mais no cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="d88d5-124">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
<span data-ttu-id="d88d5-125">Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) para aplicar as configurações aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="d88d5-125">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="prevent-showing-recent-contacts"></a><span data-ttu-id="d88d5-126">Impedir a exibição de contatos recentes</span><span class="sxs-lookup"><span data-stu-id="d88d5-126">Prevent showing recent contacts</span></span>

- <span data-ttu-id="d88d5-127">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="d88d5-127">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  <span data-ttu-id="d88d5-128">Consulte mais no cmdlet [New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="d88d5-128">See more on the [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="d88d5-129">Para conceder a nova política criada para o Amos Marble, execute:</span><span class="sxs-lookup"><span data-stu-id="d88d5-129">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  <span data-ttu-id="d88d5-130">Consulte mais no cmdlet [Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)</span><span class="sxs-lookup"><span data-stu-id="d88d5-130">See more on the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="d88d5-131">Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) para aplicar as configurações aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="d88d5-131">If you have already created a policy, you can use the [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d88d5-132">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d88d5-132">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="d88d5-133">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="d88d5-133">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d88d5-134">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="d88d5-134">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="d88d5-135">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="d88d5-135">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d88d5-136">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d88d5-136">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="d88d5-137">Seis motivos pelos quais você pode querer usar o Windows PowerShell gerenciar o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="d88d5-137">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="d88d5-138">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="d88d5-138">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d88d5-139">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="d88d5-139">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="d88d5-140">[Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="d88d5-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="d88d5-141">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d88d5-141">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="d88d5-142">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d88d5-142">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="d88d5-143">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d88d5-143">Related topics</span></span>
[<span data-ttu-id="d88d5-144">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="d88d5-144">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="d88d5-145">Bloquear transferências de arquivo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="d88d5-145">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="d88d5-146">Configurar políticas de conferência em sua organização</span><span class="sxs-lookup"><span data-stu-id="d88d5-146">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
