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
ms.openlocfilehash: f5b420b9a5f288a0c733d3dfdc7ebc45fb323f32
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814750"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="89a7f-103">Configurar políticas de conferência para sua organização</span><span class="sxs-lookup"><span data-stu-id="89a7f-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="89a7f-104">Conferência é uma parte importante do Skype for Business Online: a conferência permite que grupos de usuários reúnam-se online para ver slides e vídeo, compartilhar aplicativos, trocar arquivos ou para comunicarem-se e colaborar.</span><span class="sxs-lookup"><span data-stu-id="89a7f-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="89a7f-p101">É importante manter o controle sobre as configurações de conferências e conferências. Em alguns casos, pode haver preocupações de segurança: por padrão, qualquer pessoa, incluindo usuários não autenticados, pode participar de reuniões e salvar qualquer um dos slides ou apostilas distribuídos durante essas reuniões. Além disso, pode haver preocupações legais ocasionais. Por exemplo, por padrão, os participantes da reunião podem fazer anotações sobre o conteúdo compartilhado; no entanto, essas anotações não são salvas quando a reunião é arquivada. Se sua organização for necessária para manter um registro de toda a comunicação eletrônica, talvez você queira desabilitar anotações.</span><span class="sxs-lookup"><span data-stu-id="89a7f-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="89a7f-p102">No Skype for Business Online, as conferências são gerenciadas usando políticas de conferência. As políticas de conferência determinam os recursos e recursos que podem ser usados em uma conferência, incluindo tudo, desde se a conferência pode ou não incluir áudio e vídeo IP até o número máximo de pessoas que podem participar de uma reunião. As políticas de conferência podem ser configuradas no escopo global ou no escopo por usuário. Isso fornece aos administradores uma flexibilidade enorme quando se trata de decidir quais recursos serão disponibilizados para quais usuários.</span><span class="sxs-lookup"><span data-stu-id="89a7f-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="89a7f-114">As configurações de política podem ser configuradas no momento em que uma política é criada ou você pode usar o cmdlet **Set-CsConferencingPolicy** para modificar as configurações de uma política existente.</span><span class="sxs-lookup"><span data-stu-id="89a7f-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="89a7f-115">Definir suas políticas de conferência</span><span class="sxs-lookup"><span data-stu-id="89a7f-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="89a7f-116">Para todas as configurações de política de conferência no Skype for Business Online, você deve usar o Windows PowerShell e não pode **usar** o Centro de **administração do Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="89a7f-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="89a7f-117">Verificar e iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89a7f-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="89a7f-118">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="89a7f-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="89a7f-119">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="89a7f-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="89a7f-120">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="89a7f-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="89a7f-p103">Se você não tiver a versão 3.0 ou superior, será necessário baixar e instalar atualizações para o Windows PowerShell. Confira [o Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="89a7f-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="89a7f-124">Você também precisará instalar o módulo do Windows PowerShell para Teams que permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="89a7f-124">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="89a7f-125">Se precisar saber mais, confira Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx)em uma única janela do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89a7f-125">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="89a7f-126">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="89a7f-126">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="89a7f-127">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="89a7f-127">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="89a7f-128">Na janela **do Windows PowerShell,** conecte-se ao Microsoft 365 ou ao Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="89a7f-128">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
        
     > [!NOTE]
     > <span data-ttu-id="89a7f-129">No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="89a7f-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
     >
     > <span data-ttu-id="89a7f-130">Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="89a7f-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="89a7f-131">Se quiser saber mais sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx) em uma única janela do Windows PowerShell ou Configurar seu computador para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="89a7f-131">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="89a7f-132">Bloquear transferências de arquivo e compartilhamento de área de trabalho durante as reuniões</span><span class="sxs-lookup"><span data-stu-id="89a7f-132">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="89a7f-133">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="89a7f-133">To create a new policy for these settings, run:</span></span>
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   <span data-ttu-id="89a7f-134">Veja mais no [cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)</span><span class="sxs-lookup"><span data-stu-id="89a7f-134">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="89a7f-135">Para conceder a nova política criada a todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="89a7f-135">To grant the new policy you created to all users in your organization, run:</span></span>
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   <span data-ttu-id="89a7f-136">Veja mais no [cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)</span><span class="sxs-lookup"><span data-stu-id="89a7f-136">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="89a7f-137">Se você já criou uma política, pode usar o cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) para fazer alterações na política existente e usar o cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) para aplicar as configurações aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="89a7f-137">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="89a7f-138">Bloquear a gravação de conferências e impedir participantes anônimos da reunião</span><span class="sxs-lookup"><span data-stu-id="89a7f-138">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="89a7f-139">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="89a7f-139">To create a new policy for these settings, run:</span></span> 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   <span data-ttu-id="89a7f-140">Veja mais no [cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)</span><span class="sxs-lookup"><span data-stu-id="89a7f-140">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="89a7f-141">Para conceder a nova política criada ao Amos Marble, execute:</span><span class="sxs-lookup"><span data-stu-id="89a7f-141">To grant the new policy you created to Amos Marble, run:</span></span>
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   <span data-ttu-id="89a7f-142">Veja mais no [cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)</span><span class="sxs-lookup"><span data-stu-id="89a7f-142">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="89a7f-143">Se você já criou uma política, pode usar o cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) para aplicar as configurações aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="89a7f-143">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="89a7f-144">Impedir que participantes anônimos gravem reuniões e que usuários externos salvem o conteúdo da reunião</span><span class="sxs-lookup"><span data-stu-id="89a7f-144">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="89a7f-145">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="89a7f-145">To create a new policy for these settings, run:</span></span>  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   <span data-ttu-id="89a7f-146">Veja mais no [cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)</span><span class="sxs-lookup"><span data-stu-id="89a7f-146">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="89a7f-147">Para conceder a nova política criada a todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="89a7f-147">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

<span data-ttu-id="89a7f-148">Veja mais no [cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)</span><span class="sxs-lookup"><span data-stu-id="89a7f-148">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="89a7f-149">Se você já criou uma política, pode usar o cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) para fazer alterações na política existente e usar o cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) para aplicar as configurações aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="89a7f-149">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="89a7f-150">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="89a7f-150">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="89a7f-151">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="89a7f-151">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="89a7f-152">Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="89a7f-152">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="89a7f-153">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="89a7f-153">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="89a7f-154">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="89a7f-154">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="89a7f-155">Seis motivos pelos quais você pode querer usar o Windows PowerShell para gerenciar o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="89a7f-155">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="89a7f-156">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="89a7f-156">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="89a7f-157">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="89a7f-157">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="89a7f-158">Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="89a7f-158">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="89a7f-159">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="89a7f-159">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="89a7f-160">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="89a7f-160">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="89a7f-161">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="89a7f-161">Related topics</span></span>
[<span data-ttu-id="89a7f-162">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="89a7f-162">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="89a7f-163">Bloquear transferências de arquivo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="89a7f-163">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="89a7f-164">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="89a7f-164">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 
