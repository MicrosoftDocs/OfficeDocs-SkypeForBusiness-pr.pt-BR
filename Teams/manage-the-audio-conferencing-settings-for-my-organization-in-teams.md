---
title: Gerenciar as configurações de audioconferência para a minha organização no Microsoft Teams
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Consulte as etapas para atribuir uma licença de conferência discada e um ID de conferência a um usuário no Microsoft Teams e várias outras configurações de conferência discada. '
ms.openlocfilehash: 7af89da74b0b83872954444a847d40f0d7851087
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884701"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a><span data-ttu-id="82822-103">Gerenciar as configurações de audioconferência para a minha organização no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82822-103">If you want to manage these settings in Teams, see Manage the Audio Conferencing settings for my organization in Microsoft Teams.</span></span>

<span data-ttu-id="82822-104">Pode ser mais fácil para você visualizar todas as configurações de audioconferência em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="82822-104">It might be easier for you to see all of the dial-in conferencing settings in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="82822-105">Atribui licença de audioconferência</span><span class="sxs-lookup"><span data-stu-id="82822-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="82822-106">Não é possível atribuir licenças usando o Teams.</span><span class="sxs-lookup"><span data-stu-id="82822-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="82822-107">É necessário usar o centro de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="82822-107">You can use the Office 365 admin center though too.</span></span> <span data-ttu-id="82822-108">Consulte [Atribuir licenças do Skype for Business e do Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="82822-108">[Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)</span></span> 
  
 <span data-ttu-id="82822-109">**Atribuir uma licença a um usuário**</span><span class="sxs-lookup"><span data-stu-id="82822-109">\*\*\*\* To assign a license for a user</span></span>
  
1. <span data-ttu-id="82822-110">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="82822-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="82822-111">No painel de navegação esquerdo do **centro de administração do Office 365**, vá para **Usuários** > **Usuários ativos**, e selecione o usuário ou os usuários na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="82822-111">In the left navigation of the Office 365 admin center, go to Users  Active users > and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="82822-112">[!DICA] Para atribuir licenças a mais de 20 usuários ao mesmo tempo, você pode usar o menu suspenso **Selecionar uma exibição** e escolher uma das opções ou criar sua própria exibição.</span><span class="sxs-lookup"><span data-stu-id="82822-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="82822-113">Em seguida, clique em **Editar**, **Próximo** duas vezes, selecione a licença e clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="82822-113">Then click **Edit**Next**Next** then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="82822-114">No painel Ação em **Licenças de produto**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="82822-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="82822-115">Na página **Licenças de produto**, ative **Audioconferência** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="82822-115">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="82822-116">Para obter mais informações sobre licenças, consulte [Licenciamento de complementos do Skype for Business e do Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="82822-116">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
> [!NOTE]
> <span data-ttu-id="82822-117">Depois de atribuir a licença, a Microsoft pode não aparecer inicialmente na lista como provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="82822-117">After you assign the license, Microsoft might not appear initially in the drop-down as a dial-in conferencing provider.</span></span> <span data-ttu-id="82822-118">Caso isso aconteça, saia do centro de administração do Office 365 ou pressione CTRL+F5 para atualizar a janela do navegador.</span><span class="sxs-lookup"><span data-stu-id="82822-118">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="82822-119">Habilitar ou desabilitar o envio de e-mails para usuários de audioconferência</span><span class="sxs-lookup"><span data-stu-id="82822-119">Enable or disable emails from being sent to dial-in users</span></span>

<span data-ttu-id="82822-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**</span><span class="sxs-lookup"><span data-stu-id="82822-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="82822-121">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="82822-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="82822-122">No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="82822-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="82822-123">No painel **Configurações de ponte**, habilite ou desabilite **Enviar e-mails aos usuários automaticamente de suas configurações de discagem forem alteradas**.</span><span class="sxs-lookup"><span data-stu-id="82822-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="82822-124">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="82822-124">Click **Save**.</span></span>

    
<span data-ttu-id="82822-125">**Usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="82822-125">\*\*\*\* Using Windows PowerShell</span></span>
  
<span data-ttu-id="82822-126">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="82822-126">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="82822-127">Alterar as informações de contato do remetente das mensagens de e-mail enviadas aos usuários</span><span class="sxs-lookup"><span data-stu-id="82822-127">Change the senders contact information of email messages sent to users</span></span>

<span data-ttu-id="82822-128">É possível fazer alterações nos e-mails enviados automaticamente para seus usuários, incluindo o endereço de e-mail real e o nome de exibição das informações de contato do remetente.</span><span class="sxs-lookup"><span data-stu-id="82822-128">You can make changes to the email that is automatically sent to your users including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="82822-129">Por padrão, o remetente dos e-mails é o Office 365, mas é possível alterar o endereço de e-mail e o nome exibido com o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82822-129">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and theSet-CsOnlineDialInConferencingTenantSettings cmdlet.</span></span> <span data-ttu-id="82822-130">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="82822-130">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="82822-131">Redefinir o ID de conferência de reunião</span><span class="sxs-lookup"><span data-stu-id="82822-131">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="82822-132">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="82822-132">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="82822-133">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="82822-133">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="82822-134">Em **Audio conferência**, clique em **Redefinir ID de conferência**.</span><span class="sxs-lookup"><span data-stu-id="82822-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="82822-135">Na janela **Redefinir ID de conferência?**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="82822-135">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="82822-136">Um ID de conferência será criado automaticamente e um email será enviado ao usuário com o novo ID de conferência, se o envio de email para seus usuários estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="82822-136">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="82822-137">Está ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="82822-137">It's enabled by default.</span></span>

<span data-ttu-id="82822-138">Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="82822-138">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="82822-139">Redefinir o PIN de um organizador da conferência</span><span class="sxs-lookup"><span data-stu-id="82822-139">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="82822-140">Cada reunião agendada por um usuário terá um ID de conferência exclusivo atribuído.</span><span class="sxs-lookup"><span data-stu-id="82822-140">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="82822-141">Embora um ID de conferência seja automaticamente criado e atribuído a um usuário, pode haver ocasiões em que um usuário não queira usá-lo e você deseja configurá-lo para um certo número, ou os usuários não conseguem lembrar ou perderam o ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="82822-141">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> 

1. <span data-ttu-id="82822-142">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="82822-142">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="82822-143">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="82822-143">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="82822-144">Em **Audioconferência**, clique em **Redefinir PIN**, e então clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="82822-144">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
    
<span data-ttu-id="82822-145">Os usuários receberão um e-mail com o PIN quando forem habilitados para audioconferência ou quando o PIN for redefinido.</span><span class="sxs-lookup"><span data-stu-id="82822-145">Users will receive an email with their PIN when they're enabled for dial-in conferencing or when the PIN is reset.</span></span> <span data-ttu-id="82822-146">Entretanto, se você tiver desabilitado o envio automático de e-mails, o e-mail de redefinição de PIN não será enviado para o usuário e você precisará enviar o PIN manualmente.</span><span class="sxs-lookup"><span data-stu-id="82822-146">But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="82822-147">O PIN será exibido somente uma vez depois de ser redefinido.</span><span class="sxs-lookup"><span data-stu-id="82822-147">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="82822-148">Depois se ser exibido após a redefinição, o PIN não será mais mostrado nas propriedades do usuário e aparecerá como \*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="82822-148">Once it's displayed just after being reset, the PIN won't be shown anymore on the user properties and instead \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="82822-149">Veja [Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="82822-149">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="82822-150">Enviar um e-mail com as informações da audioconferência para um usuário</span><span class="sxs-lookup"><span data-stu-id="82822-150">Send an email to a user with their Audio Conferencing information</span></span>

1. <span data-ttu-id="82822-151">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="82822-151">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="82822-152">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="82822-152">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="82822-153">Em **Audioconferência**, clique em **Enviar informações da conferência por e-mail**.</span><span class="sxs-lookup"><span data-stu-id="82822-153">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="82822-154">Ao fazer isso, o PIN da audioconferência não é enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="82822-154">When you do this, the dial-in conferencing PIN isn't sent to the user.</span></span> 

  
<span data-ttu-id="82822-155">Consulte [Enviar um e-mail para um usuário com suas informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="82822-155">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="82822-156">Definir os números de telefone incluídos em convites</span><span class="sxs-lookup"><span data-stu-id="82822-156">Set the phone numbers included on invites</span></span>

1. <span data-ttu-id="82822-157">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="82822-157">In the **Skype for Business admin center**, in the left navigation go to Dial-in conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="82822-158">Próximo a **Audioconferência**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="82822-158">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="82822-159">No painel **Audioconferência**, é possível definir o **Número tarifado** e, se permitido, o **Número gratuito**.</span><span class="sxs-lookup"><span data-stu-id="82822-159">In the Action pane, you can set the Toll number and, if allowed, the Toll-free number.</span></span>

4. <span data-ttu-id="82822-160">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="82822-160">Click **Save**.</span></span>
    
<span data-ttu-id="82822-161">Consulte [Definir os números de telefone incluídos em convites](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="82822-161">[Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md)</span></span>
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="82822-162">Escolher as configurações de ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="82822-162">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="82822-163">**Definir a experiência da reunião quando os chamadores entram**</span><span class="sxs-lookup"><span data-stu-id="82822-163">\*\*\*\* Set the meeting experience when callers join a meeting</span></span>


1. <span data-ttu-id="82822-164">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="82822-164">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="82822-165">No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="82822-165">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="82822-166">No painel **Configurações da ponte**, ative ou desative **Notificações de entrada/saída de reuniões**.</span><span class="sxs-lookup"><span data-stu-id="82822-166">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="82822-167">Isso está ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="82822-167">CDR is enabled by default.</span></span> <span data-ttu-id="82822-168">Se você desativar essa opção, por padrão, os usuários que já entraram na reunião não serão notificados quando alguém entrar ou sair da reunião.</span><span class="sxs-lookup"><span data-stu-id="82822-168">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="82822-169">Em **Tipo de anúncio de entrada/saída**, escolha **Tons** ou **Nomes ou números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="82822-169">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="82822-170">Se escolher **Nomes ou números de telefone**, também será possível optar por ativar ou desativar **Solicitar que os chamadores gravem seu nome antes de entrar na reunião**.</span><span class="sxs-lookup"><span data-stu-id="82822-170">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="82822-171">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="82822-171">Click **Save**.</span></span>

    
<span data-ttu-id="82822-172">Consulte [Alterar as configurações de uma ponte de audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="82822-172">[Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>
  
 <span data-ttu-id="82822-173">**Definir o tamanho do PIN para reuniões**</span><span class="sxs-lookup"><span data-stu-id="82822-173">\*\*\*\* Set the PIN length for meetings</span></span>

1. <span data-ttu-id="82822-174">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="82822-174">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="82822-175">No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="82822-175">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="82822-176">No painel **Configurações da ponte**, insira o número de dígitos que deseja para o PIN na lista **Tamanho do PIN** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="82822-176">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="82822-177">O PIN deve ter entre 4 e 12 dígitos.</span><span class="sxs-lookup"><span data-stu-id="82822-177">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="82822-178">O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="82822-178">The default is 5.</span></span>

    
<span data-ttu-id="82822-179">Consulte [Alterar as configurações de uma ponte de audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="82822-179">[Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>
  
 <span data-ttu-id="82822-180">**Habilitar ou desabilitar o envio de e-mails para usuários de áudio**</span><span class="sxs-lookup"><span data-stu-id="82822-180">\*\*\*\* Enable or disable email from being sent to dial-in users</span></span>


1. <span data-ttu-id="82822-181">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="82822-181">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="82822-182">No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="82822-182">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="82822-183">No painel **Configurações da ponte**, ative ou desative **Enviar e-mails automaticamente aos usuários se suas configurações de audioconferência forem alteradas**.</span><span class="sxs-lookup"><span data-stu-id="82822-183">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="82822-184">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="82822-184">Click **Save**.</span></span> 
 
    <span data-ttu-id="82822-185">Você também pode enviar e-mails para o usuário com as configurações da audioconferência acessando as propriedades de audioconferência do usuário clicando em **Enviar informações da conferência por e-mail**.</span><span class="sxs-lookup"><span data-stu-id="82822-185">You can also send email to the user with the dial-in conferencing settings, by going to the user's properties > **Dial-in conferencingSend conference info via email**.</span></span>
    
    <span data-ttu-id="82822-186">Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.</span><span class="sxs-lookup"><span data-stu-id="82822-186">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="82822-187">Consulte [Enviar um e-mail para um usuário com suas informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="82822-187">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="82822-188">Visualizar e definir os idiomas primário (padrão) e secundários (alternativos) para uma ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="82822-188">See and set the primary and secondary languages on a dial-in conferencing bridge</span></span>

1. <span data-ttu-id="82822-189">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="82822-189">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="82822-190">Selecione um número de telefone na lista e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="82822-190">Select a number from the list of phone numbers and click **Assign**.</span></span>

3. <span data-ttu-id="82822-191">Escolha os idiomas desejados em **Idioma padrão** e **Idiomas alternativos (opcional)**.</span><span class="sxs-lookup"><span data-stu-id="82822-191">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>


<span data-ttu-id="82822-192">Consulte [Definir idiomas do atendedor automático para audioconferência](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="82822-192">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="82822-193">Visualizar os números de discagem de audioconferência</span><span class="sxs-lookup"><span data-stu-id="82822-193">See dial-in conferencing dial-in numbers</span></span>


1. <span data-ttu-id="82822-194">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="82822-194">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="82822-195">Selecione um número de telefone na lista e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="82822-195">Select a number from the list of phone numbers and click **Assign**.</span></span> <span data-ttu-id="82822-196">Aqui, você pode:</span><span class="sxs-lookup"><span data-stu-id="82822-196">Here you can Discover additional bots.</span></span>
    
  - <span data-ttu-id="82822-197">Visualizar os números de telefone definidos pelo Office 365 para serem usados para audioconferência.</span><span class="sxs-lookup"><span data-stu-id="82822-197">You can view the phone numbers that are set by Office 365 to be used for dial-in conferencing.</span></span> 
    
  - <span data-ttu-id="82822-198">Visualizar a localização e o idioma primário que serão usados pelo atendedor automático da audioconferência.</span><span class="sxs-lookup"><span data-stu-id="82822-198">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="82822-199">Consulte [Ver uma lista de números de Audioconferência](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="82822-199">[See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="82822-200">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="82822-200">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="82822-p112">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="82822-p112">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="82822-204">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="82822-204">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="82822-205">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="82822-205">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="82822-206">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="82822-206">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="82822-207">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="82822-207">Related topics</span></span>

[<span data-ttu-id="82822-208">Gerenciar as configurações de audioconferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="82822-208">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


