---
title: Gerenciar as configurações da Audioconferência para minha organização no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
description: 'Confira as etapas do Skype for Business online para atribuir uma ID de conferência e uma licença de conferência discada para um usuário e muitas outras configurações de conferência discada. '
ms.openlocfilehash: aef115d2882a368e085880a66332dc7d22e4ff04
ms.sourcegitcommit: e65411a739c539d5232ebc89af3630d07d518b89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2019
ms.locfileid: "35638560"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="1e7de-103">Gerenciar as configurações da Audioconferência para minha organização no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1e7de-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="1e7de-104">Se você quiser gerenciar essas configurações em equipes, consulte [Gerenciar as configurações de Audioconferência para minha organização no Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span><span class="sxs-lookup"><span data-stu-id="1e7de-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="1e7de-105">Pode ser mais fácil para você ver todas as configurações de audioconferência para o Skype for Business em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="1e7de-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="1e7de-106">Atribuir uma licença de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="1e7de-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="1e7de-p101">You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-p101">You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="1e7de-110">**Para atribuir uma licença para um usuário**</span><span class="sxs-lookup"><span data-stu-id="1e7de-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="1e7de-111">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="1e7de-111">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="1e7de-112">Na navegação à esquerda do **centro de administração do Office 365**, vá \*\*\*\* > para usuários**ativos**do Office e selecione o usuário ou os usuários na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="1e7de-112">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1e7de-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-p102">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="1e7de-117">No painel Ação em **Licenças de**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="1e7de-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-p103">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1e7de-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span><span class="sxs-lookup"><span data-stu-id="1e7de-p104">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider. If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="1e7de-122">Habilitar ou desabilitar emails enviados para usuários de audioconferência</span><span class="sxs-lookup"><span data-stu-id="1e7de-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="1e7de-123">![Um ícone mostrando o logotipo](../images/sfb-logo-30x30.png) do Skype for Business **usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="1e7de-123">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="1e7de-124">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="1e7de-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="1e7de-125">Vá para o **Centro** > de administração do Office 365**Skype for Business** e, no painel de navegação esquerdo, clique em **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-125">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="1e7de-126">Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="1e7de-127">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-127">Click **Save**.</span></span>

    <span data-ttu-id="1e7de-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span><span class="sxs-lookup"><span data-stu-id="1e7de-p105">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="1e7de-130">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="1e7de-131">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1e7de-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="1e7de-132">Também é possível usar o Windows PowerShell e executar:</span><span class="sxs-lookup"><span data-stu-id="1e7de-132">You can also use the Windows PowerShell and run:</span></span>

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="1e7de-133">Você pode usar o [set-csonlinedialinconferencingtenantsettingshttp](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) para gerenciar outras configurações de sua organização, incluindo o email.</span><span class="sxs-lookup"><span data-stu-id="1e7de-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="1e7de-134">Alterar as informações de contato do remetente nas mensagens de email enviadas aos usuários</span><span class="sxs-lookup"><span data-stu-id="1e7de-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="1e7de-p106">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span><span class="sxs-lookup"><span data-stu-id="1e7de-p106">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information. By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet. To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="1e7de-138">Digite o endereço de email no parâmetro _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="1e7de-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="1e7de-139">Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="1e7de-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="1e7de-140">Defina o parâmetro _SendEmailOverride_ como _Verdadeiro_.</span><span class="sxs-lookup"><span data-stu-id="1e7de-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="1e7de-141">Você pode fazer alterações nos emails enviados para usuários, como o endereço de email que envia as mensagens ou o nome de exibição do email executando:</span><span class="sxs-lookup"><span data-stu-id="1e7de-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="1e7de-142">Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado.</span><span class="sxs-lookup"><span data-stu-id="1e7de-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="1e7de-143">Você pode usar o cmdlet [set-csonlinedialinconferencingtenantsettingshttp](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) para gerenciar outras configurações de sua organização, incluindo o email.</span><span class="sxs-lookup"><span data-stu-id="1e7de-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="1e7de-144">Veja [os emails enviados automaticamente para os usuários quando as configurações de conferência de áudio mudam](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="1e7de-145">Redefinir a ID de conferência de reunião</span><span class="sxs-lookup"><span data-stu-id="1e7de-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="1e7de-146">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="1e7de-146">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="1e7de-147">Navegue para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="1e7de-148">No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **Audioconferência**, e no painel Ação, em **ID da conferência**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="1e7de-p107">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="1e7de-p107">In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="1e7de-p108">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="1e7de-p108">After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="1e7de-156">Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="1e7de-157">Redefinir o PIN de um organizador da conferência</span><span class="sxs-lookup"><span data-stu-id="1e7de-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="1e7de-p109">Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="1e7de-p109">Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="1e7de-161">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="1e7de-161">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="1e7de-162">Vá para o **Centro** > de administração do Office 365**Skype for Business** e, no painel de navegação esquerdo, clique em **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-162">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="1e7de-163">Clique em **usuários**e selecione o usuário para o qual você deseja redefinir o PIN.</span><span class="sxs-lookup"><span data-stu-id="1e7de-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="1e7de-164">No painel Ação, em **PIN**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="1e7de-p110">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span><span class="sxs-lookup"><span data-stu-id="1e7de-p110">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="1e7de-169">Consulte [redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="1e7de-170">Enviar um email com as informações de conferência de áudio para um usuário</span><span class="sxs-lookup"><span data-stu-id="1e7de-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="1e7de-171">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="1e7de-171">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="1e7de-172">Vá para o **Centro** > de administração do Office 365**Skype for Business** e, no painel de navegação esquerdo, clique em **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-172">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="1e7de-173">Clique em **usuários**e selecione o usuário para o qual você deseja redefinir o PIN.</span><span class="sxs-lookup"><span data-stu-id="1e7de-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="1e7de-174">No painel Ação, clique em **Enviar informações da conferência por email**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1e7de-175">Quando você faz isso, o pino de audioconferência não é enviado para o usuário.</span><span class="sxs-lookup"><span data-stu-id="1e7de-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="1e7de-176">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="1e7de-177">Configurar os números de telefone incluídos nos convites</span><span class="sxs-lookup"><span data-stu-id="1e7de-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="1e7de-178">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="1e7de-178">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="1e7de-179">Navegue para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-179">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="1e7de-p111">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span><span class="sxs-lookup"><span data-stu-id="1e7de-p111">In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="1e7de-182">No painel de Ação você pode definir o **Número de chamada tarifada** e, se permitido, o **Número de chamada gratuita**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="1e7de-183">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-183">Click **Save**.</span></span>

<span data-ttu-id="1e7de-184">Consulte [definir os números de telefone incluídos nos convites](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="1e7de-185">Escolher as configurações de ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="1e7de-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="1e7de-186">**Definir a experiência da reunião quando os chamadores entrarem em uma reunião**</span><span class="sxs-lookup"><span data-stu-id="1e7de-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="1e7de-187">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="1e7de-187">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="1e7de-188">Navegue para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-188">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="1e7de-189">No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá para **conferência** > de áudio**configurações da ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="1e7de-190">Em **experiência de participação na reunião**, selecione as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="1e7de-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="1e7de-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span><span class="sxs-lookup"><span data-stu-id="1e7de-p112">**Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="1e7de-193">Isso pode ser definido de acordo com a reunião quando um usuário ingressa em uma reunião usando um aplicativo Skype for Business e ele modifica a configuração **anunciar quando as pessoas entram ou saem** no menu **Opções** de reunião do Skype da reunião.</span><span class="sxs-lookup"><span data-stu-id="1e7de-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="1e7de-p113">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span><span class="sxs-lookup"><span data-stu-id="1e7de-p113">**Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="1e7de-196">Depois de fazer suas alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="1e7de-197">Consulte [alterar as configurações de uma ponte de conferência de áudio](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="1e7de-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="1e7de-198">**Definir o comprimento do PIN para reuniões**</span><span class="sxs-lookup"><span data-stu-id="1e7de-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="1e7de-199">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="1e7de-199">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="1e7de-200">Navegue para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-200">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="1e7de-201">No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá para **conferência** > de áudio**configurações da ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="1e7de-202">Em **segurança**, insira o número de dígitos que você deseja para o pino na lista **comprimento do pino** e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="1e7de-p114">The PIN must be between 4 and 12 digits. The default is 5.</span><span class="sxs-lookup"><span data-stu-id="1e7de-p114">The PIN must be between 4 and 12 digits. The default is 5.</span></span>
    
<span data-ttu-id="1e7de-205">Consulte [alterar as configurações de uma ponte de conferência de áudio](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="1e7de-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="1e7de-206">**Habilitar ou desabilitar o envio de emails para usuários de áudio**</span><span class="sxs-lookup"><span data-stu-id="1e7de-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="1e7de-207">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="1e7de-207">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="1e7de-208">Vá para o **Centro** > de administração do Office 365**Skype for Business** e, no painel de navegação esquerdo, clique em **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="1e7de-209">Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="1e7de-210">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-210">Click **Save**.</span></span>

    <span data-ttu-id="1e7de-211">Você também pode enviar emails para o usuário com as configurações de audioconferência, acessando as propriedades de videoconferência do usuário e clicando em **enviar informações de conferência por e-mail**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="1e7de-212">Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.</span><span class="sxs-lookup"><span data-stu-id="1e7de-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="1e7de-213">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="1e7de-214">Ver e definir os idiomas principais (padrão) e secundários (alternativos) em uma ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="1e7de-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="1e7de-215">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="1e7de-215">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="1e7de-216">Navegue para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="1e7de-217">No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **videoconferências**e clique em ponte da **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="1e7de-218">Selecione um número de telefone na lista, clique em **definir idiomas** no painel ação e, na página **definir idiomas** , clique na lista usar o **idioma principal** para exibir a lista completa de idiomas com suporte.</span><span class="sxs-lookup"><span data-stu-id="1e7de-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="1e7de-p115">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span><span class="sxs-lookup"><span data-stu-id="1e7de-p115">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="1e7de-221">Veja [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="1e7de-222">Consulte números de discagem de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="1e7de-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="1e7de-223">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="1e7de-223">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="1e7de-224">Navegue para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-224">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="1e7de-p116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span><span class="sxs-lookup"><span data-stu-id="1e7de-p116">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:</span></span>

   - <span data-ttu-id="1e7de-227">Veja os números de telefone definidos pelo Office 365 a serem usados para videoconferências.</span><span class="sxs-lookup"><span data-stu-id="1e7de-227">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="1e7de-228">Exiba o local e os idiomas primário e secundário, que serão usados pelo atendedor automático da conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="1e7de-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="1e7de-p117">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span><span class="sxs-lookup"><span data-stu-id="1e7de-p117">Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="1e7de-231">Você pode acessar**usuários** de **audioconferência** > e selecionar as propriedades do usuário para alterar o número padrão de um usuário, escolhendo um novo número na lista de números disponíveis em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1e7de-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="1e7de-232">Veja [ver uma lista de números de audioconferência](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="1e7de-233">Visualizar uma lista de usuários habilitados</span><span class="sxs-lookup"><span data-stu-id="1e7de-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="1e7de-234">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="1e7de-234">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="1e7de-235">Navegue para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-235">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="1e7de-236">No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **videoconferências**> e depois **usuários**.</span><span class="sxs-lookup"><span data-stu-id="1e7de-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="1e7de-237">Veja [Ver uma lista de usuários habilitados para conferência de áudio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="1e7de-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1e7de-238">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="1e7de-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="1e7de-p118">There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.</span><span class="sxs-lookup"><span data-stu-id="1e7de-p118">There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="1e7de-241">Para obter mais ajuda sobre cada cmdlet, consulte [Cmdlets do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=627324).</span><span class="sxs-lookup"><span data-stu-id="1e7de-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="1e7de-242">Aqui estão as configurações no nível da organização:</span><span class="sxs-lookup"><span data-stu-id="1e7de-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="1e7de-243">**Configurar notificações de entrada/saída** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="1e7de-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="1e7de-244">**Configurar registro de nome** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="1e7de-244">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="1e7de-245">**Configurar comprimento do PIN** O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="1e7de-245">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="1e7de-246">**Configurar apenas reuniões por telefone** O padrão _$false_.</span><span class="sxs-lookup"><span data-stu-id="1e7de-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="1e7de-247">**Configurar o envio de email para usuários** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="1e7de-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="1e7de-248">**Configurar o envio de email a partir de uma conta diferente** O padrão é _$false_.</span><span class="sxs-lookup"><span data-stu-id="1e7de-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="1e7de-249">**Configurar o endereço De no email enviado aos usuários** O padrão é _$null_.</span><span class="sxs-lookup"><span data-stu-id="1e7de-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="1e7de-250">**Configurar o nome para exibição do email que é enviado aos usuários** O padrão é _$null_.</span><span class="sxs-lookup"><span data-stu-id="1e7de-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1e7de-251">Quer saber mais sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e7de-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="1e7de-p119">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="1e7de-p119">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="1e7de-255">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="1e7de-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="1e7de-256">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e7de-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="1e7de-p120">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="1e7de-p120">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="1e7de-259">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1e7de-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="1e7de-260">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1e7de-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="1e7de-261">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1e7de-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="1e7de-p121">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="1e7de-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="1e7de-264">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1e7de-264">Related topics</span></span>

[<span data-ttu-id="1e7de-265">Gerenciar as configurações de audioconferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="1e7de-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


