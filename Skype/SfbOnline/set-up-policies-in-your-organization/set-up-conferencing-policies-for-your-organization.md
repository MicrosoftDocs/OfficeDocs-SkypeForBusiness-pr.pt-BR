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
f1keywords: None
ms.custom:
- Setup
description: 'Conferência é uma parte importante do Skype for Business Online: a conferência permite que grupos de usuários reúnam-se online para ver slides e vídeo, compartilhar aplicativos, trocar arquivos ou para comunicarem-se e colaborar.'
ms.openlocfilehash: 43c441e769622fcf5f292329c460c7c662619ee1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297704"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a><span data-ttu-id="6b176-103">Configurar políticas de conferência para sua organização</span><span class="sxs-lookup"><span data-stu-id="6b176-103">Set up conferencing policies for your organization</span></span>

<span data-ttu-id="6b176-104">Conferência é uma parte importante do Skype for Business Online: a conferência permite que grupos de usuários reúnam-se online para ver slides e vídeo, compartilhar aplicativos, trocar arquivos ou para comunicarem-se e colaborar.</span><span class="sxs-lookup"><span data-stu-id="6b176-104">Conferencing is an important part of Skype for Business Online: conferencing enables groups of users to come together online to view slides and video, share applications, exchange files, and otherwise communicate and collaborate.</span></span>
  
<span data-ttu-id="6b176-p101">É importante manter o controle das configurações de conferência e conferências. Em alguns casos, pode haver problemas de segurança: por padrão, qualquer pessoa, incluindo usuários não autenticados, pode participar de reuniões e salvar qualquer slide ou folheto distribuído durante essas reuniões. Além disso, pode haver preocupações legais ocasionais. Por exemplo, por padrão, os participantes da reunião podem fazer anotações em conteúdo compartilhado; no entanto, essas anotações não são salvas quando a reunião é arquivada. Se a sua organização for necessária para manter um registro de todas as comunicações eletrônicas, talvez você queira desativar as anotações.</span><span class="sxs-lookup"><span data-stu-id="6b176-p101">It's important for you to maintain control over conferences and conference settings. In some cases, there might be security concerns: by default, anyone, including unauthenticated users, can participate in meetings and save any of the slides or handouts distributed during those meetings. In addition, there might be occasional legal concerns. For example, by default ,meeting participants are allowed to make annotations on shared content; however, these annotations are not saved when the meeting is archived. If your organization is required to keep a record of all electronic communication, you might want to disable annotations.</span></span> 
  
<span data-ttu-id="6b176-p102">No Skype for Business Online, as conferências são gerenciadas usando políticas de conferência. As políticas de conferência determinam os recursos e as funcionalidades que podem ser usados em uma conferência, incluindo o fato de que a conferência pode ou não ter áudio e vídeo IP para o número máximo de pessoas que podem participar de uma reunião. As políticas de conferência podem ser configuradas no escopo global ou no escopo por usuário. Isso proporciona aos administradores uma enorme flexibilidade quando se trata de decidir quais recursos serão disponibilizados para os usuários.</span><span class="sxs-lookup"><span data-stu-id="6b176-p102">In Skype for Business Online, conferences are managed by using conferencing policies. Conferencing policies determine the features and capabilities that can be used in a conference, including everything from whether or not the conference can include IP audio and video to the maximum number of people who can attend a meeting. Conferencing policies can be configured at the global scope or at the per-user scope. This provides administrators with enormous flexibility when it comes to deciding which capabilities will be made available to which users.</span></span>
  
<span data-ttu-id="6b176-114">As configurações de política podem ser definidas no momento em que uma política é criada ou você pode usar o cmdlet **set-CsConferencingPolicy** para modificar as configurações de uma política existente.</span><span class="sxs-lookup"><span data-stu-id="6b176-114">Policy settings can be configured at the time a policy is created, or you can use the **Set-CsConferencingPolicy** cmdlet to modify the settings of an existing policy.</span></span>
  
## <a name="set-your-conferencing-policies"></a><span data-ttu-id="6b176-115">Definir suas políticas de conferência</span><span class="sxs-lookup"><span data-stu-id="6b176-115">Set your conferencing policies</span></span>

> [!NOTE]
> <span data-ttu-id="6b176-116">Para todas as configurações de política de conferência no Skype for Business Online, você deve usar o Windows PowerShell e **não pode usar** o **centro de administração do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="6b176-116">For all of the conferencing policy settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="6b176-117">Verificar e iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b176-117">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="6b176-118">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="6b176-118">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="6b176-119">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6b176-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6b176-120">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6b176-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="6b176-p103">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="6b176-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="6b176-p104">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="6b176-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="6b176-127">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="6b176-127">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="6b176-128">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6b176-128">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="6b176-129">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6b176-129">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6b176-130">Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="6b176-130">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6b176-131">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="6b176-131">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="6b176-132">Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6b176-132">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a><span data-ttu-id="6b176-133">Bloquear transferências de arquivo e compartilhamento de área de trabalho durante as reuniões</span><span class="sxs-lookup"><span data-stu-id="6b176-133">Block file transfers and desktop sharing during meetings</span></span>

- <span data-ttu-id="6b176-134">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="6b176-134">To create a new policy for these settings, run:</span></span>
  > 
  > ```
  > New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  > ```
  > <span data-ttu-id="6b176-135">Veja mais no cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6b176-135">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="6b176-136">Para conceder a nova política criada para todos os usuários em sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="6b176-136">To grant the new policy you created to all users in your organization, run:</span></span>
  > 
  > ```
  > Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  > ```
  > <span data-ttu-id="6b176-137">Veja mais no cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6b176-137">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
  <span data-ttu-id="6b176-138">Se você já tiver criado uma política, poderá usar o cmdlet [set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para fazer alterações na política existente e usar o cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar as configurações aos usuários.</span><span class="sxs-lookup"><span data-stu-id="6b176-138">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a><span data-ttu-id="6b176-139">Bloquear a gravação de conferências e evitar participantes de reuniões anônimos</span><span class="sxs-lookup"><span data-stu-id="6b176-139">Block recording of conferences and prevent anonymous meeting participants</span></span>

- <span data-ttu-id="6b176-140">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="6b176-140">To create a new policy for these settings, run:</span></span> 
  > 
  > ```
  > New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  > ```
  > <span data-ttu-id="6b176-141">Veja mais no cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6b176-141">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="6b176-142">Para conceder a nova política criada para o Marble Amos, execute:</span><span class="sxs-lookup"><span data-stu-id="6b176-142">To grant the new policy you created to Amos Marble, run:</span></span>
  > 
  > ```
  >  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  > ```
  > <span data-ttu-id="6b176-143">Veja mais no cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6b176-143">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="6b176-144">Se você já tiver criado uma política, poderá usar o cmdlet [set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para fazer alterações na política existente e usar o cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar as configurações aos usuários.</span><span class="sxs-lookup"><span data-stu-id="6b176-144">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a><span data-ttu-id="6b176-145">Impedir que participantes anônimos gravem reuniões e que usuários externos salvem o conteúdo da reunião</span><span class="sxs-lookup"><span data-stu-id="6b176-145">Block anonymous participants from recording meetings and external users from saving meeting content</span></span>

- <span data-ttu-id="6b176-146">Para criar uma nova política para essas configurações, execute:</span><span class="sxs-lookup"><span data-stu-id="6b176-146">To create a new policy for these settings, run:</span></span>  
  > 
  > ```
  > New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  > ```
  > <span data-ttu-id="6b176-147">Veja mais no cmdlet [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6b176-147">See more on the [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet.</span></span>
    
- <span data-ttu-id="6b176-148">Para conceder a nova política criada para todos os usuários de sua organização, execute:</span><span class="sxs-lookup"><span data-stu-id="6b176-148">To grant the new policy you created to all of the users in your organization, run:</span></span>
    
> 
>   ```
>   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
>   ```

<span data-ttu-id="6b176-149">Veja mais no cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .</span><span class="sxs-lookup"><span data-stu-id="6b176-149">See more on the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet.</span></span>
    
<span data-ttu-id="6b176-150">Se você já tiver criado uma política, poderá usar o cmdlet [set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) para fazer alterações na política existente e usar o cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) para aplicar as configurações aos usuários.</span><span class="sxs-lookup"><span data-stu-id="6b176-150">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet to apply the settings to your users.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6b176-151">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6b176-151">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="6b176-152">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="6b176-152">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6b176-153">Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="6b176-153">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="6b176-154">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="6b176-154">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6b176-155">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6b176-155">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="6b176-156">Seis motivos para usar o Windows PowerShell para gerenciar o Office 365 </span><span class="sxs-lookup"><span data-stu-id="6b176-156">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="6b176-p106">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="6b176-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="6b176-159">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b176-159">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="6b176-160">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6b176-160">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="6b176-161">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6b176-161">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="6b176-162">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6b176-162">Related topics</span></span>
[<span data-ttu-id="6b176-163">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="6b176-163">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="6b176-164">Bloquear transferências de arquivo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="6b176-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="6b176-165">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="6b176-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

  
 
