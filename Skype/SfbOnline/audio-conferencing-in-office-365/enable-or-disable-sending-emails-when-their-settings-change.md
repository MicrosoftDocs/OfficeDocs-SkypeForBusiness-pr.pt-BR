---
title: Habilitar ou desabilitar o envio de emails quando as configurações de conferência de áudio mudarem no Skype for Business Online
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 28da70d829972a7b9d3659290652c2482d409364
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792324"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="61ab2-103">Habilitar ou desabilitar o envio de emails quando as configurações de conferência de áudio mudarem no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="61ab2-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="61ab2-104">Se você quiser habilitar ou desabilitar o envio de emails no Microsoft Teams, consulte [habilitar ou desabilitar o envio de emails quando as configurações de conferência de áudio mudarem no Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="61ab2-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="61ab2-105">Os usuários são notificados automaticamente por e-mail quando estão habilitados para videoconferências.</span><span class="sxs-lookup"><span data-stu-id="61ab2-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="61ab2-106">No entanto, pode haver ocasiões em que você queira reduzir o número de emails enviados para os usuários do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="61ab2-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="61ab2-107">Nesses casos, você pode desabilitar o envio de emails.</span><span class="sxs-lookup"><span data-stu-id="61ab2-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="61ab2-108">Se você desabilitar o envio de emails, os emails de audioconferência não serão enviados para seus usuários, incluindo emails para quando os usuários estiverem habilitados ou desabilitados para a conferência de áudio, quando o PIN for redefinido e quando a ID de conferência e o número de telefone de conferência padrão forem alterados .</span><span class="sxs-lookup"><span data-stu-id="61ab2-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="61ab2-109">Aqui está um exemplo do e-mail que é enviado aos usuários quando eles são habilitados para videoconferências:</span><span class="sxs-lookup"><span data-stu-id="61ab2-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Email de audioconferência](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="61ab2-111">Quando os emails são enviados para seus usuários?</span><span class="sxs-lookup"><span data-stu-id="61ab2-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="61ab2-112">Há vários emails enviados para os usuários em sua organização após serem habilitados para conferências de áudio:</span><span class="sxs-lookup"><span data-stu-id="61ab2-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="61ab2-113">Quando uma licença de **conferência de áudio** é atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="61ab2-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="61ab2-114">Quando você redefine manualmente o PIN de audioconferência de áudio do usuário.</span><span class="sxs-lookup"><span data-stu-id="61ab2-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="61ab2-115">Quando você redefine manualmente o ID de conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="61ab2-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="61ab2-116">Quando a licença de **conferência de áudio** é removida.</span><span class="sxs-lookup"><span data-stu-id="61ab2-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="61ab2-117">Quando o provedor de audioconferência de um usuário for alterado da Microsoft para outro provedor ou **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="61ab2-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="61ab2-118">Quando o provedor de audioconferência de um usuário for alterado para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="61ab2-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="61ab2-119">Habilitar ou desabilitar o envio de emails para os usuários</span><span class="sxs-lookup"><span data-stu-id="61ab2-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="61ab2-120">Você pode usar o centro de administração do Skype for Business ou o Windows PowerShell para habilitar ou desabilitar o envio de emails para os usuários.</span><span class="sxs-lookup"><span data-stu-id="61ab2-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="61ab2-121">![Um ícone mostrando o logotipo](../images/sfb-logo-30x30.png) do Skype for Business **usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="61ab2-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="61ab2-122">No **centro de administração do Skype for Business**, no painel de navegação à esquerda, clique em **videoconferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="61ab2-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="61ab2-123">Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.</span><span class="sxs-lookup"><span data-stu-id="61ab2-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="61ab2-124">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="61ab2-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="61ab2-125">Você também pode enviar emails para um usuário com as configurações de videoconferência acessando**usuários**de **audioconferência** > , selecionando o usuário e clicando em **enviar informações de conferência por email**.</span><span class="sxs-lookup"><span data-stu-id="61ab2-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="61ab2-126">Se você fizer isso, será enviado um e-mail que inclui apenas a ID de conferência e o número de telefone de conferência, mas não o PIN.</span><span class="sxs-lookup"><span data-stu-id="61ab2-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="61ab2-127">Para obter mais informações, consulte [enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md) .</span><span class="sxs-lookup"><span data-stu-id="61ab2-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="61ab2-128">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="61ab2-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="61ab2-129">Execute o seguinte para desabilitar o envio de emails:</span><span class="sxs-lookup"><span data-stu-id="61ab2-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="61ab2-130">Para obter ajuda com esse cmdlet, consulte [set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="61ab2-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="61ab2-131">O que mais você deve saber?</span><span class="sxs-lookup"><span data-stu-id="61ab2-131">What else should you know?</span></span>

- <span data-ttu-id="61ab2-132">Quando os emails automáticos estiverem desativados, você ainda poderá disparar manualmente o envio de um email com a ID de conferência e o número de telefone usando o centro de administração do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="61ab2-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="61ab2-133">No entanto, se você fizer isso, o pino não será incluído.</span><span class="sxs-lookup"><span data-stu-id="61ab2-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="61ab2-134">Se você quiser redefinir o PIN de audioconferência e enviar emails estiver desabilitado, será necessário enviá-lo para o usuário de outra maneira.</span><span class="sxs-lookup"><span data-stu-id="61ab2-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="61ab2-135">O envio de emails a seus usuários pode ser desabilitado usando o Centro de administração do Skype for Business ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61ab2-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="61ab2-136">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="61ab2-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="61ab2-137">Você pode usar esses cmdlets para economizar tempo ou automatizar isso.</span><span class="sxs-lookup"><span data-stu-id="61ab2-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="61ab2-138">Get-Csonlinedialinconferencingtenantsettingshttp</span><span class="sxs-lookup"><span data-stu-id="61ab2-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="61ab2-139">Remove-Csonlinedialinconferencingtenantsettingshttp</span><span class="sxs-lookup"><span data-stu-id="61ab2-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="61ab2-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="61ab2-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="61ab2-141">Get-Csonlinedialinconferencingtenantsettingshttp</span><span class="sxs-lookup"><span data-stu-id="61ab2-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- <span data-ttu-id="61ab2-p104">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="61ab2-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="61ab2-145">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="61ab2-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="61ab2-146">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61ab2-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="61ab2-147">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está realizando alterações de configuração para muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="61ab2-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="61ab2-148">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="61ab2-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="61ab2-149">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="61ab2-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="61ab2-150">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="61ab2-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="61ab2-151">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="61ab2-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="61ab2-p106">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="61ab2-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="61ab2-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="61ab2-154">Related topics</span></span>

[<span data-ttu-id="61ab2-155">Emails enviados para os usuários quando as configurações de conferência de áudio mudam</span><span class="sxs-lookup"><span data-stu-id="61ab2-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="61ab2-156">Enviar um email para um usuário com suas informações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="61ab2-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


