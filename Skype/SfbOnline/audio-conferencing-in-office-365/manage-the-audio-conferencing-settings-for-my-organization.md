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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Consulte as etapas do Skype for Business Online para atribuir uma licença de conferência discada e um ID de conferência a um usuário e muitas outras configurações de conferência discada. '
ms.openlocfilehash: 7f4387e7d818730de3b2b0336453a3f6ec9b39e7
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780487"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="c7ec7-103">Gerenciar as configurações da Audioconferência para minha organização no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c7ec7-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="c7ec7-104">Se você quiser gerenciar essas configurações em equipes, consulte [Gerenciar as configurações de Audioconferência para minha organização no Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="c7ec7-105">Pode ser mais fácil para você ver todas as configurações de audioconferência do Skype for Business em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-105">It might be easier for you to see all of the dial-in conferencing settings in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="c7ec7-106">Atribuir uma licença de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="c7ec7-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="c7ec7-107">Não é possível atribuir licenças usando o **centro de administração do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-107">You can't assign licenses using the **Skype for Business admin center**, you must use the Office 365 admin center.</span></span> <span data-ttu-id="c7ec7-108">Você deve usar o centro de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-108">You can use the Office 365 admin center though too.</span></span> <span data-ttu-id="c7ec7-109">Consulte [Atribuir licenças do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="c7ec7-110">**Para atribuir uma licença para um usuário**</span><span class="sxs-lookup"><span data-stu-id="c7ec7-110">**** To assign a license for a user</span></span>

1. <span data-ttu-id="c7ec7-111">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-111">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="c7ec7-112">Na barra de navegação esquerda do **centro de administração do Office 365**, vá até **Usuários** > **Usuários ativos**, e selecione o usuário ou usuários na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-112">In the left navigation of the Office 365 admin center, go to Users  Active users > and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7ec7-113">[!DICA] Para atribuir licenças a mais de 20 usuários ao mesmo tempo, você pode usar o menu suspenso **Selecionar uma exibição** e escolher uma das opções ou criar sua própria exibição.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="c7ec7-114">Em seguida, clique em **Editar**, **Avançar** duas vezes, selecione a licença e clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-114">Then click **Edit**Next**Next** then select the license and click **Submit**.</span></span> <span data-ttu-id="c7ec7-115">Você também pode atribuir licenças a vários usuários usando o Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="c7ec7-116">Para obter instruções e scripts de amostra do PowerShell, consulte [Atribuir licenças do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="c7ec7-117">No painel de Ação em **Licenças de produtos**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="c7ec7-118">Na página **Licenças de produtos**, ligue a **Audioconferência** e em seguida clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="c7ec7-119">Para mais informações sobre licenciamento, consulte [Licenciamento de suplementos do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c7ec7-120">Depois de atribuir a licença, a Microsoft pode não aparecer inicialmente na lista como um provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-120">After you assign the license, Microsoft might not appear initially in the drop-down as a dial-in conferencing provider.</span></span> <span data-ttu-id="c7ec7-121">Caso isso aconteça, saia do centro de administração do Office 365 ou pressione CTRL+F5 para atualizar a janela do navegador.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-121">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="c7ec7-122">Ativar ou desativar emails enviados para usuários de audioconferência</span><span class="sxs-lookup"><span data-stu-id="c7ec7-122">Enable or disable emails from being sent to dial-in users</span></span>

<span data-ttu-id="c7ec7-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Usar o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="c7ec7-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="c7ec7-124">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="c7ec7-125">Vá para o **centro de administração do Office 365** > **do Skype for Business** e, no painel de navegação esquerdo, clique em **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-125">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**</span></span>

3. <span data-ttu-id="c7ec7-126">Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="c7ec7-127">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-127">Click **Save**.</span></span>

    <span data-ttu-id="c7ec7-128">Você também pode enviar emails para o usuário com as configurações da audioconferência acessando as propriedades de audioconferência do usuário e clicando em **Enviar informações da conferência via email**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-128">You can also send emails to the user with the dial-in conferencing settings, by going to the user's properties > **Dial-in conferencingSend conference info via email**.</span></span> <span data-ttu-id="c7ec7-129">O ID da conferência e o número de telefone padrão da audioconferência estão incluídos no convite da reunião, mas não o PIN.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-129">The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="c7ec7-130">Veja [Enviar um email para um usuário com as informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="c7ec7-131">**Usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c7ec7-131">**** Using Windows PowerShell</span></span>

- <span data-ttu-id="c7ec7-132">Também é possível usar o Windows PowerShell e executar:</span><span class="sxs-lookup"><span data-stu-id="c7ec7-132">You can also use the Windows PowerShell and run:</span></span>

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="c7ec7-133">Você pode usar [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações da sua organização, incluindo o email.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="c7ec7-134">Alterar as informações de contato do remetente nas mensagens de email enviadas aos usuários</span><span class="sxs-lookup"><span data-stu-id="c7ec7-134">Change the senders contact information of email messages sent to users</span></span>

<span data-ttu-id="c7ec7-135">Você pode fazer alterações nos emails enviados automaticamente para seus usuários, incluindo o endereço de email real e o nome para exibição das informações de contato do remetente.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-135">You can make changes to the email that is automatically sent to your users including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="c7ec7-136">Por padrão, o remetente dos emails é o Office 365, mas é possível alterar o endereço de email e o nome para exibição com o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-136">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="c7ec7-137">Para fazer alterações no endereço do email enviado para seus usuários, você deve:</span><span class="sxs-lookup"><span data-stu-id="c7ec7-137">To make changes to the email address that is sending the email to the users you must:</span></span>

- <span data-ttu-id="c7ec7-138">Insira o endereço de email no parâmetro _SendEmailFromAddress_.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-138">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="c7ec7-139">Insira o nome para exibição no email no parâmetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="c7ec7-140">Defina o parâmetro _SendEmailOverride_ como _Verdadeiro_.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="c7ec7-141">Você pode fazer alterações nos emails enviados para usuários, como o endereço de email que envia as mensagens ou o nome de exibição do email executando:</span><span class="sxs-lookup"><span data-stu-id="c7ec7-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="c7ec7-142">Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="c7ec7-143">Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações de sua organização, incluindo o email.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization including email.</span></span>

<span data-ttu-id="c7ec7-144">Veja [Emails enviados automaticamente para os usuários quando suas configurações de Audioconferência forem alteradas](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-144">See [Emails that are automatically sent to users when their dial-in conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="c7ec7-145">Redefinir a ID de conferência de reunião</span><span class="sxs-lookup"><span data-stu-id="c7ec7-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="c7ec7-146">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-146">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="c7ec7-147">Vá para o **centro de administração do Office 365** > **do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="c7ec7-148">No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **Audioconferência**, e no painel Ação, em **ID da conferência**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="c7ec7-149">Na janela **Redefinir o ID da conferência?** , clique **Sim**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-149">In the ** Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="c7ec7-150">Um ID de conferência será criado automaticamente e um email será enviado ao usuário com o novo ID de conferência, se o envio de email para seus usuários estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="c7ec7-151">Está ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="c7ec7-152">[!IMPORTANTE] Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="c7ec7-153">Você deve notificar os usuários para reagendar os convites de reunião para garantir que o novo ID da conferência seja inserido nos convites.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="c7ec7-154">Os usuários podem usar a Ferramenta de Migração de Reunião do Skype for Business para atualizar suas reuniões marcadas.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-154">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="c7ec7-155">Para ver como baixar, instalar e executar a Ferramenta de Atualização de Reunião do Skype for Business, consulte: [Ferramenta de Atualização de Reunião do Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Ferramenta de Migração de Reunião (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047)e [Skype for Business Online, Ferramenta de Migração de Reunião (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-155">To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and Lync  Skype for Business Online, Meeting Migration Tool (64-bit)  Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>

<span data-ttu-id="c7ec7-156">Veja [Redefinir o ID de conferência para um usuário](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="c7ec7-157">Redefinir o PIN de um organizador da conferência</span><span class="sxs-lookup"><span data-stu-id="c7ec7-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="c7ec7-158">A cada reunião agendada por um usuário será atribuído um ID de conferência único.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-158">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="c7ec7-159">Embora um ID de conferência seja criado e atribuído a um usuário automaticamente, podem existir ocasiões em que um usuário não deseje usá-lo e você precise configurá-lo para um determinado número, ou seus usuários não lembrem ou tenham perdido o ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-159">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> <span data-ttu-id="c7ec7-160">Você pode usar o centro de administração do Skype for Business e o Windows PowerShell para exibir, alterar e redefinir seu ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="c7ec7-161">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-161">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="c7ec7-162">Vá para o **centro de administração do Office 365** > **do Skype for Business** e, no painel de navegação esquerdo, clique em **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-162">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**</span></span>

3. <span data-ttu-id="c7ec7-163">Clique em **Usuários**, e selecione o usuário para o qual você deseja redefinir o PIN.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-163">Click on **Dial-in users**, select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="c7ec7-164">No painel de Ação, em **PIN**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-164">In the Action pane, click **Reset PIN**.</span></span>

<span data-ttu-id="c7ec7-165">Os usuários receberão um email com seu PIN quando estiverem habilitados para a audioconferência ou quando o PIN for redefinido.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-165">Users will receive an email with their PIN when they're enabled for dial-in conferencing or when the PIN is reset.</span></span> <span data-ttu-id="c7ec7-166">Entretanto, se você desabilitou o envio automático de emails, o email de redefinição do PIN não será enviado e você deverá enviar manualmente o PIN para o usuário.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-166">But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="c7ec7-167">O PIN será exibido somente uma vez depois de ser redefinido.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="c7ec7-168">Depois de ser exibido, logo após ser redefinido, o PIN não será mais mostrado nas propriedades do usuário; em vez disso, será mostrado \*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-168">Once it's displayed just after being reset, the PIN won't be shown anymore on the user properties and instead \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="c7ec7-169">Consulte [Redefinir o PIN da Audioconferência](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-169">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin.md)</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="c7ec7-170">Enviar um email com informações da Audioconferência para um usuário</span><span class="sxs-lookup"><span data-stu-id="c7ec7-170">Send an email to a user with their Audio Conferencing information</span></span>

1. <span data-ttu-id="c7ec7-171">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-171">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="c7ec7-172">Vá para o **centro de administração do Office 365** > **do Skype for Business** e, no painel de navegação esquerdo, clique em **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-172">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**</span></span>

3. <span data-ttu-id="c7ec7-173">Clique em **Usuários**, e selecione o usuário para o qual você deseja redefinir o PIN.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-173">Click on **Dial-in users**, select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="c7ec7-174">No painel Ação, clique em **Enviar informações da conferência por email**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c7ec7-175">Ao fazer isso, o PIN da audioconferência não é enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-175">When you do this, the dial-in conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="c7ec7-176">Veja [Enviar um email para um usuário com as informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="c7ec7-177">Definir os números de telefone incluídos em convites</span><span class="sxs-lookup"><span data-stu-id="c7ec7-177">Set the phone numbers included on invites</span></span>

1. <span data-ttu-id="c7ec7-178">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-178">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="c7ec7-179">Vá para o **centro de administração do Office 365** > **do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-179">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="c7ec7-180">No painel de navegação esquerdo, vá para **Audioconferência** > **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="c7ec7-181">Selecione o usuário que você deseja habilitar para a Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-181">Select the user that you want to enable for dial-in conferencing.</span></span>

4. <span data-ttu-id="c7ec7-182">No painel de Ação você pode definir o **Número de chamada tarifada** e, se permitido, o **Número de chamada gratuita**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="c7ec7-183">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-183">Click **Save**.</span></span>

<span data-ttu-id="c7ec7-184">Consulte [Definir os números de telefone incluídos em convites](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-184">[Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md)</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="c7ec7-185">Escolher as configurações de ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="c7ec7-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="c7ec7-186">**Definir a experiência da reunião quando quem está ligando ingressa em uma reunião**</span><span class="sxs-lookup"><span data-stu-id="c7ec7-186">**** Set the meeting experience when callers join a meeting</span></span>


1. <span data-ttu-id="c7ec7-187">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-187">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="c7ec7-188">Vá para o **centro de administração do Office 365** > **do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-188">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="c7ec7-189">No **centro de administração do Skype for Business**, no painel de navegação esquerdo, acesse **Audioconferência** > **Configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-189">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="c7ec7-190">Em **Experiência de participação na reunião**, selecione as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="c7ec7-190">Under **Meeting join experience** select the following actions:</span></span>

  - <span data-ttu-id="c7ec7-191">**Habilitar notificações de entrada e saída de reunião** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="c7ec7-192">Se você desmarcar essa caixa de seleção, por padrão, os usuários que já tenham ingressado na reunião não serão notificados quando alguém entrar ou sair.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-192">However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

    <span data-ttu-id="c7ec7-193">Isso pode ser definido para cada reunião quando um usuário entra em uma reunião usando um aplicativo do Skype for Business e modifica a configuração no Skype Meeting **Anunciar quando as pessoas entram ou saem** no menu da reunião **Opções**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business client and they modify the **Announce when people enter or leave** setting in the Skype Meeting Options menu of the meeting.</span></span>

  - <span data-ttu-id="c7ec7-194">**Solicitar que os autores de chamadas registrem seus nomes antes de ingressar na reunião** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-194">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="c7ec7-195">Se você desmarcar essa caixa de seleção, os participantes não precisarão registrar seu nome antes de ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-195">However, if you uncheck it, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="c7ec7-196">Depois de fazer suas alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="c7ec7-197">Consulte [Alterar as configurações de uma ponte de Audioconferência](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-197">[Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span></span>
  
 <span data-ttu-id="c7ec7-198">**Definir o comprimento do PIN para reuniões**</span><span class="sxs-lookup"><span data-stu-id="c7ec7-198">**** Set the PIN length for meetings</span></span>

1. <span data-ttu-id="c7ec7-199">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-199">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="c7ec7-200">Vá para o **centro de administração do Office 365** > **do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-200">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="c7ec7-201">No **centro de administração do Skype for Business**, no painel de navegação esquerdo, acesse **Audioconferência** > **Configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-201">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="c7ec7-202">Em **Segurança**, insira o número de dígitos que você deseja para o PIN na lista **Comprimento do PIN** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-202">Under **Security**PIN length > enter the number of digits you want for the PIN and then click **Save**.</span></span>

    <span data-ttu-id="c7ec7-203">O PIN deve ter entre 4 e 12 dígitos.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="c7ec7-204">O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-204">The default is 5.</span></span>
    
<span data-ttu-id="c7ec7-205">Consulte [Alterar as configurações de uma ponte de Audioconferência](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-205">[Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span></span>
  
 <span data-ttu-id="c7ec7-206">**Ativar ou desativar o envio de email para usuários de áudio**</span><span class="sxs-lookup"><span data-stu-id="c7ec7-206">**** Enable or disable email from being sent to dial-in users</span></span>

1. <span data-ttu-id="c7ec7-207">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-207">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="c7ec7-208">Vá para o **centro de administração do Office 365** > **do Skype for Business** e, no painel de navegação esquerdo, clique em **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**</span></span>

3. <span data-ttu-id="c7ec7-209">Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="c7ec7-210">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-210">Click **Save**.</span></span>

    <span data-ttu-id="c7ec7-211">Você também pode enviar um email para o usuário com as configurações da audioconferência acessando as propriedades de audioconferência do usuário e clicando em **Enviar informações da conferência via email**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-211">You can also send email to the user with the dial-in conferencing settings, by going to the user's properties > **Dial-in conferencingSend conference info via email**.</span></span>

    <span data-ttu-id="c7ec7-212">Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="c7ec7-213">Veja [Enviar um email para um usuário com as informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="c7ec7-214">Veja e defina os idiomas principal (padrão) e secundário (alternativo) em uma ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="c7ec7-214">See and set the primary and secondary languages on a dial-in conferencing bridge</span></span>


1. <span data-ttu-id="c7ec7-215">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-215">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="c7ec7-216">Vá para o **centro de administração do Office 365** > **do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="c7ec7-217">No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **Audioconferência** e clique em **Ponte Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-217">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="c7ec7-218">Selecione um número de telefone da lista, clique em **Definir idiomas** no painel de Ação e depois na página **Configurar idiomas** clique uso da lista de **Idioma principal** para exibir a lista completa dos idiomas com suporte.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-218">In the Action pane, select the phone number from the list, click **Set languages** and then on the **Set languages** page, click the drop-down under **Primary language** to view the complete list of supported languages.</span></span>

    <span data-ttu-id="c7ec7-219">Você também pode definir os idiomas primário e secundário com suporte quando você seleciona Microsoft como o provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.</span></span> <span data-ttu-id="c7ec7-220">A ordem que você seleciona nas listas é a mesma ordem em que os idiomas serão apresentados aos autores de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="c7ec7-221">Veja [Definir idiomas do assistente automático para Audioconferência](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="c7ec7-222">Consultar os números de discagem de audioconferência</span><span class="sxs-lookup"><span data-stu-id="c7ec7-222">See dial-in conferencing dial-in numbers</span></span>

1. <span data-ttu-id="c7ec7-223">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-223">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="c7ec7-224">Vá para o **centro de administração do Office 365** > **do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-224">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="c7ec7-225">No **centro de administração do Skype for Business**, no painel de navegação esquerdo, acesse **Audioconferência** > **Ponte Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-225">In the **Skype for Business admin center**, in the left navigation go to **dial-in conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="c7ec7-226">Aqui você pode:</span><span class="sxs-lookup"><span data-stu-id="c7ec7-226">Here you can Discover additional bots.</span></span>

  - <span data-ttu-id="c7ec7-227">Exibir os números de telefone definidos pelo Office 365 para a Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-227">You can view the phone numbers that are set by Office 365 to be used for dial-in conferencing.</span></span>

  - <span data-ttu-id="c7ec7-228">Exibir o local e o idioma principal e secundário que será usado pelo assistente automático da Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-228">You can also view the location, and the primary and secondary languages that will be used by the dial-in conferencing auto attendant.</span></span>

  - <span data-ttu-id="c7ec7-229">Selecionar o número de telefone padrão que será fornecido aos usuários quando eles forem habilitados para a Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-229">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.</span></span> <span data-ttu-id="c7ec7-230">No entanto, se o número de telefone padrão da ponte de audioconferência for alterado, o número de telefone padrão dos usuários existentes não será alterado.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-230">However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="c7ec7-231">Você pode ir para **Audioconferência** > **Usuários** e selecionar as propriedades do usuário para alterar o número padrão do usuário selecionando um número novo da lista de números disponíveis na sua organização.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-231">You can go to **Dial-in conferencing** > **Dial-in users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="c7ec7-232">Consulte [Ver uma lista de números de Audioconferência](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-232">[See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md)</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="c7ec7-233">Ver uma lista de usuários habilitados</span><span class="sxs-lookup"><span data-stu-id="c7ec7-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="c7ec7-234">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-234">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="c7ec7-235">Vá para o **centro de administração do Office 365** > **do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-235">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="c7ec7-236">No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **Audioconferência** e clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-236">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing**> and then **Dial-in users**.</span></span>

<span data-ttu-id="c7ec7-237">Consulte [Ver uma lista de usuários habilitados para Audioconferência](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c7ec7-238">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c7ec7-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="c7ec7-239">Existem várias configurações que você pode gerenciar no nível da organização usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-239">There are several settings that you can manage settings at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="c7ec7-240">Isso facilita a aplicação de configurações a todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-240">This makes it easy to make these settings and have them apply to all of your users.</span></span>

<span data-ttu-id="c7ec7-241">Para obter mais ajuda sobre cada cmdlet, consulte [Cmdlets do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=627324).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="c7ec7-242">Aqui estão as configurações no nível da organização:</span><span class="sxs-lookup"><span data-stu-id="c7ec7-242">Here are the performance settings:</span></span>

- <span data-ttu-id="c7ec7-243">**Configurar notificações de entrada/saída** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="c7ec7-244">**Configurar registro de nome** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-244">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="c7ec7-245">**Configurar comprimento do PIN** O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-245">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="c7ec7-246">**Configurar apenas reuniões por telefone** O padrão _$false_.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="c7ec7-247">**Configurar o envio de email para usuários** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="c7ec7-248">**Configurar o envio de email a partir de uma conta diferente** O padrão é _$false_.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="c7ec7-249">**Configurar o endereço De no email enviado aos usuários** O padrão é _$null_.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="c7ec7-250">**Configurar o nome para exibição do email que é enviado aos usuários** O padrão é _$null_.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c7ec7-251">Quer saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c7ec7-251">Want to know more about Windows Powershell?</span></span>
- <span data-ttu-id="c7ec7-p119">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c7ec7-p119">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="c7ec7-255">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="c7ec7-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="c7ec7-256">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7ec7-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="c7ec7-257">O Windows PowerShell tem muitas vantagens de velocidade, simplicidade e produtividade em comparação ao uso exclusivo do centro de administração do Office 365, por exemplo quando você realiza alterações de configurações para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c7ec7-258">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c7ec7-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="c7ec7-259">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c7ec7-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="c7ec7-260">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c7ec7-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="c7ec7-261">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c7ec7-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="c7ec7-p121">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="c7ec7-264">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c7ec7-264">Related topics</span></span>

[<span data-ttu-id="c7ec7-265">Gerenciar as configurações de Audioconferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="c7ec7-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


