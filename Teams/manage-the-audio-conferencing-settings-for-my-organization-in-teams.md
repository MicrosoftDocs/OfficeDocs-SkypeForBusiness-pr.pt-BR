---
title: Gerenciar as configurações de Audioconferência de sua organização no Microsoft Teams
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
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Consulte as etapas para atribuir uma licença de conferência discada e um ID de conferência a um usuário no Microsoft Teams e várias outras configurações de conferência discada. '
ms.openlocfilehash: 593987c6de3f6245afcdd7221fa7130a511d9f77
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291007"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="0475f-103">Gerenciar as configurações de Audioconferência de sua organização no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0475f-103">Manage the Audio Conferencing settings for your organization in Microsoft Teams</span></span>

<span data-ttu-id="0475f-104">Pode ser mais fácil para você visualizar todas as configurações de audioconferência em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="0475f-104">It might be easier for you to see all of the audio conferencing settings for Microsoft Teams in one place.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="0475f-105">Atribui licença de audioconferência</span><span class="sxs-lookup"><span data-stu-id="0475f-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="0475f-106">Não é possível atribuir licenças usando o Teams.</span><span class="sxs-lookup"><span data-stu-id="0475f-106">You can't assign licenses using Teams.</span></span> <span data-ttu-id="0475f-107">Você deve usar o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0475f-107">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="0475f-108">Consulte [Atribuir licenças do Skype for Business e do Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="0475f-108">See [Assign Skype for Business and Microsoft Teams licenses](assign-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="0475f-109">**Atribuir uma licença a um usuário**</span><span class="sxs-lookup"><span data-stu-id="0475f-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="0475f-110">Entre no Microsoft 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="0475f-110">Sign in to Microsoft 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0475f-111">Na navegação à esquerda do **centro de administração do Microsoft 365**, vá para usuários**ativos**do **usuários** > e selecione o usuário ou os usuários na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0475f-111">In the left navigation of the **Microsoft 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0475f-112">[!DICA] Para atribuir licenças a mais de 20 usuários ao mesmo tempo, você pode usar o menu suspenso **Selecionar uma exibição** e escolher uma das opções ou criar sua própria exibição.</span><span class="sxs-lookup"><span data-stu-id="0475f-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="0475f-113">Em seguida, clique em **Editar**, **Próximo** duas vezes, selecione a licença e clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="0475f-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span>  
  
3. <span data-ttu-id="0475f-114">No painel Ação em **Licenças de produto**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0475f-114">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="0475f-115">Na página **Licenças de produto**, ative **Audioconferência** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0475f-115">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="0475f-116">Para saber mais sobre licenciamento, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="0475f-116">For more on licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="0475f-117">Depois de atribuir a licença, a Microsoft pode não aparecer inicialmente na lista como provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="0475f-117">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="0475f-118">Caso isso aconteça, saia do centro de administração do Office 365 ou pressione CTRL+F5 para atualizar a janela do navegador.</span><span class="sxs-lookup"><span data-stu-id="0475f-118">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="0475f-119">Habilitar ou desabilitar o envio de e-mails para usuários de audioconferência</span><span class="sxs-lookup"><span data-stu-id="0475f-119">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="0475f-120">![Teams-logo-30x30. png](media/teams-logo-30x30.png) **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="0475f-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0475f-121">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="0475f-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="0475f-122">No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="0475f-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="0475f-123">No painel **Configurações de ponte**, habilite ou desabilite **Enviar e-mails aos usuários automaticamente de suas configurações de discagem forem alteradas**.</span><span class="sxs-lookup"><span data-stu-id="0475f-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="0475f-124">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0475f-124">Click **Save**.</span></span>

    
<span data-ttu-id="0475f-125">**Usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0475f-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="0475f-126">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0475f-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="0475f-127">Redefinir a ID de conferência de reunião</span><span class="sxs-lookup"><span data-stu-id="0475f-127">Reset the meeting conference ID</span></span>

<span data-ttu-id="0475f-128">![Teams-logo-30x30. png](media/teams-logo-30x30.png) **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="0475f-128">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0475f-129">Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0475f-129">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="0475f-130">Em **conferência de áudio**, clique em **Redefinir ID de conferência**.</span><span class="sxs-lookup"><span data-stu-id="0475f-130">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

3. <span data-ttu-id="0475f-131">Na janela **Redefinir ID de conferência?** , clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="0475f-131">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="0475f-132">Um ID de conferência será criado automaticamente e um email será enviado ao usuário com o novo ID de conferência, se o envio de email para seus usuários estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="0475f-132">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="0475f-133">Está ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="0475f-133">It's enabled by default.</span></span>

<span data-ttu-id="0475f-134">Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0475f-134">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="0475f-135">Redefinir o PIN de um organizador da conferência</span><span class="sxs-lookup"><span data-stu-id="0475f-135">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="0475f-136">Cada reunião agendada por um usuário receberá uma ID de conferência exclusiva.</span><span class="sxs-lookup"><span data-stu-id="0475f-136">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="0475f-137">Embora uma ID de conferência seja criada automaticamente e atribuída a um usuário, pode haver ocasiões em que um usuário não queira usar essa e você deseja defini-la como um número específico ou que seus usuários não se lembram ou perderam a ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="0475f-137">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> 

<span data-ttu-id="0475f-138">![Teams-logo-30x30. png](media/teams-logo-30x30.png) **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="0475f-138">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0475f-139">Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0475f-139">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="0475f-140">Em **conferência de áudio**, clique em **Redefinir PIN**e em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="0475f-140">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="0475f-141">Os usuários receberão um email com o PIN quando estiverem habilitados para videoconferência ou quando o PIN for redefinido.</span><span class="sxs-lookup"><span data-stu-id="0475f-141">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="0475f-142">Mas se você tiver desabilitado o envio de emails automaticamente, um email de redefinição de PIN não será enviado e você terá que enviar o PIN manualmente para o usuário.</span><span class="sxs-lookup"><span data-stu-id="0475f-142">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="0475f-143">O PIN será exibido somente uma vez depois de ser redefinido.</span><span class="sxs-lookup"><span data-stu-id="0475f-143">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="0475f-144">Depois que ele é exibido logo após a redefinição, o pino não é mais mostrado nas propriedades do usuário; em vez disso, \* \* \* será mostrado.</span><span class="sxs-lookup"><span data-stu-id="0475f-144">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="0475f-145">Consulte [redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0475f-145">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="0475f-146">Enviar um email com as informações de conferência de áudio para um usuário</span><span class="sxs-lookup"><span data-stu-id="0475f-146">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="0475f-147">![Teams-logo-30x30. png](media/teams-logo-30x30.png) **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="0475f-147">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0475f-148">Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0475f-148">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="0475f-149">Em **conferência de áudio**, clique em **enviar informações de conferência por email**.</span><span class="sxs-lookup"><span data-stu-id="0475f-149">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="0475f-150">Quando você faz isso, o pino de audioconferência não é enviado para o usuário.</span><span class="sxs-lookup"><span data-stu-id="0475f-150">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="0475f-151">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0475f-151">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
  
## <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="0475f-152">Definir os números de telefone incluídos em convites</span><span class="sxs-lookup"><span data-stu-id="0475f-152">Set the phone numbers included on invites</span></span>

<span data-ttu-id="0475f-153">![Teams-logo-30x30. png](media/teams-logo-30x30.png) **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="0475f-153">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0475f-154">Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0475f-154">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="0475f-155">Ao lado de **conferência de áudio**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0475f-155">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="0475f-156">No painel **conferência de áudio** , você pode definir o **número de chamada tarifada** e, se permitido, o **número de chamada gratuita**.</span><span class="sxs-lookup"><span data-stu-id="0475f-156">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="0475f-157">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0475f-157">Click **Save**.</span></span>
    
<span data-ttu-id="0475f-158">Consulte [definir os números de telefone incluídos nos convites](set-the-phone-numbers-included-on-invites-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0475f-158">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a><span data-ttu-id="0475f-159">Escolher configurações de ponte de áudio audioconferência</span><span class="sxs-lookup"><span data-stu-id="0475f-159">Choose audio conferencing bridge settings</span></span>

<span data-ttu-id="0475f-160">**Definir a experiência da reunião quando os chamadores entrarem em uma reunião**</span><span class="sxs-lookup"><span data-stu-id="0475f-160">**Set the meeting experience when callers join a meeting**</span></span>

<span data-ttu-id="0475f-161">![Teams-logo-30x30. png](media/teams-logo-30x30.png) **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="0475f-161">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0475f-162">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="0475f-162">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="0475f-163">Na parte superior da página **pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="0475f-163">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="0475f-164">No painel **Configurações da ponte**, ative ou desative **Notificações de entrada/saída de reuniões**.</span><span class="sxs-lookup"><span data-stu-id="0475f-164">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="0475f-165">Isso é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="0475f-165">This is enabled by default.</span></span> <span data-ttu-id="0475f-166">Se você desabilitar essa opção, por padrão, os usuários que já entraram na reunião não serão notificados quando alguém entrar ou sair da reunião.</span><span class="sxs-lookup"><span data-stu-id="0475f-166">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="0475f-167">Em **tipo de anúncio de entrada/saída**, escolha **toques** ou **nomes ou números de telefone**.</span><span class="sxs-lookup"><span data-stu-id="0475f-167">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="0475f-168">Se você escolher **nomes ou números de telefone**, também poderá optar por habilitar ou desabilitar **o recurso pedir que os chamadores registrem o nome antes de ingressar na reunião**.</span><span class="sxs-lookup"><span data-stu-id="0475f-168">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

5. <span data-ttu-id="0475f-169">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0475f-169">Click **Save**.</span></span>

    
<span data-ttu-id="0475f-170">Consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="0475f-170">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="0475f-171">**Definir o comprimento do PIN para reuniões**</span><span class="sxs-lookup"><span data-stu-id="0475f-171">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="0475f-172">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="0475f-172">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="0475f-173">Na parte superior da página **pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="0475f-173">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="0475f-174">No painel **configurações de ponte** , insira o número de dígitos que você deseja para o pino na lista **comprimento do pino** e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="0475f-174">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="0475f-175">O PIN deve ter entre 4 e 12 dígitos.</span><span class="sxs-lookup"><span data-stu-id="0475f-175">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="0475f-176">O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="0475f-176">The default is 5.</span></span>

    
<span data-ttu-id="0475f-177">Consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="0475f-177">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="0475f-178">**Habilitar ou desabilitar o envio de emails para usuários de áudio**</span><span class="sxs-lookup"><span data-stu-id="0475f-178">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="0475f-179">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="0475f-179">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="0475f-180">Na parte superior da página **pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="0475f-180">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="0475f-181">No painel **configurações de ponte** , habilite ou desabilite **enviar emails automaticamente aos usuários se suas configurações de audioconferência de áudio mudarem**.</span><span class="sxs-lookup"><span data-stu-id="0475f-181">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="0475f-182">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0475f-182">Click **Save**.</span></span> 
 
    <span data-ttu-id="0475f-183">Você também pode enviar emails para o usuário com as configurações de audioconferência, acessando as propriedades de videoconferência do usuário e clicando **em enviar informações de conferência por email**.</span><span class="sxs-lookup"><span data-stu-id="0475f-183">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="0475f-184">Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.</span><span class="sxs-lookup"><span data-stu-id="0475f-184">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="0475f-185">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0475f-185">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="0475f-186">Ver e definir os idiomas principais (padrão) e secundários (alternativos) em uma ponte de audioconferência</span><span class="sxs-lookup"><span data-stu-id="0475f-186">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

<span data-ttu-id="0475f-187">![Teams-logo-30x30. png](media/teams-logo-30x30.png) **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="0475f-187">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0475f-188">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="0475f-188">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="0475f-189">Selecione um número de telefone na lista e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0475f-189">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="0475f-190">Escolha os idiomas desejados em **idioma padrão** e **idiomas alternativos (opcional)**.</span><span class="sxs-lookup"><span data-stu-id="0475f-190">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

4. <span data-ttu-id="0475f-191">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0475f-191">Click **Save**.</span></span>


<span data-ttu-id="0475f-192">Veja [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0475f-192">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="0475f-193">Consulte números de discagem de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="0475f-193">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="0475f-194">![Teams-logo-30x30. png](media/teams-logo-30x30.png) **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="0475f-194">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0475f-195">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="0475f-195">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="0475f-196">Selecione um número de telefone na lista e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0475f-196">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="0475f-197">Aqui você pode:</span><span class="sxs-lookup"><span data-stu-id="0475f-197">Here you can:</span></span>
    
   - <span data-ttu-id="0475f-198">Veja os números de telefone definidos pelo Office 365 a serem usados para videoconferências.</span><span class="sxs-lookup"><span data-stu-id="0475f-198">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
   - <span data-ttu-id="0475f-199">Exiba o local e o idioma principal que serão usados pelo atendedor automático de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="0475f-199">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>

  
<span data-ttu-id="0475f-200">Veja [ver uma lista de números de audioconferência](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0475f-200">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>
  

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0475f-201">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0475f-201">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="0475f-p111">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="0475f-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0475f-205">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="0475f-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0475f-206">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0475f-206">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="0475f-207">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0475f-207">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
    
## <a name="related-topics"></a><span data-ttu-id="0475f-208">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="0475f-208">Related topics</span></span>

[<span data-ttu-id="0475f-209">Gerenciar as configurações de audioconferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="0475f-209">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


