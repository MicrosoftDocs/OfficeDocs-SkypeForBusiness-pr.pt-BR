---
title: Gerenciar as configurações de audioconferência para a minha organização no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Consulte as etapas para atribuir uma licença de conferência discada e um ID de conferência a um usuário no Microsoft Teams e várias outras configurações de conferência discada. '
ms.openlocfilehash: 40a6dd3e545e913a134ae7bac80b5ec3085dc96a
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015329"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a><span data-ttu-id="12156-103">Gerenciar as configurações de audioconferência para a minha organização no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12156-103">Manage the Audio Conferencing settings for my organization in Microsoft Teams</span></span>

<span data-ttu-id="12156-104">Pode ser mais fácil para você visualizar todas as configurações de audioconferência em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="12156-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="12156-105">Atribui licença de audioconferência</span><span class="sxs-lookup"><span data-stu-id="12156-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="12156-106">Não é possível atribuir licenças usando equipes.</span><span class="sxs-lookup"><span data-stu-id="12156-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="12156-107">Você deve usar o Centro de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="12156-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="12156-108">Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="12156-108">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span> 
  
 <span data-ttu-id="12156-109">**Atribuir uma licença a um usuário**</span><span class="sxs-lookup"><span data-stu-id="12156-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="12156-110">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="12156-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="12156-111">No painel de navegação esquerdo do **centro de administração do Office 365**, vá para **Usuários** > **Usuários ativos**, e selecione o usuário ou os usuários na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="12156-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="12156-112">[!DICA] Para atribuir licenças a mais de 20 usuários ao mesmo tempo, você pode usar o menu suspenso **Selecionar uma exibição** e escolher uma das opções ou criar sua própria exibição.</span><span class="sxs-lookup"><span data-stu-id="12156-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="12156-113">Em seguida, clique em **Editar**, **próximo** duas vezes e em seguida, selecione a licença e clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="12156-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="12156-114">No painel Ação em **Licenças de produto**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="12156-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="12156-115">Na página **Licenças de produtos**, ligue a **Audioconferência** e em seguida clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="12156-115">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="12156-116">Para obter mais informações sobre licenciamento, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="12156-116">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).</span></span>
    
> [!NOTE]
> <span data-ttu-id="12156-117">Após atribuir a licença, Microsoft talvez não sejam exibidos inicialmente na lista como um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="12156-117">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="12156-118">Caso isso aconteça, saia do Centro de administração do Office 365 ou pressione CTRL+F5 para atualizar a janela do navegador.</span><span class="sxs-lookup"><span data-stu-id="12156-118">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="12156-119">Habilitar ou desabilitar o envio de e-mails para usuários de audioconferência</span><span class="sxs-lookup"><span data-stu-id="12156-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="12156-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**</span><span class="sxs-lookup"><span data-stu-id="12156-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="12156-121">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="12156-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="12156-122">No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="12156-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="12156-123">No painel **Configurações de ponte**, habilite ou desabilite **Enviar e-mails aos usuários automaticamente de suas configurações de discagem forem alteradas**.</span><span class="sxs-lookup"><span data-stu-id="12156-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="12156-124">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="12156-124">Click **Save**.</span></span>

    
<span data-ttu-id="12156-125">**Usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="12156-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="12156-126">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="12156-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="12156-127">Alterar as informações de contato do remetente das mensagens de e-mail enviadas aos usuários</span><span class="sxs-lookup"><span data-stu-id="12156-127">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="12156-128">Você pode fazer alterações para email que será enviado automaticamente aos seus usuários, incluindo o endereço de email real e o nome para exibição de informações de contato do remetente.</span><span class="sxs-lookup"><span data-stu-id="12156-128">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="12156-129">Por padrão, o remetente dos emails é o Office 365, mas você pode alterar o endereço de email e usando o Windows PowerShell de nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="12156-129">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> <span data-ttu-id="12156-130">Consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="12156-130">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="12156-131">Redefinir o ID de conferência de reunião</span><span class="sxs-lookup"><span data-stu-id="12156-131">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="12156-132">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="12156-132">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="12156-133">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="12156-133">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="12156-134">Em **Audio conferência**, clique em **Redefinir ID de conferência**.</span><span class="sxs-lookup"><span data-stu-id="12156-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="12156-135">No **Redefinir ID de conferência?** janela, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="12156-135">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="12156-136">Um ID de conferência será criado automaticamente e um email será enviado ao usuário com o novo ID de conferência, se o envio de email para seus usuários estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="12156-136">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="12156-137">Está ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="12156-137">It's enabled by default.</span></span>

<span data-ttu-id="12156-138">Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="12156-138">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="12156-139">Redefinir o PIN de um organizador da conferência</span><span class="sxs-lookup"><span data-stu-id="12156-139">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="12156-140">Cada reunião que um usuário agenda será obtido atribuída uma ID de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="12156-140">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="12156-141">Embora uma ID de conferência será criada automaticamente e atribuída a um usuário, pode haver ocasiões quando um usuário não deseja usar este e deseja defini-la a um certo número ou os usuários não conseguir se lembrar ou tem perdido sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="12156-141">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

1. <span data-ttu-id="12156-142">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="12156-142">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="12156-143">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="12156-143">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="12156-144">Em **Audioconferência**, clique em **Redefinir PIN**, e então clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="12156-144">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
    
<span data-ttu-id="12156-145">Os usuários receberão um email com o PIN quando elas são habilitadas para conferência de áudio ou quando o PIN ser redefinido.</span><span class="sxs-lookup"><span data-stu-id="12156-145">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="12156-146">Mas, se você desabilitou automaticamente enviando e-mails, um email de redefinição PIN não será enviado e você terá que enviar manualmente o PIN para o usuário.</span><span class="sxs-lookup"><span data-stu-id="12156-146">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="12156-147">O PIN será exibido somente uma vez depois de ser redefinido.</span><span class="sxs-lookup"><span data-stu-id="12156-147">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="12156-148">Depois que ele é exibido depois de ser redefinido, o PIN não será mostrado mais sobre as propriedades de usuário; em vez disso, \* \* \* serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="12156-148">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="12156-149">Veja [Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="12156-149">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="12156-150">Enviar um e-mail com as informações da audioconferência para um usuário</span><span class="sxs-lookup"><span data-stu-id="12156-150">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="12156-151">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="12156-151">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="12156-152">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="12156-152">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="12156-153">Em **Audioconferência**, clique em **Enviar informações da conferência por e-mail**.</span><span class="sxs-lookup"><span data-stu-id="12156-153">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="12156-154">Ao fazer isso, o PIN da audioconferência não é enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="12156-154">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

  
<span data-ttu-id="12156-155">Consulte [Enviar um e-mail para um usuário com suas informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="12156-155">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="12156-156">Definir os números de telefone incluídos em convites</span><span class="sxs-lookup"><span data-stu-id="12156-156">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="12156-157">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="12156-157">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="12156-158">Próximo a **Audioconferência**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="12156-158">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="12156-159">No painel **Audioconferência**, é possível definir o **Número tarifado** e, se permitido, o **Número gratuito**.</span><span class="sxs-lookup"><span data-stu-id="12156-159">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="12156-160">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="12156-160">Click **Save**.</span></span>
    
<span data-ttu-id="12156-161">Consulte [Definir os números de telefone incluídos em convites](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="12156-161">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="12156-162">Escolher as configurações de ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="12156-162">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="12156-163">**Definir a experiência da reunião quando os chamadores entram**</span><span class="sxs-lookup"><span data-stu-id="12156-163">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="12156-164">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="12156-164">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="12156-165">No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="12156-165">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="12156-166">No painel **Configurações da ponte**, ative ou desative **Notificações de entrada/saída de reuniões**.</span><span class="sxs-lookup"><span data-stu-id="12156-166">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="12156-167">Isso é ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="12156-167">This is enabled by default.</span></span> <span data-ttu-id="12156-168">Se você desabilitar essa opção, os usuários que já tenham ingressado na reunião por padrão não serão notificados quando alguém entra ou sai da reunião.</span><span class="sxs-lookup"><span data-stu-id="12156-168">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="12156-169">Em **Tipo de anúncio de entrada/saída**, escolha **Tons** ou **Nomes ou números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="12156-169">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="12156-170">Se escolher **Nomes ou números de telefone**, também será possível optar por ativar ou desativar **Solicitar que os chamadores gravem seu nome antes de entrar na reunião**.</span><span class="sxs-lookup"><span data-stu-id="12156-170">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="12156-171">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="12156-171">Click **Save**.</span></span>

    
<span data-ttu-id="12156-172">Consulte [Alterar as configurações de uma ponte de audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="12156-172">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="12156-173">**Definir o tamanho do PIN para reuniões**</span><span class="sxs-lookup"><span data-stu-id="12156-173">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="12156-174">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="12156-174">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="12156-175">No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="12156-175">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="12156-176">No painel **Configurações da ponte**, insira o número de dígitos que deseja para o PIN na lista **Tamanho do PIN** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="12156-176">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="12156-177">O PIN deve ter entre 4 e 12 dígitos.</span><span class="sxs-lookup"><span data-stu-id="12156-177">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="12156-178">O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="12156-178">The default is 5.</span></span>

    
<span data-ttu-id="12156-179">Consulte [Alterar as configurações de uma ponte de audioconferência](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="12156-179">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="12156-180">**Habilitar ou desabilitar o envio de e-mails para usuários de áudio**</span><span class="sxs-lookup"><span data-stu-id="12156-180">**Enable or disable email from being sent to audio users**</span></span>


1. <span data-ttu-id="12156-181">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="12156-181">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="12156-182">No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="12156-182">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="12156-183">No painel **Configurações da ponte**, ative ou desative **Enviar e-mails automaticamente aos usuários se suas configurações de audioconferência forem alteradas**.</span><span class="sxs-lookup"><span data-stu-id="12156-183">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="12156-184">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="12156-184">Click **Save**.</span></span> 
 
    <span data-ttu-id="12156-185">Você também pode enviar e-mails para o usuário com as configurações da audioconferência acessando as propriedades de audioconferência do usuário clicando em **Enviar informações da conferência por e-mail**.</span><span class="sxs-lookup"><span data-stu-id="12156-185">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="12156-186">Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.</span><span class="sxs-lookup"><span data-stu-id="12156-186">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="12156-187">Consulte [Enviar um e-mail para um usuário com suas informações de Audioconferência](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="12156-187">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="12156-188">Visualizar e definir os idiomas primário (padrão) e secundários (alternativos) para uma ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="12156-188">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

1. <span data-ttu-id="12156-189">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="12156-189">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="12156-190">Selecione um número de telefone na lista e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="12156-190">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="12156-191">Escolha os idiomas desejados em **Idioma padrão** e **Idiomas alternativos (opcional)**.</span><span class="sxs-lookup"><span data-stu-id="12156-191">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="12156-192">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="12156-192">Click **Save**.</span></span>


<span data-ttu-id="12156-193">Veja [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="12156-193">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="12156-194">Consulte serviços de audioconferência discada números</span><span class="sxs-lookup"><span data-stu-id="12156-194">See audio conferencing dial-in numbers</span></span>


1. <span data-ttu-id="12156-195">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="12156-195">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="12156-196">Selecione um número de telefone na lista e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="12156-196">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="12156-197">Aqui, você pode:</span><span class="sxs-lookup"><span data-stu-id="12156-197">Here you can:</span></span>
    
  - <span data-ttu-id="12156-198">Exiba os números de telefone definidos pelo Office 365 a serem usados para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="12156-198">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="12156-199">Exiba o local e o idioma principal, que será usado pelo atendedor automático conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="12156-199">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="12156-200">Consulte [ver uma lista de números de conferência de áudio](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="12156-200">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="12156-201">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="12156-201">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="12156-p112">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="12156-p112">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="12156-205">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="12156-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="12156-206">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12156-206">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="12156-207">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="12156-207">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="12156-208">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="12156-208">Related topics</span></span>

[<span data-ttu-id="12156-209">Gerenciar as configurações de audioconferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="12156-209">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


