---
title: Configurar políticas de conferência para sua organização
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
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
description: 'Conferência é uma parte importante do Skype for Business Online: a conferência permite que grupos de usuários reúnam-se online para ver slides e vídeo, compartilhar aplicativos, trocar arquivos ou para comunicarem-se e colaborar.'
ms.openlocfilehash: 84037d571bf6f9dc3451793678a6d1b650492bd9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240073"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="cd31a-103">Configurar políticas de conferência para sua organização</span><span class="sxs-lookup"><span data-stu-id="cd31a-103">Set up conferencing policies for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="cd31a-104">Conferência é uma parte importante do Skype for Business Online: a conferência permite que grupos de usuários reúnam-se online para ver slides e vídeo, compartilhar aplicativos, trocar arquivos ou para comunicarem-se e colaborar.</span><span class="sxs-lookup"><span data-stu-id="cd31a-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="cd31a-105">É importante que você mantenha o controle das conferências e de suas configurações.</span><span class="sxs-lookup"><span data-stu-id="cd31a-105">It's important for you to maintain control over conferences and conference settings.</span></span> <span data-ttu-id="cd31a-106">Em alguns casos, pode haver preocupação em termos de segurança: por padrão, qualquer pessoa, incluindo usuários não autenticados, pode participar de reuniões e salvar quaisquer slides ou folhetos distribuídos durante aquelas reuniões.</span><span class="sxs-lookup"><span data-stu-id="cd31a-106">In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings.</span></span> <span data-ttu-id="cd31a-107">Além disso, podem ocorrer preocupações legais ocasionais.</span><span class="sxs-lookup"><span data-stu-id="cd31a-107">In addition, there might be occasional legal concerns.</span></span> <span data-ttu-id="cd31a-108">Por exemplo, por padrão, os participantes da reunião têm permissão para fazer anotações em conteúdo compartilhado; no entanto, essas anotações não são salvas quando a reunião é arquivada.</span><span class="sxs-lookup"><span data-stu-id="cd31a-108">For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived.</span></span> <span data-ttu-id="cd31a-109">Se sua organização precisar manter um registro de toda a comunicação eletrônica, talvez você queira desabilitar as anotações.</span><span class="sxs-lookup"><span data-stu-id="cd31a-109">If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="cd31a-110">No Skype for Business Online, as conferências são gerenciadas usando políticas de conferência.</span><span class="sxs-lookup"><span data-stu-id="cd31a-110">In Skype for Business Online, conferences are managed by using conferencing policies.</span></span> <span data-ttu-id="cd31a-111">As políticas de conferência determinam os recursos e as capacidades que podem ser usados em uma conferência, incluindo tudo desde se a conferência pode ou não incluir áudio e vídeo IP até o número máximo de pessoas que podem participar de uma reunião.</span><span class="sxs-lookup"><span data-stu-id="cd31a-111">Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting.</span></span> <span data-ttu-id="cd31a-112">Essas políticas podem ser configuradas no escopo global ou no escopo por uso.</span><span class="sxs-lookup"><span data-stu-id="cd31a-112">Conferencing policies can be configured at the global scope or at the per-user scope.</span></span> <span data-ttu-id="cd31a-113">Isso fornece aos administradores uma flexibilidade enorme no que diz respeito a decidir quais capacidades serão disponibilizadas para quais usuários.</span><span class="sxs-lookup"><span data-stu-id="cd31a-113">This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="cd31a-114">As configurações de política podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **Set-CsConferencingPolicy** para modificar as configurações de uma política existente.</span><span class="sxs-lookup"><span data-stu-id="cd31a-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="cd31a-115">Definir suas políticas de conferência</span><span class="sxs-lookup"><span data-stu-id="cd31a-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="cd31a-116">Para todas as configurações de política de conferência no Skype for Business Online, você  deve usar o Windows PowerShell e não pode usar o centro de administração **Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="cd31a-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 

### <a name="start-windows-powershell"></a><span data-ttu-id="cd31a-117">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd31a-117">Start Windows PowerShell</span></span>

 > [!Note]
> <span data-ttu-id="cd31a-118">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="cd31a-118">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="cd31a-119">Se você estiver usando o último lançamento público do PowerShell Teams, não precisa instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="cd31a-119">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="cd31a-120">Instale o [módulo Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="cd31a-120">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="cd31a-121">Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="cd31a-121">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module 
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="cd31a-122">Se você quiser mais informações sobre como iniciar Windows PowerShell, consulte Conexão para todos os serviços Microsoft 365 ou [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="cd31a-122">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="cd31a-123">Bloquear transferências de arquivo e compartilhamento de área de trabalho durante as reuniões</span><span class="sxs-lookup"><span data-stu-id="cd31a-123">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="cd31a-124">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="cd31a-124">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="cd31a-125">Consulte mais no cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="cd31a-125">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="cd31a-126">Para conceder a nova política criada a todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="cd31a-126">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="cd31a-127">Consulte mais no cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="cd31a-127">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
  <span data-ttu-id="cd31a-128">Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) para aplicar as configurações aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="cd31a-128">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="cd31a-129">Bloquear o registro de conferências e impedir participantes de reuniões anônimas</span><span class="sxs-lookup"><span data-stu-id="cd31a-129">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="cd31a-130">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="cd31a-130">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="cd31a-131">Consulte mais no cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="cd31a-131">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="cd31a-132">Para conceder a nova política criada para o Amos Marble, execute:</span><span class="sxs-lookup"><span data-stu-id="cd31a-132">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="cd31a-133">Consulte mais no cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="cd31a-133">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
<span data-ttu-id="cd31a-134">Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) para aplicar as configurações aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="cd31a-134">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="cd31a-135">Impedir que participantes anônimos gravem reuniões e que usuários externos salvem o conteúdo da reunião</span><span class="sxs-lookup"><span data-stu-id="cd31a-135">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="cd31a-136">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="cd31a-136">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="cd31a-137">Consulte mais no cmdlet [New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="cd31a-137">See more on the [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet.</span></span>
    
- <span data-ttu-id="cd31a-138">Para conceder a nova política criada a todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="cd31a-138">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="cd31a-139">Consulte mais no cmdlet [Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)</span><span class="sxs-lookup"><span data-stu-id="cd31a-139">See more on the [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet.</span></span>
    
<span data-ttu-id="cd31a-140">Se você já tiver criado uma política, poderá usar o cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) para fazer alterações na política existente e, em seguida, usar o cmdlet[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) para aplicar as configurações aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="cd31a-140">If you have already created a policy, you can use the [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="cd31a-141">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="cd31a-141">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="cd31a-142">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="cd31a-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="cd31a-143">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 e Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="cd31a-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="cd31a-144">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="cd31a-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cd31a-145">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cd31a-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="cd31a-146">Seis motivos pelos quais você pode querer usar Windows PowerShell gerenciar Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="cd31a-146">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="cd31a-147">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="cd31a-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="cd31a-148">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="cd31a-148">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="cd31a-149">[Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="cd31a-149">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="cd31a-150">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cd31a-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="cd31a-151">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cd31a-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="cd31a-152">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cd31a-152">Related topics</span></span>
[<span data-ttu-id="cd31a-153">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="cd31a-153">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="cd31a-154">Bloquear transferências de arquivo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="cd31a-154">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="cd31a-155">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="cd31a-155">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
