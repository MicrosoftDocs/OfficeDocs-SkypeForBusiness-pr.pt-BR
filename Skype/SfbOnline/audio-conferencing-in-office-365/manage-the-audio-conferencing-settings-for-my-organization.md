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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Consulte etapas do Skype for Business Online para atribuir uma licença de conferência discada e uma ID de conferência a um usuário e muitas outras configurações de conferência discada. '
ms.openlocfilehash: eb0212bcd7c03fac619efa2749a8308097f75505
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114227"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="aeb56-103">Gerenciar as configurações da Audioconferência para minha organização no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="aeb56-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="aeb56-104">Se você quiser gerenciar essas configurações em equipes, consulte [Gerenciar as configurações de Audioconferência para minha organização no Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span><span class="sxs-lookup"><span data-stu-id="aeb56-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="aeb56-105">Pode ser mais fácil para você ver todas as configurações de audioconferência do Skype for Business em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="aeb56-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="aeb56-106">Atribuir uma licença de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="aeb56-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="aeb56-107">Não é possível atribuir licenças usando o **Centro de administração do Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="aeb56-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="aeb56-108">Você deve usar o Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aeb56-108">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="aeb56-109">Consulte [Atribuir licenças do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="aeb56-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="aeb56-110">**Para atribuir uma licença para um usuário**</span><span class="sxs-lookup"><span data-stu-id="aeb56-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="aeb56-111">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="aeb56-111">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="aeb56-112">Na navegação à esquerda do centro de administração, vá para **Usuários**  >  **Usuários ativos e** selecione o usuário ou os usuários na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="aeb56-112">In the left navigation of the admin center, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aeb56-113">[!DICA] Para atribuir licenças a mais de 20 usuários ao mesmo tempo, você pode usar o menu suspenso **Selecionar uma exibição** e escolher uma das opções ou criar sua própria exibição.</span><span class="sxs-lookup"><span data-stu-id="aeb56-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="aeb56-114">Em seguida, **clique** em Editar , **Em** seguida, selecione a licença e clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="aeb56-115">Você também pode atribuir licenças a vários usuários usando o Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="aeb56-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="aeb56-116">Para obter instruções e scripts de amostra do PowerShell, consulte [Atribuir licenças do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="aeb56-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="aeb56-117">No painel Ação em **Licenças de**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="aeb56-118">Na página **Licenças de produtos**, ligue a **Audioconferência** e em seguida clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="aeb56-119">Para mais informações sobre licenciamento, consulte [Licenciamento de complementos do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="aeb56-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="aeb56-120">Depois de atribuir a licença, a Microsoft pode não aparecer inicialmente na lista como um provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="aeb56-120">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="aeb56-121">Se isso acontecer, saia do centro de administração ou pressione CTRL+F5 para atualizar a janela do navegador.</span><span class="sxs-lookup"><span data-stu-id="aeb56-121">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="aeb56-122">Habilitar ou desabilitar emails enviados para usuários de audioconferência</span><span class="sxs-lookup"><span data-stu-id="aeb56-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="aeb56-123">![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="aeb56-123">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="aeb56-124">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="aeb56-124">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="aeb56-125">Vá para o centro de administração > **Skype for Business** e, na navegação à esquerda, clique em **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-125">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="aeb56-126">Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="aeb56-127">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-127">Click **Save**.</span></span>

    <span data-ttu-id="aeb56-128">Você também pode enviar emails para o usuário com as configurações de audioconferência indo para as propriedades de audioconferência do usuário e clicando em Enviar informações de conferência **por email**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-128">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="aeb56-129">A ID da conferência e o número de telefone de audioconferência padrão estão incluídos no convite da reunião, mas não no PIN.</span><span class="sxs-lookup"><span data-stu-id="aeb56-129">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="aeb56-130">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="aeb56-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="aeb56-131">**Usando Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="aeb56-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="aeb56-132">Também é possível usar o Windows PowerShell e executar:</span><span class="sxs-lookup"><span data-stu-id="aeb56-132">You can also use the Windows PowerShell and run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="aeb56-133">Você pode usar [o Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) para gerenciar outras configurações para sua organização, incluindo email.</span><span class="sxs-lookup"><span data-stu-id="aeb56-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="aeb56-134">Alterar as informações de contato do remetente em mensagens de email enviadas aos usuários</span><span class="sxs-lookup"><span data-stu-id="aeb56-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="aeb56-135">Você pode fazer alterações no email que é enviado automaticamente para seus usuários, incluindo o endereço de email real e o nome de exibição das informações de contato do remetente.</span><span class="sxs-lookup"><span data-stu-id="aeb56-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="aeb56-136">Por padrão, o remetente dos emails é o Microsoft 365 ou o Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="aeb56-136">By default, the sender of the emails is Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="aeb56-137">Para fazer alterações no endereço de email que está enviando o email para os usuários, você deve:</span><span class="sxs-lookup"><span data-stu-id="aeb56-137">To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="aeb56-138">Insira o endereço de email no _parâmetro SendEmailFromAddress._</span><span class="sxs-lookup"><span data-stu-id="aeb56-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="aeb56-139">Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="aeb56-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="aeb56-140">Defina o parâmetro _SendEmailOverride_ como _Verdadeiro_.</span><span class="sxs-lookup"><span data-stu-id="aeb56-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="aeb56-141">Você pode fazer alterações nos emails enviados para usuários, como o endereço de email que envia as mensagens ou o nome de exibição do email executando:</span><span class="sxs-lookup"><span data-stu-id="aeb56-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="aeb56-142">Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado.</span><span class="sxs-lookup"><span data-stu-id="aeb56-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="aeb56-143">Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) para gerenciar outras configurações para sua organização, incluindo email.</span><span class="sxs-lookup"><span data-stu-id="aeb56-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="aeb56-144">Consulte [Emails que são enviados automaticamente aos usuários quando suas configurações de Audioconferência mudam](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="aeb56-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="aeb56-145">Redefinir a ID de conferência de reunião</span><span class="sxs-lookup"><span data-stu-id="aeb56-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="aeb56-146">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="aeb56-146">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="aeb56-147">Vá para o centro de administração > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-147">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="aeb56-148">No **centro de administração do Skype for Business**, no painel de navegação esquerdo, vá para **Audioconferência**, e no painel Ação, em **ID da conferência**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="aeb56-149">Na janela **Redefinir iD** da conferência? clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-149">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="aeb56-150">Um ID de conferência será criado automaticamente e um email será enviado ao usuário com o novo ID de conferência, se o envio de email para seus usuários estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="aeb56-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="aeb56-151">Está ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="aeb56-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="aeb56-152">[!IMPORTANTE] Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores.</span><span class="sxs-lookup"><span data-stu-id="aeb56-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="aeb56-153">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites.</span><span class="sxs-lookup"><span data-stu-id="aeb56-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="aeb56-154">Os usuários podem usar a Ferramenta de Migração de Reunião do Skype for Business para atualizar suas reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="aeb56-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="aeb56-155">Para ver como baixar, instalar e executar a Ferramenta de Atualização de Reunião do Skype for Business, consulte: Ferramenta de Atualização de Reunião para Skype for Business e [Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), Skype for Business Online, Ferramenta de Migração de Reunião [(64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)e Skype for Business Online, Ferramenta de Migração de Reunião  [(32 bits)](https://www.microsoft.com/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="aeb56-155">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="aeb56-156">Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="aeb56-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="aeb56-157">Redefinir o PIN de um organizador da conferência</span><span class="sxs-lookup"><span data-stu-id="aeb56-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="aeb56-158">Cada reunião agendada por um usuário receberá uma ID de conferência exclusiva.</span><span class="sxs-lookup"><span data-stu-id="aeb56-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="aeb56-159">Embora uma ID de conferência seja criada e atribuída automaticamente a um usuário, pode haver momentos em que um usuário não deseja usá-lo e você deseja defini-lo como um determinado número, ou seus usuários não podem se lembrar ou perder a ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="aeb56-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="aeb56-160">Você pode usar o centro de administração do Skype for Business e o Windows PowerShell para exibir, alterar e redefinir seu ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="aeb56-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="aeb56-161">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="aeb56-161">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="aeb56-162">Vá para o centro de administração > **Skype for Business** e, na navegação à esquerda, clique em **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-162">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="aeb56-163">Clique **em Usuários** e selecione o usuário para o que você deseja redefinir o PIN.</span><span class="sxs-lookup"><span data-stu-id="aeb56-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="aeb56-164">No painel Ação, em **PIN,** clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="aeb56-165">Os usuários receberão um email com seu PIN quando eles estão habilitados para audioconferência ou quando o PIN é redefinido.</span><span class="sxs-lookup"><span data-stu-id="aeb56-165">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="aeb56-166">Mas se você tiver desabilitado o envio automático de emails, um email de redefinição de PIN não será enviado e você terá que enviar manualmente o PIN para o usuário.</span><span class="sxs-lookup"><span data-stu-id="aeb56-166">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="aeb56-167">O PIN será exibido somente uma vez depois de ser redefinido.</span><span class="sxs-lookup"><span data-stu-id="aeb56-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="aeb56-168">Depois que ele é exibido logo após ser redefinido, o PIN não será mais mostrado nas propriedades do usuário; em vez disso, \*\*\*\*\* será mostrado.</span><span class="sxs-lookup"><span data-stu-id="aeb56-168">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="aeb56-169">Consulte [Redefinir o PIN de Audioconferência](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="aeb56-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="aeb56-170">Enviar um email com informações de Audioconferência para um usuário</span><span class="sxs-lookup"><span data-stu-id="aeb56-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="aeb56-171">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="aeb56-171">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="aeb56-172">Vá para o centro de administração > **Skype for Business** e, na navegação à esquerda, clique em **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-172">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="aeb56-173">Clique **em Usuários** e selecione o usuário para o que você deseja redefinir o PIN.</span><span class="sxs-lookup"><span data-stu-id="aeb56-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="aeb56-174">No painel Ação, clique em **Enviar informações da conferência por email**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aeb56-175">Quando você faz isso, o PIN de audioconferência não é enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="aeb56-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="aeb56-176">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="aeb56-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="aeb56-177">Definindo os números de telefone incluídos em convites</span><span class="sxs-lookup"><span data-stu-id="aeb56-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="aeb56-178">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="aeb56-178">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="aeb56-179">Vá para o centro de administração > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-179">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="aeb56-180">No painel de navegação esquerdo, vá para **Audioconferência** > **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="aeb56-181">Selecione o usuário que você deseja habilitar para Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="aeb56-181">Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="aeb56-182">No painel de Ação você pode definir o **Número de chamada tarifada** e, se permitido, o **Número de chamada gratuita**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="aeb56-183">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-183">Click **Save**.</span></span>

<span data-ttu-id="aeb56-184">Consulte [Definir os números de telefone incluídos em convites](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="aeb56-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="aeb56-185">Escolher as configurações de ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="aeb56-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="aeb56-186">**Definir a experiência de reunião quando os chamadores ingressarem em uma reunião**</span><span class="sxs-lookup"><span data-stu-id="aeb56-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="aeb56-187">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="aeb56-187">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="aeb56-188">Vá para o centro de administração > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-188">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="aeb56-189">No Centro de administração do **Skype for Business**, na navegação à esquerda, vá para Configurações de ponte da Microsoft de **audioconferência.**  >  </span><span class="sxs-lookup"><span data-stu-id="aeb56-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="aeb56-190">Em **Experiência de junção de reunião,** selecione as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="aeb56-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="aeb56-191">**Habilitar a ativação de notificações de entrada e saída de reunião** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="aeb56-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="aeb56-192">Se você limpar essa caixa de seleção, os usuários que já ingressaram na reunião por padrão não serão notificados quando alguém entrar ou sair da reunião.</span><span class="sxs-lookup"><span data-stu-id="aeb56-192">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="aeb56-193">Isso pode ser definido em uma base de reunião por reunião quando um usuário ingresse em uma reunião usando um aplicativo do Skype for Business e eles modificam a configuração Anunciar quando as pessoas entram ou saem no **menu** Opções de Reunião do Skype da reunião. </span><span class="sxs-lookup"><span data-stu-id="aeb56-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="aeb56-194">**Peça que os chamadores registrem seus nomes antes de ingressar na reunião** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="aeb56-194">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="aeb56-195">Se você limpar essa caixa de seleção, os chamadores não serão solicitados a gravar seus nomes antes de ingressarem em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="aeb56-195">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="aeb56-196">Depois de fazer suas alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="aeb56-197">Consulte [Alterar as configurações de uma ponte de Audioconferência.](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="aeb56-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="aeb56-198">**Definir o tamanho do PIN para reuniões**</span><span class="sxs-lookup"><span data-stu-id="aeb56-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="aeb56-199">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="aeb56-199">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="aeb56-200">Vá para o centro de administração > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-200">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="aeb56-201">No Centro de administração do **Skype for Business**, na navegação à esquerda, vá para Configurações de ponte da Microsoft de **audioconferência.**  >  </span><span class="sxs-lookup"><span data-stu-id="aeb56-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="aeb56-202">Em **Segurança**, insira o número de dígitos que você deseja para o PIN na lista de comprimento **do PIN** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="aeb56-203">O PIN deve ter entre 4 e 12 dígitos.</span><span class="sxs-lookup"><span data-stu-id="aeb56-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="aeb56-204">O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="aeb56-204">The default is 5.</span></span>
    
<span data-ttu-id="aeb56-205">Consulte [Alterar as configurações de uma ponte de Audioconferência.](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="aeb56-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="aeb56-206">**Habilitar ou desabilitar o envio de emails para usuários de áudio**</span><span class="sxs-lookup"><span data-stu-id="aeb56-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="aeb56-207">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="aeb56-207">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="aeb56-208">Vá para o centro de administração > **Skype for Business** e, na navegação à esquerda, clique em **Audioconferência**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-208">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="aeb56-209">Na página **Configurações de ponte da Microsoft** , marque ou desmarque **Enviar emails para os usuários automaticamente se as suas configurações de audioconferência mudarem**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="aeb56-210">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-210">Click **Save**.</span></span>

    <span data-ttu-id="aeb56-211">Você também pode enviar emails para o usuário com as configurações de audioconferência, indo para as propriedades de audioconferência do usuário e clicando em Enviar informações de conferência **por email**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="aeb56-212">Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.</span><span class="sxs-lookup"><span data-stu-id="aeb56-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="aeb56-213">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="aeb56-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="aeb56-214">Consulte e defina os idiomas principal (padrão) e secundário (alternativo) em uma ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="aeb56-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="aeb56-215">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="aeb56-215">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="aeb56-216">Vá para o centro de administração > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-216">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="aeb56-217">No Centro de administração do **Skype for Business,** na navegação à esquerda, vá para **Audioconferência** e clique em **Ponte da Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="aeb56-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="aeb56-218">Selecione um número de telefone na lista, clique em Definir  idiomas no painel Ação  e, na página Definir idiomas, clique na lista usar o idioma principal para exibir a lista completa de idiomas com suporte. </span><span class="sxs-lookup"><span data-stu-id="aeb56-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="aeb56-219">Você também pode definir os idiomas primários e secundários com suporte ao selecionar a Microsoft como provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="aeb56-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="aeb56-220">A ordem que você seleciona nas listas é a mesma ordem em que os idiomas serão apresentados aos autores de chamadas.</span><span class="sxs-lookup"><span data-stu-id="aeb56-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="aeb56-221">Veja [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="aeb56-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="aeb56-222">Consulte números de discagem de audioconferência</span><span class="sxs-lookup"><span data-stu-id="aeb56-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="aeb56-223">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="aeb56-223">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="aeb56-224">Vá para o centro de administração > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-224">Go to the admin center > **Skype for Business**.</span></span>
 
3. <span data-ttu-id="aeb56-225">No Centro **de administração do Skype for Business**, na navegação à esquerda, vá para **Audioconferência**  >  **ponte microsoft**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-225">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="aeb56-226">Aqui você pode:</span><span class="sxs-lookup"><span data-stu-id="aeb56-226">Here you can:</span></span>

   - <span data-ttu-id="aeb56-227">Exibir os números de telefone definidos pelo Microsoft 365 ou Office 365 a serem usados para Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="aeb56-227">View the phone numbers that are set by Microsoft 365 or Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="aeb56-228">Exibir o local e os idiomas primários e secundários que serão usados pelo atendimento automático de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="aeb56-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="aeb56-229">Selecione o número de telefone padrão que será dado aos usuários quando eles estão habilitados para Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="aeb56-229">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="aeb56-230">No entanto, se o número de telefone padrão da ponte de audioconferência mudar, o número de telefone padrão para usuários existentes não mudará.</span><span class="sxs-lookup"><span data-stu-id="aeb56-230">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="aeb56-231">Você pode ir até Usuários de **Audioconferência** e selecionar as propriedades do usuário para alterar o número padrão de um usuário escolhendo um novo número na lista de números que estão disponíveis em  >   sua organização.</span><span class="sxs-lookup"><span data-stu-id="aeb56-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="aeb56-232">Consulte [Ver uma lista de números de Audioconferência](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="aeb56-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="aeb56-233">Visualizar uma lista de usuários habilitados</span><span class="sxs-lookup"><span data-stu-id="aeb56-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="aeb56-234">Entre com sua conta de trabalho ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="aeb56-234">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="aeb56-235">Vá para o centro de administração > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="aeb56-235">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="aeb56-236">No Centro de administração do **Skype for Business**, na navegação à esquerda, vá para **Audioconferência**> **e,** em seguida, Usuários .</span><span class="sxs-lookup"><span data-stu-id="aeb56-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="aeb56-237">Veja [Ver uma lista de usuários habilitados para conferência de áudio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="aeb56-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="aeb56-238">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="aeb56-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="aeb56-239">Há várias configurações que você pode gerenciar no nível da organização usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aeb56-239">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="aeb56-240">Isso facilita a aplicação de configurações a todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="aeb56-240">This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="aeb56-241">Para obter mais ajuda sobre cada cmdlet, consulte [Cmdlets do Skype for Business Online](/previous-versions//mt228132(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="aeb56-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).</span></span>

<span data-ttu-id="aeb56-242">Aqui estão as configurações no nível da organização:</span><span class="sxs-lookup"><span data-stu-id="aeb56-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="aeb56-243">**Configurar notificações de entrada/saída** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="aeb56-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="aeb56-244">**Configurar registro de nome** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="aeb56-244">**Setting name recording** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="aeb56-245">**Configurar comprimento do PIN** O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="aeb56-245">**Setting the PIN length** The default is 5.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="aeb56-246">**Configurar apenas reuniões por telefone** O padrão _$false_.</span><span class="sxs-lookup"><span data-stu-id="aeb56-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="aeb56-247">**Configurar o envio de email para usuários** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="aeb56-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="aeb56-248">**Configurar o envio de email a partir de uma conta diferente** O padrão é _$false_.</span><span class="sxs-lookup"><span data-stu-id="aeb56-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="aeb56-249">**Configurar o endereço De no email enviado aos usuários** O padrão é _$null_.</span><span class="sxs-lookup"><span data-stu-id="aeb56-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="aeb56-250">**Configurar o nome para exibição do email que é enviado aos usuários** O padrão é _$null_.</span><span class="sxs-lookup"><span data-stu-id="aeb56-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="aeb56-251">Deseja saber mais sobre Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aeb56-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="aeb56-252">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="aeb56-252">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="aeb56-253">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="aeb56-253">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="aeb56-254">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="aeb56-254">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="aeb56-255">Por que você precisa usar o Microsoft 365 ou o Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="aeb56-255">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="aeb56-256">[Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="aeb56-256">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

- <span data-ttu-id="aeb56-257">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do centro de administração, como quando você está fazendo alterações de configurações para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="aeb56-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="aeb56-258">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="aeb56-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="aeb56-259">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="aeb56-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="aeb56-260">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="aeb56-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="aeb56-261">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="aeb56-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    <span data-ttu-id="aeb56-p121">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="aeb56-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="aeb56-264">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="aeb56-264">Related topics</span></span>

[<span data-ttu-id="aeb56-265">Gerenciar as configurações de audioconferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="aeb56-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)