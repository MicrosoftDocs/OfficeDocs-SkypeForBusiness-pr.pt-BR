---
title: Gerenciar as configurações de áudio da conferência para minha organização
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
description: 'Consulte as etapas para atribuir uma ID de conferência e a licença de conferência discada a um usuário e outras configurações de conferência discada. '
ms.openlocfilehash: 26d80b71344227aeaec7089e2bb9f9a9dfe32ad2
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703664"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="25019-103">Gerenciar as configurações de áudio da conferência para minha organização</span><span class="sxs-lookup"><span data-stu-id="25019-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="25019-104">Talvez seja mais fácil para ver todas as configurações de serviços de audioconferência para Skype para Teams da Microsoft em um único local e de negócios.</span><span class="sxs-lookup"><span data-stu-id="25019-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="25019-105">Atribuir uma licença de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="25019-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="25019-106">Não é possível atribuir licenças usando o **Skype para centro de administração de negócios**.</span><span class="sxs-lookup"><span data-stu-id="25019-106">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="25019-107">Você deve usar o Centro de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="25019-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="25019-108">Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="25019-108">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="25019-109">**Para atribuir uma licença para um usuário**</span><span class="sxs-lookup"><span data-stu-id="25019-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="25019-110">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="25019-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="25019-111">No painel de navegação à esquerda do **Centro de administração do Office 365**, vá para **usuários** > **usuários ativos**e selecione o usuário ou usuários da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="25019-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="25019-112">[!DICA] Para atribuir licenças a mais de 20 usuários ao mesmo tempo, você pode usar o menu suspenso **Selecionar uma exibição** e escolher uma das opções ou criar sua própria exibição.</span><span class="sxs-lookup"><span data-stu-id="25019-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="25019-113">Em seguida, clique em **Editar**, **próximo** duas vezes e em seguida, selecione a licença e clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="25019-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="25019-114">Você também pode atribuir licenças a vários usuários usando o Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="25019-114">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="25019-115">Para obter instruções e scripts do PowerShell de amostra, consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="25019-115">For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="25019-116">No painel Ação em **Licenças de**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="25019-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="25019-117">Na página **Licenças do produto** , ligue a **Conferência de áudio** e, em seguida, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25019-117">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="25019-118">Para obter mais informações sobre licenciamento, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="25019-118">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="25019-119">Após atribuir a licença, Microsoft talvez não sejam exibidos inicialmente na lista como um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="25019-119">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="25019-120">Caso isso aconteça, saia do Centro de administração do Office 365 ou pressione CTRL+F5 para atualizar a janela do navegador.</span><span class="sxs-lookup"><span data-stu-id="25019-120">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="25019-121">Habilitar ou desabilitar os e-mails enviados para usuários de serviços de audioconferência</span><span class="sxs-lookup"><span data-stu-id="25019-121">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="25019-122">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="25019-122">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="25019-123">No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="25019-123">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="25019-124">Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="25019-124">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="25019-125">No painel de **configurações de ponte** , habilite ou desabilite a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de discagem**.</span><span class="sxs-lookup"><span data-stu-id="25019-125">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="25019-126">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25019-126">Click **Save**.</span></span>

<span data-ttu-id="25019-127">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="25019-127">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="25019-128">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="25019-128">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="25019-129">Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="25019-129">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="25019-130">Na página **configurações de ponte da Microsoft** , marque ou desmarque a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="25019-130">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="25019-131">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25019-131">Click **Save**.</span></span>
    
    <span data-ttu-id="25019-132">Você também pode enviar emails para o usuário com as configurações de serviços de audioconferência indo para propriedades de conferência de áudio do usuário e clicar em **Enviar informações de conferência via email**.</span><span class="sxs-lookup"><span data-stu-id="25019-132">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="25019-133">Número de telefone do serviços de audioconferência a conferência ID e o padrão é incluído no convite da reunião, mas não o PIN.</span><span class="sxs-lookup"><span data-stu-id="25019-133">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="25019-134">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="25019-134">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="25019-135">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="25019-135">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="25019-136">Também é possível usar o Windows PowerShell e executar:</span><span class="sxs-lookup"><span data-stu-id="25019-136">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="25019-137">Você pode usar o [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações da sua organização, incluindo email.</span><span class="sxs-lookup"><span data-stu-id="25019-137">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="25019-138">Alterar as informações de contato do remetente nas mensagens de email enviadas aos usuários</span><span class="sxs-lookup"><span data-stu-id="25019-138">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="25019-139">Você pode fazer alterações para email que será enviado automaticamente aos seus usuários, incluindo o endereço de email real e o nome para exibição de informações de contato do remetente.</span><span class="sxs-lookup"><span data-stu-id="25019-139">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="25019-140">Por padrão, o remetente dos emails é o Office 365, mas você pode alterar o endereço de email e nome para exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .</span><span class="sxs-lookup"><span data-stu-id="25019-140">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="25019-141">Para fazer alterações para o endereço de email que está enviando email aos usuários, você deve:</span><span class="sxs-lookup"><span data-stu-id="25019-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="25019-142">Insira o endereço de email no parâmetro _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="25019-142">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="25019-143">Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="25019-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="25019-144">Defina o parâmetro _SendEmailOverride_ como _True_.</span><span class="sxs-lookup"><span data-stu-id="25019-144">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="25019-145">Você pode fazer alterações nos emails enviados para usuários, como o endereço de email que envia as mensagens ou o nome de exibição do email executando:</span><span class="sxs-lookup"><span data-stu-id="25019-145">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="25019-146">Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado.</span><span class="sxs-lookup"><span data-stu-id="25019-146">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="25019-147">Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações da sua organização, incluindo email.</span><span class="sxs-lookup"><span data-stu-id="25019-147">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="25019-148">Consulte [Emails que são enviados automaticamente para os usuários quando alteram suas configurações de conferência de áudio](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="25019-148">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="25019-149">Redefinir a ID de conferência de reunião</span><span class="sxs-lookup"><span data-stu-id="25019-149">Reset the meeting conference ID</span></span>

<span data-ttu-id="25019-150">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="25019-150">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="25019-151">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="25019-151">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="25019-152">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="25019-152">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="25019-153">Em **Conferência de áudio**, clique em **Redefinir ID de conferência**.</span><span class="sxs-lookup"><span data-stu-id="25019-153">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="25019-154">No **Redefinir ID de conferência?** janela, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="25019-154">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="25019-155">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="25019-155">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="25019-156">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="25019-156">It's enabled by default.</span></span>

<span data-ttu-id="25019-157">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="25019-157">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="25019-158">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="25019-158">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="25019-159">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="25019-159">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="25019-160">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**e, no painel de ação em **ID da conferência**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="25019-160">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="25019-161">No **Redefinir ID de conferência?** janela, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="25019-161">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="25019-162">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="25019-162">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="25019-163">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="25019-163">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="25019-164">[!IMPORTANTE] Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores.</span><span class="sxs-lookup"><span data-stu-id="25019-164">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="25019-165">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites.</span><span class="sxs-lookup"><span data-stu-id="25019-165">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="25019-166">Os usuários podem usar o Skype para ferramenta de migração de reunião de negócios para atualizar suas reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="25019-166">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="25019-167">Para ver como baixar, instalar e executar o Skype para ferramenta de atualização de reunião de negócios, consulte: [Ferramenta de atualização de reunião para Skype para negócios e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para negócios Online, a ferramenta de migração de reunião (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype para Business Online Meeting Ferramenta de migração (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="25019-167">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="25019-168">Veja [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="25019-168">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="25019-169">Redefinir o PIN de um organizador da conferência</span><span class="sxs-lookup"><span data-stu-id="25019-169">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="25019-170">Cada reunião que um usuário agenda será obtido atribuída uma ID de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="25019-170">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="25019-171">Embora uma ID de conferência será criada automaticamente e atribuída a um usuário, pode haver ocasiões quando um usuário não deseja usar este e deseja defini-la a um certo número ou os usuários não conseguir se lembrar ou tem perdido sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="25019-171">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="25019-172">Você pode usar o Skype para centro de administração de negócios e do Windows PowerShell para exibir, alterar e redefinir a sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="25019-172">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="25019-173">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="25019-173">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="25019-174">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="25019-174">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="25019-175">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="25019-175">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="25019-176">Em **Conferência de áudio**, clique em **Redefinir PIN**e clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="25019-176">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="25019-177">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="25019-177">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="25019-178">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="25019-178">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="25019-179">Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="25019-179">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="25019-180">Clique em **usuários**e, em seguida, selecione o usuário que você deseja redefinir o PIN para.</span><span class="sxs-lookup"><span data-stu-id="25019-180">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="25019-181">No painel de ações, em **PIN**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="25019-181">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="25019-182">Os usuários receberão um email com o PIN quando elas são habilitadas para conferência de áudio ou quando o PIN ser redefinido.</span><span class="sxs-lookup"><span data-stu-id="25019-182">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="25019-183">Mas, se você desabilitou automaticamente enviando e-mails, um email de redefinição PIN não será enviado e você terá que enviar manualmente o PIN para o usuário.</span><span class="sxs-lookup"><span data-stu-id="25019-183">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="25019-184">O PIN será exibido somente uma vez depois de ser redefinido.</span><span class="sxs-lookup"><span data-stu-id="25019-184">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="25019-185">Depois que ele é exibido depois de ser redefinido, o PIN não será mostrado mais sobre as propriedades de usuário; em vez disso, \* \* \* serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="25019-185">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="25019-186">Consulte [Redefinir o PIN de conferência de áudio](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="25019-186">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="25019-187">Enviar um email com informações de conferência de áudio a um usuário</span><span class="sxs-lookup"><span data-stu-id="25019-187">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="25019-188">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="25019-188">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="25019-189">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="25019-189">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="25019-190">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="25019-190">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="25019-191">Em **Conferência de áudio**, clique em **Enviar informações de conferência no email**.</span><span class="sxs-lookup"><span data-stu-id="25019-191">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="25019-192">Quando você fizer isso, os serviços de audioconferência PIN não será enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="25019-192">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="25019-193">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="25019-193">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="25019-194">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="25019-194">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="25019-195">Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="25019-195">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="25019-196">Clique em **usuários**e, em seguida, selecione o usuário que você deseja redefinir o PIN para.</span><span class="sxs-lookup"><span data-stu-id="25019-196">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="25019-197">No painel Ação, clique em **Enviar informações da conferência por email**.</span><span class="sxs-lookup"><span data-stu-id="25019-197">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="25019-198">Quando você fizer isso, os serviços de audioconferência PIN não será enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="25019-198">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="25019-199">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="25019-199">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="25019-200">Configuração do telefone convidam números incluídos no</span><span class="sxs-lookup"><span data-stu-id="25019-200">Setting the phone numbers included on invites</span></span>

<span data-ttu-id="25019-201">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="25019-201">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="25019-202">No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="25019-202">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="25019-203">Ao lado de **Conferência de áudio**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="25019-203">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="25019-204">No painel de **Conferência de áudio** , você pode definir o **número de Chamada Tarifada** e, se permitido, o **número de chamada gratuito**.</span><span class="sxs-lookup"><span data-stu-id="25019-204">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="25019-205">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25019-205">Click **Save**.</span></span>

<span data-ttu-id="25019-206">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="25019-206">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  
  
1. <span data-ttu-id="25019-207">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="25019-207">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="25019-208">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="25019-208">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="25019-209">No painel de navegação esquerdo, vá para **conferência de áudio** > **usuários**.</span><span class="sxs-lookup"><span data-stu-id="25019-209">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="25019-210">Selecione o usuário que você deseja habilitar para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="25019-210">Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="25019-211">No painel de ações, você pode definir o **número de Chamada Tarifada** e, se permitido, o **número de chamada gratuito**.</span><span class="sxs-lookup"><span data-stu-id="25019-211">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="25019-212">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25019-212">Click **Save**.</span></span>
    
<span data-ttu-id="25019-213">Consulte [Definir convidam números incluídos no telefone](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="25019-213">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="25019-214">Escolher configurações de ponte de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="25019-214">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="25019-215">**Definir a experiência da reunião, quando os chamadores ingressem em uma reunião**</span><span class="sxs-lookup"><span data-stu-id="25019-215">**Set the meeting experience when callers join a meeting**</span></span>

 <span data-ttu-id="25019-216">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="25019-216">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="25019-217">No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="25019-217">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="25019-218">Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="25019-218">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="25019-219">No painel de **configurações de ponte** , habilitar ou desabilitar a **entrada de reunião e sair de notificações**.</span><span class="sxs-lookup"><span data-stu-id="25019-219">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="25019-220">Isso é ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="25019-220">This is enabled by default.</span></span> <span data-ttu-id="25019-221">Se você desabilitar essa opção, os usuários que já tenham ingressado na reunião por padrão não serão notificados quando alguém entra ou sai da reunião.</span><span class="sxs-lookup"><span data-stu-id="25019-221">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="25019-222">Em **tipo de anúncio de entrada/saída**, escolha **tons** ou **nomes ou números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="25019-222">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="25019-223">Se você escolher **nomes ou números de telefone**, você também pode optar por habilitar ou desabilitar **os chamadores Ask registrar seus nomes antes de ingressar na reunião**.</span><span class="sxs-lookup"><span data-stu-id="25019-223">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

1. <span data-ttu-id="25019-224">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25019-224">Click **Save**.</span></span>

<span data-ttu-id="25019-225">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="25019-225">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="25019-226">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="25019-226">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="25019-227">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="25019-227">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="25019-228">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="25019-228">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="25019-229">Em que **a experiência de participação da reunião**, selecione as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="25019-229">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="25019-230">**Habilitar a ativação de notificações de entrada e saída de reunião** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="25019-230">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="25019-231">Se você desmarcar essa caixa de seleção, os usuários que já tenham ingressado na reunião por padrão não serão notificados quando alguém entra ou sai da reunião.</span><span class="sxs-lookup"><span data-stu-id="25019-231">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="25019-232">Isso pode ser definido em uma base de reunião por reunião quando um usuário ingressa em uma reunião usando um Skype para o aplicativo de negócios ou Teams da Microsoft e eles modificam a configuração de **anunciar quando as pessoas entrar ou sair** do menu Skype reunião ou Microsoft Teams **Opções** do reunião.</span><span class="sxs-lookup"><span data-stu-id="25019-232">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="25019-233">**Peça que os chamadores registrem seus nomes antes de ingressar na reunião** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="25019-233">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="25019-234">Se você desmarcar essa caixa de seleção, os chamadores não solicitados registrar seus nomes antes de ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="25019-234">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="25019-235">Depois de fazer suas alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25019-235">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="25019-236">Consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="25019-236">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="25019-237">**Definir o tamanho PIN para reuniões**</span><span class="sxs-lookup"><span data-stu-id="25019-237">**Set the PIN length for meetings**</span></span>

 <span data-ttu-id="25019-238">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="25019-238">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="25019-239">No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="25019-239">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="25019-240">Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="25019-240">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="25019-241">No painel de **configurações de ponte** , insira o número de dígitos que você deseja para o PIN na lista **tamanho PIN** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25019-241">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="25019-242">O PIN deve ter entre 4 e 12 dígitos.</span><span class="sxs-lookup"><span data-stu-id="25019-242">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="25019-243">O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="25019-243">The default is 5.</span></span>

<span data-ttu-id="25019-244">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="25019-244">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="25019-245">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="25019-245">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="25019-246">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="25019-246">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="25019-247">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="25019-247">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="25019-248">Em **segurança**, insira o número de dígitos que você deseja para o PIN na lista **tamanho PIN** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25019-248">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="25019-249">O PIN deve ter entre 4 e 12 dígitos.</span><span class="sxs-lookup"><span data-stu-id="25019-249">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="25019-250">O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="25019-250">The default is 5.</span></span>
    
<span data-ttu-id="25019-251">Consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="25019-251">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="25019-252">**Habilitar ou desabilitar o email que está sendo enviado a usuários de áudio**</span><span class="sxs-lookup"><span data-stu-id="25019-252">**Enable or disable email from being sent to audio users**</span></span>

 <span data-ttu-id="25019-253">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="25019-253">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="25019-254">No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="25019-254">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="25019-255">Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="25019-255">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="25019-256">No painel de **configurações de ponte** , habilite ou desabilite a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="25019-256">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="25019-257">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25019-257">Click **Save**.</span></span> 
 
    <span data-ttu-id="25019-258">Você também pode enviar email para o usuário com as configurações de conferência de áudio, indo para propriedades de conferência de áudio do usuário e clicar em **Enviar informações de conferência no email**.</span><span class="sxs-lookup"><span data-stu-id="25019-258">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="25019-259">Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.</span><span class="sxs-lookup"><span data-stu-id="25019-259">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="25019-260">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="25019-260">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="25019-261">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="25019-261">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="25019-262">Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="25019-262">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="25019-263">Na página **configurações de ponte da Microsoft** , marque ou desmarque a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="25019-263">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="25019-264">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25019-264">Click **Save**.</span></span>
    
    <span data-ttu-id="25019-265">Você também pode enviar email para o usuário com as configurações de conferência de áudio, indo para propriedades de conferência de áudio do usuário e clicar em **Enviar informações de conferência via email**.</span><span class="sxs-lookup"><span data-stu-id="25019-265">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="25019-266">Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.</span><span class="sxs-lookup"><span data-stu-id="25019-266">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="25019-267">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="25019-267">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="25019-268">Consulte e defina o principal (padrão) e os idiomas secundários de (alternativos) em uma ponte de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="25019-268">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

 <span data-ttu-id="25019-269">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="25019-269">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="25019-270">No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="25019-270">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="25019-271">Selecione um número de telefone na lista e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="25019-271">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="25019-272">Escolha os idiomas desejado em **idioma padrão** e **idiomas alternativos (opcionais)**.</span><span class="sxs-lookup"><span data-stu-id="25019-272">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

<span data-ttu-id="25019-273">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="25019-273">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="25019-274">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="25019-274">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="25019-275">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="25019-275">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="25019-276">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**e, em seguida, clique em **Microsoft ponte**.</span><span class="sxs-lookup"><span data-stu-id="25019-276">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="25019-277">Selecione um número de telefone na lista, clique em **definir idiomas** no painel de ações e na página **conjunto** de idiomas, clique em uso na lista de **idioma principal** para exibir a lista completa dos idiomas com suporte.</span><span class="sxs-lookup"><span data-stu-id="25019-277">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="25019-278">Você também pode definir os idiomas principais e secundários que têm suporte quando você seleciona Microsoft como o provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="25019-278">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="25019-279">A ordem em que você selecione nas listas é a mesma ordem em que idiomas serão apresentados aos chamadores.</span><span class="sxs-lookup"><span data-stu-id="25019-279">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="25019-280">Veja [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="25019-280">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="25019-281">Consulte serviços de audioconferência discada números</span><span class="sxs-lookup"><span data-stu-id="25019-281">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="25019-282">![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="25019-282">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="25019-283">No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="25019-283">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="25019-284">Selecione um número de telefone na lista e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="25019-284">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="25019-285">Aqui, você pode:</span><span class="sxs-lookup"><span data-stu-id="25019-285">Here you can:</span></span>
    
  - <span data-ttu-id="25019-286">Exiba os números de telefone definidos pelo Office 365 a serem usados para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="25019-286">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="25019-287">Exiba o local e o idioma principal, que será usado pelo atendedor automático conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="25019-287">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>


<span data-ttu-id="25019-288">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="25019-288">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="25019-289">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="25019-289">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="25019-290">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="25019-290">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="25019-291">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="25019-291">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="25019-292">Aqui, você pode:</span><span class="sxs-lookup"><span data-stu-id="25019-292">Here you can:</span></span>
    
  - <span data-ttu-id="25019-293">Exiba os números de telefone definidos pelo Office 365 a serem usados para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="25019-293">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="25019-294">Exiba o local e os idiomas principais e secundários, que serão usados pelo atendedor automático conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="25019-294">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="25019-295">Selecione o número de telefone padrão que será fornecido aos usuários quando eles estão habilitados para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="25019-295">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="25019-296">No entanto, se o número de telefone de ponte de conferência de áudio padrão for alterado, não alterará o número de telefone padrão para usuários existentes.</span><span class="sxs-lookup"><span data-stu-id="25019-296">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="25019-297">Você pode ir para a **conferência de áudio** > **usuários** e selecione Propriedades do usuário para alterar o padrão de número de um usuário escolhendo um novo número da lista de números que estão disponíveis em sua organização.</span><span class="sxs-lookup"><span data-stu-id="25019-297">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="25019-298">Consulte [ver uma lista de números de conferência de áudio](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="25019-298">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) <span data-ttu-id="25019-300">Visualizar uma lista de usuários habilitados</span><span class="sxs-lookup"><span data-stu-id="25019-300">See a list of users that are enabled</span></span>

1. <span data-ttu-id="25019-301">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="25019-301">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="25019-302">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="25019-302">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="25019-303">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**> e, em seguida, **os usuários**.</span><span class="sxs-lookup"><span data-stu-id="25019-303">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="25019-304">Veja [Ver uma lista de usuários habilitados para conferência de áudio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="25019-304">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="25019-305">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="25019-305">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="25019-306">Existem diversas configurações que podem ser gerenciadas no nível da organização usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25019-306">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="25019-307">Isso facilita aplicar as configurações para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="25019-307">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="25019-308">Para obter mais ajuda sobre cada cmdlet, consulte [Cmdlets do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=627324).</span><span class="sxs-lookup"><span data-stu-id="25019-308">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="25019-309">Aqui estão as configurações de nível de organização:</span><span class="sxs-lookup"><span data-stu-id="25019-309">Here are the organization-level settings:</span></span> 
 
- <span data-ttu-id="25019-310">**Definir notificações de entrada/saída** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="25019-310">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="25019-311">**A definição de registro de nome** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="25019-311">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="25019-312">**A definição do comprimento do PIN** O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="25019-312">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="25019-313">**Configuração somente discada reuniões de um telefone** O padrão _$false_.</span><span class="sxs-lookup"><span data-stu-id="25019-313">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="25019-314">**Definindo-se enviar email aos usuários** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="25019-314">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="25019-315">**Definindo-se enviar email a partir de uma conta diferente** O padrão é _$false_.</span><span class="sxs-lookup"><span data-stu-id="25019-315">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="25019-316">**Definindo o endereço From em que é enviado aos usuários de email** O padrão é _$null_.</span><span class="sxs-lookup"><span data-stu-id="25019-316">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="25019-317">**Definir o nome de exibição para o email que será enviado aos usuários** O padrão é _$null_.</span><span class="sxs-lookup"><span data-stu-id="25019-317">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="25019-318">Quer saber mais sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="25019-318">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="25019-p123">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="25019-p123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="25019-322">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="25019-322">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="25019-323">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="25019-323">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="25019-324">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações de muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="25019-324">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="25019-325">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="25019-325">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="25019-326">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="25019-326">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="25019-327">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="25019-327">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="25019-328">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="25019-328">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="25019-p125">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="25019-p125">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="25019-331">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="25019-331">Related topics</span></span>

[<span data-ttu-id="25019-332">Gerenciar as configurações de audioconferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="25019-332">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


