---
title: Habilitar ou desabilitar o envio de emails quando as configurações de AudioConferência mudarem no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 681a02fd410c008f46ad7906c5963660df668a89
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164260"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="ea270-103">Habilitar ou desabilitar o envio de emails quando as configurações de AudioConferência mudarem no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ea270-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="ea270-104">Se você quiser habilitar ou desabilitar o envio de emails no Microsoft Teams, consulte Habilitar ou desabilitar o envio de emails quando as configurações [de Audioconferência mudarem no Microsoft Teams.](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)</span><span class="sxs-lookup"><span data-stu-id="ea270-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="ea270-105">Os usuários são notificados automaticamente por email quando estão habilitados para Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="ea270-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="ea270-106">No entanto, pode haver ocasiões em que você queira reduzir o número de emails enviados para usuários do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ea270-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="ea270-107">Nesses casos, você pode desabilitar o envio de emails.</span><span class="sxs-lookup"><span data-stu-id="ea270-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="ea270-108">Se você desabilitar o envio de emails, os emails de Audioconferência não serão enviados para seus usuários, incluindo emails para quando os usuários estão habilitados ou desabilitados para audioconferência, quando o PIN é redefinido e quando a ID de conferência e o número de telefone de conferência padrão mudam.</span><span class="sxs-lookup"><span data-stu-id="ea270-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="ea270-109">Aqui está um exemplo de email que é enviado aos usuários quando eles estão habilitados para Audioconferência:</span><span class="sxs-lookup"><span data-stu-id="ea270-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Email de audioconferência](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="ea270-111">Quando os emails são enviados para seus usuários?</span><span class="sxs-lookup"><span data-stu-id="ea270-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="ea270-112">Há vários emails enviados para os usuários em sua organização depois que eles são habilitados para audioconferência:</span><span class="sxs-lookup"><span data-stu-id="ea270-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="ea270-113">Quando uma **licença de Audioconferência** é atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="ea270-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="ea270-114">Quando você redefine manualmente o PIN de audioconferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="ea270-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="ea270-115">Quando você redefine manualmente o ID de conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="ea270-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="ea270-116">Quando a **licença de Audioconferência** é removida delas.</span><span class="sxs-lookup"><span data-stu-id="ea270-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="ea270-117">Quando o provedor de audioconferência de um usuário é alterado da Microsoft para outro provedor ou **Nenhum.**</span><span class="sxs-lookup"><span data-stu-id="ea270-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="ea270-118">Quando o provedor de audioconferência de um usuário é alterado para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ea270-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="ea270-119">Habilitar ou desabilitar o envio de emails aos usuários</span><span class="sxs-lookup"><span data-stu-id="ea270-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="ea270-120">Você pode usar o Centro de administração do Skype for Business ou o Windows PowerShell para habilitar ou desabilitar os emails enviados aos usuários.</span><span class="sxs-lookup"><span data-stu-id="ea270-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="ea270-121">![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="ea270-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="ea270-122">No Centro **de administração do Skype for Business,** na navegação à esquerda, clique em **Audioconferência.**</span><span class="sxs-lookup"><span data-stu-id="ea270-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="ea270-123">Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.</span><span class="sxs-lookup"><span data-stu-id="ea270-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="ea270-124">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ea270-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ea270-125">Você também pode enviar emails para um usuário com as configurações de audioconferência indo para Usuários de Audioconferência, selecionando o usuário e clicando em Enviar informações de conferência  >   **por email.**</span><span class="sxs-lookup"><span data-stu-id="ea270-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="ea270-126">Se você fizer isso, um email será enviado que inclua apenas a ID de conferência e o número de telefone de conferência, mas não o PIN.</span><span class="sxs-lookup"><span data-stu-id="ea270-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="ea270-127">Consulte [Enviar um email para um usuário com suas informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ea270-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="ea270-128">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ea270-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="ea270-129">Execute o seguinte para desabilitar o envio de emails:</span><span class="sxs-lookup"><span data-stu-id="ea270-129">Run the following to disable sending emails:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="ea270-130">Para ajuda com esse cmdlet, consulte [Set-CsOnlineDialInConferencingTenantSettings.](https://go.microsoft.com/fwlink/?LinkId=715757)</span><span class="sxs-lookup"><span data-stu-id="ea270-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="ea270-131">O que mais você deve saber?</span><span class="sxs-lookup"><span data-stu-id="ea270-131">What else should you know?</span></span>

- <span data-ttu-id="ea270-132">Quando emails automáticos são desabilitados, você ainda pode disparar manualmente o envio de um email com a ID de conferência e o número de telefone usando o Centro de administração do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ea270-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="ea270-133">No entanto, se você fizer isso, o PIN não será incluído.</span><span class="sxs-lookup"><span data-stu-id="ea270-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="ea270-134">Se você quiser redefinir o PIN de audioconferência e o envio de emails estiver desabilitado, será necessário enviá-lo para o usuário de outra maneira.</span><span class="sxs-lookup"><span data-stu-id="ea270-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="ea270-135">O envio de emails a seus usuários pode ser desabilitado usando o Centro de administração do Skype for Business ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea270-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="ea270-136">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ea270-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="ea270-137">Você pode usar esses cmdlets para economizar tempo ou automatizar isso.</span><span class="sxs-lookup"><span data-stu-id="ea270-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="ea270-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="ea270-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="ea270-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="ea270-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="ea270-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea270-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="ea270-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="ea270-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- <span data-ttu-id="ea270-142">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="ea270-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ea270-143">Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="ea270-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="ea270-144">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ea270-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ea270-145">Por que você precisa usar o Microsoft 365 ou o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="ea270-145">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ea270-146">Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea270-146">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="ea270-147">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="ea270-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ea270-148">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ea270-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="ea270-149">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ea270-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ea270-150">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ea270-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ea270-151">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ea270-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="ea270-p106">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="ea270-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ea270-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ea270-154">Related topics</span></span>

[<span data-ttu-id="ea270-155">Emails enviados para os usuários quando suas configurações de Audioconferência mudarem</span><span class="sxs-lookup"><span data-stu-id="ea270-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="ea270-156">Enviar um email para um usuário com suas informações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="ea270-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


