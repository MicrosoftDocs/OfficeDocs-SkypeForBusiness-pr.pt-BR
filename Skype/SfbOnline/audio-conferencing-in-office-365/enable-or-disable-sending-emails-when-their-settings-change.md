---
title: Habilitar ou desabilitar o envio de emails ao alteram suas configurações
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 9656dc25347661626397e4f95daee7bd5f460a6d
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703440"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a><span data-ttu-id="06ec2-103">Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="06ec2-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="06ec2-104">Os usuários são notificados automaticamente por email quando estiverem habilitados para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="06ec2-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="06ec2-105">Pode haver momentos, entretanto, quando você deseja reduzir o número de emails que são enviadas para Skype para usuário Teams da Microsoft e de negócios.</span><span class="sxs-lookup"><span data-stu-id="06ec2-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span></span> <span data-ttu-id="06ec2-106">Nesses casos, você pode desabilitar o envio de email.</span><span class="sxs-lookup"><span data-stu-id="06ec2-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="06ec2-107">Se você desabilitar o envio de emails, emails de conferência de áudio não serão enviadas aos seus usuários, incluindo emails para quando os usuários estão habilitados ou desabilitados para conferências de áudio, quando o seu PIN é redefinido e quando as alterações no número de telefone a ID de conferência e a conferência padrão .</span><span class="sxs-lookup"><span data-stu-id="06ec2-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="06ec2-108">Aqui está um exemplo de email enviada aos usuários quando eles estão habilitados para conferência de áudio:</span><span class="sxs-lookup"><span data-stu-id="06ec2-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Email de conferência de áudio](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="06ec2-110">Quando os emails são enviados para seus usuários?</span><span class="sxs-lookup"><span data-stu-id="06ec2-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="06ec2-111">Há vários emails que serão enviadas aos usuários em sua organização depois que eles estão habilitados para conferência de áudio:</span><span class="sxs-lookup"><span data-stu-id="06ec2-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="06ec2-112">Quando uma licença de **Conferência de áudio** é atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="06ec2-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="06ec2-113">Quando você redefinir manualmente os serviços de audioconferência PIN do usuário.</span><span class="sxs-lookup"><span data-stu-id="06ec2-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="06ec2-114">Quando você redefine manualmente o ID de conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="06ec2-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="06ec2-115">Quando a licença de **Conferência de áudio** seja removida deles.</span><span class="sxs-lookup"><span data-stu-id="06ec2-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="06ec2-116">Quando o provedor de serviços de audioconferência de um usuário for alterado da Microsoft para outro provedor ou **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="06ec2-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="06ec2-117">Quando o provedor de serviços de audioconferência de um usuário é alterado para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="06ec2-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>
    
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="06ec2-118">Habilitar ou desabilitar o email que está sendo enviado a usuários</span><span class="sxs-lookup"><span data-stu-id="06ec2-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="06ec2-119">Você pode usar o Microsoft Teams, o Skype para centro de administração de negócios, ou o Windows PowerShell para habilitar ou desabilitar o email enviado aos usuários.</span><span class="sxs-lookup"><span data-stu-id="06ec2-119">You can use Microsoft Teams, the Skype for Business admin center, or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="06ec2-120">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="06ec2-120">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="06ec2-121">No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="06ec2-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="06ec2-122">Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="06ec2-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="06ec2-123">No painel de **configurações de ponte** , habilite ou desabilite a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de discagem**.</span><span class="sxs-lookup"><span data-stu-id="06ec2-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="06ec2-124">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="06ec2-124">Click **Save**.</span></span>
  
<span data-ttu-id="06ec2-125">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="06ec2-125">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="06ec2-126">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, clique em **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="06ec2-126">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="06ec2-127">Na página **configurações de ponte da Microsoft** , marque ou desmarque a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="06ec2-127">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="06ec2-128">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="06ec2-128">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="06ec2-129">Você também pode enviar email a um usuário com as configurações de serviços de audioconferência indo para **conferência de áudio** > **usuários**, selecionando o usuário e, em seguida, clicando em **Enviar informações de conferência via email**.</span><span class="sxs-lookup"><span data-stu-id="06ec2-129">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="06ec2-130">Se fizer isso, será enviado um email que inclui somente o ID de conferência e o número de telefone de conferência, mas não o PIN.</span><span class="sxs-lookup"><span data-stu-id="06ec2-130">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="06ec2-131">Para obter mais informações, consulte [Enviar um email a um usuário com as informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md) .</span><span class="sxs-lookup"><span data-stu-id="06ec2-131">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="06ec2-132">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="06ec2-132">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="06ec2-133">Execute o seguinte procedimento para desabilitar o envio de emails:</span><span class="sxs-lookup"><span data-stu-id="06ec2-133">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="06ec2-134">Para obter ajuda com este cmdlet, consulte [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="06ec2-134">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="06ec2-135">O que mais você deve saber?</span><span class="sxs-lookup"><span data-stu-id="06ec2-135">What else should you know?</span></span>

- <span data-ttu-id="06ec2-136">Quando emails automáticas estão desabilitadas, você pode acionar ainda manualmente enviar um email com o número de telefone e a ID de conferência usando o Skype para o Centro de administração de negócios.</span><span class="sxs-lookup"><span data-stu-id="06ec2-136">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="06ec2-137">No entanto, se você fizer isso, o PIN não será incluído.</span><span class="sxs-lookup"><span data-stu-id="06ec2-137">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="06ec2-138">Se você deseja redefinir o PIN de conferência de áudio e enviando e-mails estiver desabilitado, você precisará enviá-la ao usuário em outra forma.</span><span class="sxs-lookup"><span data-stu-id="06ec2-138">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="06ec2-139">O envio de emails a seus usuários pode ser desabilitado usando o Centro de administração do Skype for Business ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06ec2-139">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="06ec2-140">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="06ec2-140">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="06ec2-141">Você pode usar esses cmdlets para economizar tempo ou automatizar isso.</span><span class="sxs-lookup"><span data-stu-id="06ec2-141">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="06ec2-142">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="06ec2-142">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="06ec2-143">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="06ec2-143">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="06ec2-144">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="06ec2-144">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="06ec2-145">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="06ec2-145">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="06ec2-p104">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="06ec2-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="06ec2-149">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="06ec2-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="06ec2-150">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="06ec2-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="06ec2-151">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="06ec2-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="06ec2-152">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="06ec2-152">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="06ec2-153">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="06ec2-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="06ec2-154">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="06ec2-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="06ec2-155">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="06ec2-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="06ec2-p106">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="06ec2-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="06ec2-158">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="06ec2-158">Related topics</span></span>

[<span data-ttu-id="06ec2-159">Emails enviados aos usuários ao alteram suas configurações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="06ec2-159">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="06ec2-160">Enviar um email para um usuário com suas informações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="06ec2-160">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


