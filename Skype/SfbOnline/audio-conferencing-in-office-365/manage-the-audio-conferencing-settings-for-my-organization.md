---
title: "Gerenciar as configurações de áudio da conferência para minha organização"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: b890358cebfe6b5d701758c4b6086d6e1f388ca1
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="18eb3-103">Gerenciar as configurações de áudio da conferência para minha organização</span><span class="sxs-lookup"><span data-stu-id="18eb3-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="18eb3-104">Talvez seja mais fácil para ver todas as configurações de serviços de audioconferência para Skype para Teams da Microsoft em um único local e de negócios.</span><span class="sxs-lookup"><span data-stu-id="18eb3-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="18eb3-105">Atribuir uma licença de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="18eb3-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="18eb3-106">Não é possível atribuir licenças usando o **Skype para centro de administração de negócios**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-106">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="18eb3-107">Você deve usar o Centro de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="18eb3-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="18eb3-108">Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-108">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="18eb3-109">**Para atribuir uma licença para um usuário**</span><span class="sxs-lookup"><span data-stu-id="18eb3-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="18eb3-110">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="18eb3-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="18eb3-111">No painel de navegação à esquerda do **Centro de administração do Office 365**, vá para **usuários** > **usuários ativos**e selecione o usuário ou usuários da lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="18eb3-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="18eb3-112">[!DICA] Para atribuir licenças a mais de 20 usuários ao mesmo tempo, você pode usar o menu suspenso **Selecionar uma exibição** e escolher uma das opções ou criar sua própria exibição.</span><span class="sxs-lookup"><span data-stu-id="18eb3-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="18eb3-113">Em seguida, clique em **Editar**, **próximo** duas vezes e em seguida, selecione a licença e clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="18eb3-114">Você também pode atribuir licenças a vários usuários usando o Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="18eb3-114">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="18eb3-115">Para obter instruções e scripts do PowerShell de amostra, consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-115">For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="18eb3-116">No painel Ação em **Licenças de**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="18eb3-117">Na página **Licenças do produto** , ligue a **Conferência de áudio** e, em seguida, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-117">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="18eb3-118">Para obter mais informações sobre licenciamento, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-118">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="18eb3-119">Após atribuir a licença, Microsoft talvez não sejam exibidos inicialmente na lista como um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="18eb3-119">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="18eb3-120">Caso isso aconteça, saia do Centro de administração do Office 365 ou pressione CTRL+F5 para atualizar a janela do navegador.</span><span class="sxs-lookup"><span data-stu-id="18eb3-120">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="18eb3-121">Atribuir uma ID de conferência a um usuário</span><span class="sxs-lookup"><span data-stu-id="18eb3-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="18eb3-122">Uma ID de conferência é atribuída automaticamente a um usuário quando eles estiverem configurados para conferência de áudio usando o Microsoft como um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="18eb3-122">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="18eb3-123">A ID de conferência atribuída pode ser estáticos ou dinâmicos e é enviada no convite da reunião, quando a reunião foi agendada.</span><span class="sxs-lookup"><span data-stu-id="18eb3-123">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> 
  
<span data-ttu-id="18eb3-124">IDs estáticas são usadas quando as pessoas na sua organização não desejam Lembre-se de um número aleatório; eles podem selecionar um certo número ou escolha que é fácil de lembrar.</span><span class="sxs-lookup"><span data-stu-id="18eb3-124">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or choose one that's easy to remember.</span></span> <span data-ttu-id="18eb3-125">Se IDs de conferência dinâmicas estiverem sendo usadas, cada reunião agendada por um usuário terá uma ID de conferência exclusiva atribuída.</span><span class="sxs-lookup"><span data-stu-id="18eb3-125">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="18eb3-126">Se você desejar atribuir dinâmico em vez de IDs de conferência estático, consulte [IDs de conferência de áudio usando dinâmicos em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-126">If you want to assign dynamic rather than static conference IDs, see [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="18eb3-127">O Centro de administração do Skype for Business não pode ser usado para atribuir uma ID de conferência a um usuário, mas você pode usar o Windows PowerShell para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="18eb3-127">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="18eb3-128">Para definir a ID de conferência para um usuário, execute:</span><span class="sxs-lookup"><span data-stu-id="18eb3-128">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="18eb3-129">Uma ID de conferência deve conter 7 dígitos, e você não pode alterá-lo no Skype para centro de administração de negócios ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18eb3-129">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="18eb3-130">Consulte [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) para saber mais sobre o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="18eb3-130">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="18eb3-131">[!IMPORTANTE]  Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores.</span><span class="sxs-lookup"><span data-stu-id="18eb3-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="18eb3-132">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites.</span><span class="sxs-lookup"><span data-stu-id="18eb3-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="18eb3-133">Os usuários podem usar o Skype para ferramenta de migração de reunião de negócios para atualizar suas reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="18eb3-133">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="18eb3-134">Para ver como baixar, instalar e executar o Skype para ferramenta de atualização de reunião de negócios, consulte: [Ferramenta de atualização de reunião para Skype para negócios e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para negócios Online, a ferramenta de migração de reunião (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype para Business Online Meeting Ferramenta de migração (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="18eb3-134">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="18eb3-135">Veja [Consulte, alterar e redefina um ID de conferência atribuído a um usuário](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-135">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a><span data-ttu-id="18eb3-136">Alterar o provedor de serviços de audioconferência da Microsoft a um provedor de terceiros</span><span class="sxs-lookup"><span data-stu-id="18eb3-136">Change the audio conferencing provider from Microsoft to a third-party provider</span></span>

1. <span data-ttu-id="18eb3-137">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="18eb3-137">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="18eb3-138">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-138">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="18eb3-139">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**e então e selecione o usuário que você deseja alterar o provedor de serviços de audioconferência para.</span><span class="sxs-lookup"><span data-stu-id="18eb3-139">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then and select the user you want to change the audio conferencing provider for.</span></span>
    
4. <span data-ttu-id="18eb3-140">No Painel de Ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-140">In the Action pane, click **Edit**.</span></span> 
    
5. <span data-ttu-id="18eb3-141">Na página **Propriedades** , em **nome do provedor**, escolha o provedor de serviços de audioconferência para o usuário.</span><span class="sxs-lookup"><span data-stu-id="18eb3-141">On the **Properties** page, under **Provider name**, choose the audio conferencing provider for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="18eb3-142">Você só pode selecionar Microsoft como o provedor de serviços de audioconferência ou **Nenhum** se você tiver selecionado vários usuários.</span><span class="sxs-lookup"><span data-stu-id="18eb3-142">You can only select Microsoft as the audio conferencing provider or **None** if you have selected multiple users.</span></span>
  
6. <span data-ttu-id="18eb3-143">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-143">Click **Save**.</span></span> 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="18eb3-144">Habilitar ou desabilitar os e-mails enviados para usuários de serviços de audioconferência</span><span class="sxs-lookup"><span data-stu-id="18eb3-144">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="18eb3-145">Você pode usar o Skype para centro de administração de negócios ou o Windows PowerShell para habilitar ou desabilitar o email enviado aos usuários.</span><span class="sxs-lookup"><span data-stu-id="18eb3-145">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="18eb3-146">**Usando o Skype para o Centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="18eb3-146">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="18eb3-147">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="18eb3-147">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="18eb3-148">Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-148">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="18eb3-149">Na página **configurações de ponte da Microsoft** , marque ou desmarque a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-149">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="18eb3-150">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-150">Click **Save**.</span></span>
    
    <span data-ttu-id="18eb3-151">Você também pode enviar emails para o usuário com as configurações de serviços de audioconferência indo para propriedades de conferência de áudio do usuário e clicar em **Enviar informações de conferência via email**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-151">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="18eb3-152">Número de telefone do serviços de audioconferência a conferência ID e o padrão é incluído no convite da reunião, mas não o PIN.</span><span class="sxs-lookup"><span data-stu-id="18eb3-152">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="18eb3-153">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-153">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="18eb3-154">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="18eb3-154">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="18eb3-155">Também é possível usar o Windows PowerShell e executar:</span><span class="sxs-lookup"><span data-stu-id="18eb3-155">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="18eb3-156">Você pode usar o [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações da sua organização, incluindo email.</span><span class="sxs-lookup"><span data-stu-id="18eb3-156">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="18eb3-157">Alterar as informações de contato do remetente nas mensagens de email enviadas aos usuários</span><span class="sxs-lookup"><span data-stu-id="18eb3-157">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="18eb3-158">Você pode fazer alterações para email que será enviado automaticamente aos seus usuários, incluindo o endereço de email real e o nome para exibição de informações de contato do remetente.</span><span class="sxs-lookup"><span data-stu-id="18eb3-158">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="18eb3-159">Por padrão, o remetente dos emails é o Office 365, mas você pode alterar o endereço de email e nome para exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .</span><span class="sxs-lookup"><span data-stu-id="18eb3-159">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="18eb3-160">Para fazer alterações para o endereço de email que está enviando email aos usuários, você deve:</span><span class="sxs-lookup"><span data-stu-id="18eb3-160">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="18eb3-161">Insira o endereço de email no parâmetro _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="18eb3-161">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="18eb3-162">Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="18eb3-162">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="18eb3-163">Defina o parâmetro _SendEmailOverride_ como _True_.</span><span class="sxs-lookup"><span data-stu-id="18eb3-163">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="18eb3-164">Você pode fazer alterações nos emails enviados para usuários, como o endereço de email que envia as mensagens ou o nome de exibição do email executando:</span><span class="sxs-lookup"><span data-stu-id="18eb3-164">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="18eb3-165">Se você quiser alterar as informações do endereço de email, deve verificar se as políticas de recebimento de email de sua organização permitem emails do endereço de email personalizado.</span><span class="sxs-lookup"><span data-stu-id="18eb3-165">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="18eb3-166">Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações da sua organização, incluindo email.</span><span class="sxs-lookup"><span data-stu-id="18eb3-166">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="18eb3-167">Consulte [Emails que são enviados automaticamente para os usuários quando alteram suas configurações de conferência de áudio](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-167">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="18eb3-168">Redefinir a ID de conferência de reunião</span><span class="sxs-lookup"><span data-stu-id="18eb3-168">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="18eb3-169">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="18eb3-169">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="18eb3-170">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-170">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="18eb3-171">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**e, no painel de ação em **ID da conferência**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-171">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="18eb3-172">No **Redefinir ID de conferência?** janela, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-172">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="18eb3-173">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="18eb3-173">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="18eb3-174">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="18eb3-174">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="18eb3-175">[!IMPORTANTE] Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores.</span><span class="sxs-lookup"><span data-stu-id="18eb3-175">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="18eb3-176">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites.</span><span class="sxs-lookup"><span data-stu-id="18eb3-176">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="18eb3-177">Os usuários podem usar o Skype para ferramenta de migração de reunião de negócios para atualizar suas reuniões existentes.</span><span class="sxs-lookup"><span data-stu-id="18eb3-177">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="18eb3-178">Para ver como baixar, instalar e executar o Skype para ferramenta de atualização de reunião de negócios, consulte: [ferramenta de atualização de reunião para Skype para negócios e Lync] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para negócios Online, ferramenta de migração de reunião (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype para Business Online Ferramenta de migração (32 bits) da reunião](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="18eb3-178">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync]((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="18eb3-179">Veja [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-179">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="18eb3-180">Redefinir o PIN de um organizador da conferência</span><span class="sxs-lookup"><span data-stu-id="18eb3-180">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="18eb3-181">IDs estáticas são usadas quando as pessoas na sua organização não desejam Lembre-se de um número aleatório; eles podem selecionar um certo número ou use um que seja fácil de lembrar.</span><span class="sxs-lookup"><span data-stu-id="18eb3-181">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="18eb3-182">Se IDs de conferência dinâmicas estiverem sendo usadas, cada reunião agendada por um usuário terá uma ID de conferência exclusiva atribuída.</span><span class="sxs-lookup"><span data-stu-id="18eb3-182">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="18eb3-183">Se você deseja atribuir dinâmico em vez de conferência estática IDs, [IDs de conferência de áudio usando dinâmicos em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-183">If you want to assign dynamic rather than static conference IDs, [Using Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="18eb3-184">Embora uma ID de conferência estática será criada automaticamente e atribuída a um usuário, pode haver ocasiões quando um usuário não deseja usar este e deseja defini-la a um certo número ou os usuários não conseguir se lembrar ou tem perdido sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="18eb3-184">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="18eb3-185">Você pode usar o Skype para centro de administração de negócios e do Windows PowerShell para exibir, alterar e redefinir a sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="18eb3-185">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
1. <span data-ttu-id="18eb3-186">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="18eb3-186">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="18eb3-187">Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-187">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="18eb3-188">Clique em **usuários**e, em seguida, selecione o usuário que você deseja redefinir o PIN para.</span><span class="sxs-lookup"><span data-stu-id="18eb3-188">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="18eb3-189">No painel de ações, em **PIN**, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-189">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="18eb3-190">Os usuários receberão um email com o PIN quando elas são habilitadas para conferência de áudio ou quando o PIN ser redefinido.</span><span class="sxs-lookup"><span data-stu-id="18eb3-190">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="18eb3-191">Mas, se você desabilitou automaticamente enviando e-mails, um email de redefinição PIN não será enviado e você terá que enviar manualmente o PIN para o usuário.</span><span class="sxs-lookup"><span data-stu-id="18eb3-191">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="18eb3-192">O PIN será exibido somente uma vez depois de ser redefinido.</span><span class="sxs-lookup"><span data-stu-id="18eb3-192">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="18eb3-193">Depois que ele é exibido depois de ser redefinido, o PIN não será mostrado mais sobre as propriedades de usuário; em vez disso, \* \* \* serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="18eb3-193">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="18eb3-194">Veja [Redefinir o PIN de conferência de áudio para um usuário](reset-the-audio-conferencing-pin-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-194">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="18eb3-195">Enviar um email com informações de conferência de áudio a um usuário</span><span class="sxs-lookup"><span data-stu-id="18eb3-195">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="18eb3-196">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="18eb3-196">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="18eb3-197">Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-197">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="18eb3-198">Clique em **usuários**e, em seguida, selecione o usuário que você deseja redefinir o PIN para.</span><span class="sxs-lookup"><span data-stu-id="18eb3-198">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="18eb3-199">No painel Ação, clique em **Enviar informações da conferência por email**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-199">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="18eb3-200">Quando você fizer isso, os serviços de audioconferência PIN não será enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="18eb3-200">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="18eb3-201">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-201">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="18eb3-202">Definindo o número de telefone de conferência de áudio padrão para organizadores de reunião</span><span class="sxs-lookup"><span data-stu-id="18eb3-202">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="18eb3-203">**Para definir o número de telefone de conferência de áudio padrão para organizadores de reunião, quando você estiver habilitando um usuário para conferência de áudio**</span><span class="sxs-lookup"><span data-stu-id="18eb3-203">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="18eb3-204">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="18eb3-204">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="18eb3-205">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-205">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="18eb3-206">No painel de navegação esquerdo, vá para **conferência de áudio** > **usuários**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-206">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="18eb3-207">Selecione o usuário que você deseja habilitar para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="18eb3-207">Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="18eb3-208">No painel de ações, nas propriedades do usuário, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-208">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="18eb3-209">Na página **Propriedades** , em **nome do provedor**, use a lista suspensa para selecionar o provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="18eb3-209">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="18eb3-210">Se você selecionar Microsoft como um provedor de serviços de audioconferência, você pode escolher o número de telefone de conferência de áudio padrão da lista.</span><span class="sxs-lookup"><span data-stu-id="18eb3-210">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="18eb3-211">Se você selecionar um ACP de terceiros como o provedor de serviços de audioconferência, você precisará digitar manualmente as tarifas e, se necessário, o número de telefone gratuitos.</span><span class="sxs-lookup"><span data-stu-id="18eb3-211">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span> <span data-ttu-id="18eb3-212">Esses números de telefone serão o número de telefone padrão.</span><span class="sxs-lookup"><span data-stu-id="18eb3-212">These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="18eb3-213">O número de telefone de conferência de áudio padrão de um usuário é o número que é exibido no convite da reunião, quando eles agendam uma reunião.</span><span class="sxs-lookup"><span data-stu-id="18eb3-213">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="18eb3-214">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-214">Click **Save**.</span></span> 
    
<span data-ttu-id="18eb3-215">Consulte [Definir convidam números incluídos no telefone](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-215">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="18eb3-216">**Para definir o número de telefone de conferência de áudio padrão para organizadores de reunião depois de habilitar um usuário para conferência de áudio**</span><span class="sxs-lookup"><span data-stu-id="18eb3-216">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="18eb3-217">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="18eb3-217">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="18eb3-218">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-218">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="18eb3-219">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**, selecione o usuário desejado e na página ação, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-219">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="18eb3-220">Na página **Propriedades** , em **nome do provedor**, use a lista suspensa para selecionar o provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="18eb3-220">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="18eb3-221">Se o usuário usa o Microsoft como um provedor de serviços de audioconferência, você pode escolher o número de telefone de conferência de áudio padrão da lista.</span><span class="sxs-lookup"><span data-stu-id="18eb3-221">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="18eb3-222">Se o usuário utilizar um ACP de terceiros como o provedor de serviços de audioconferência, você precisará digitar manualmente as tarifas e, se necessário, o número de telefone gratuitos.</span><span class="sxs-lookup"><span data-stu-id="18eb3-222">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="18eb3-223">O número de telefone de conferência de áudio padrão de um usuário é o número que é exibido no convite da reunião, quando eles agendam uma reunião.</span><span class="sxs-lookup"><span data-stu-id="18eb3-223">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="18eb3-224">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-224">Click **Save**.</span></span> 
    
<span data-ttu-id="18eb3-225">Consulte [Definir convidam números incluídos no telefone](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-225">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="setting-audio-conferencing-bridge-settings"></a><span data-ttu-id="18eb3-226">Definindo as configurações de ponte de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="18eb3-226">Setting audio conferencing bridge settings</span></span>

 <span data-ttu-id="18eb3-227">**Definir a experiência da reunião, quando os chamadores ingressem em uma reunião**</span><span class="sxs-lookup"><span data-stu-id="18eb3-227">**Set the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="18eb3-228">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="18eb3-228">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="18eb3-229">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-229">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="18eb3-230">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="18eb3-231">Em que **a experiência de participação da reunião**, selecione as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="18eb3-231">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="18eb3-232">**Habilitar a ativação de notificações de entrada e saída de reunião** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="18eb3-232">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="18eb3-233">Se você desmarcar essa caixa de seleção, os usuários que já tenham ingressado na reunião por padrão não serão notificados quando alguém entra ou sai da reunião.</span><span class="sxs-lookup"><span data-stu-id="18eb3-233">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="18eb3-234">Isso pode ser definido em uma base de reunião por reunião quando um usuário ingressa em uma reunião usando um Skype para o aplicativo de negócios ou Teams da Microsoft e eles modificam a configuração de **anunciar quando as pessoas entrar ou sair** do menu Skype reunião ou Microsoft Teams **Opções** do reunião.</span><span class="sxs-lookup"><span data-stu-id="18eb3-234">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="18eb3-235">**Peça que os chamadores registrem seus nomes antes de ingressar na reunião** Esta opção é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="18eb3-235">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="18eb3-236">Se você desmarcar essa caixa de seleção, os chamadores não solicitados registrar seus nomes antes de ingressar em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="18eb3-236">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="18eb3-237">Depois de fazer suas alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-237">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="18eb3-238">Consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-238">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="18eb3-239">**Definir o tamanho PIN para reuniões**</span><span class="sxs-lookup"><span data-stu-id="18eb3-239">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="18eb3-240">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="18eb3-240">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="18eb3-241">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-241">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="18eb3-242">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-242">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="18eb3-243">Em **segurança**, insira o número de dígitos que você deseja para o PIN na lista **tamanho PIN** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-243">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="18eb3-244">O PIN deve ter entre 4 e 12 dígitos.</span><span class="sxs-lookup"><span data-stu-id="18eb3-244">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="18eb3-245">O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="18eb3-245">The default is 5.</span></span>
    
<span data-ttu-id="18eb3-246">Consulte [alterar as configurações de uma ponte de conferência de áudio](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-246">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="18eb3-247">**Habilitar ou desabilitar o email que está sendo enviado a usuários de áudio**</span><span class="sxs-lookup"><span data-stu-id="18eb3-247">**Enable or disable email from being sent to audio users**</span></span>
  
1. <span data-ttu-id="18eb3-248">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="18eb3-248">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="18eb3-249">Vá para o **Centro de administração do Office 365** > **Skype for Business** e no painel de navegação esquerdo, clique em **conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-249">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="18eb3-250">Na página **configurações de ponte da Microsoft** , marque ou desmarque a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-250">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="18eb3-251">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-251">Click **Save**.</span></span>
    
    <span data-ttu-id="18eb3-252">Você também pode enviar email para o usuário com as configurações de conferência de áudio, indo para propriedades de conferência de áudio do usuário e clicar em **Enviar informações de conferência via email**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-252">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="18eb3-253">Se você fizer isso, será enviado um email somente com o número de telefone e a ID da conferência, mas o PIN não será incluído.</span><span class="sxs-lookup"><span data-stu-id="18eb3-253">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="18eb3-254">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-254">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="18eb3-255">Consulte e definir os idiomas principais e secundários em uma ponte de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="18eb3-255">See and set the primary and secondary languages on an audio conferencing bridge</span></span>

1. <span data-ttu-id="18eb3-256">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="18eb3-256">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="18eb3-257">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-257">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="18eb3-258">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**e, em seguida, clique em **Microsoft ponte**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-258">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="18eb3-259">Selecione um número de telefone na lista, clique em **definir idiomas** no painel de ações e na página **conjunto** de idiomas, clique em uso na lista de **idioma principal** para exibir a lista completa dos idiomas com suporte.</span><span class="sxs-lookup"><span data-stu-id="18eb3-259">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="18eb3-260">Você também pode definir os idiomas principais e secundários que têm suporte quando você seleciona Microsoft como o provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="18eb3-260">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="18eb3-261">A ordem em que você selecione nas listas é a mesma ordem em que idiomas serão apresentados aos chamadores.</span><span class="sxs-lookup"><span data-stu-id="18eb3-261">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="18eb3-262">Veja [Definir idiomas do atendedor automático para conferência de áudio](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-262">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="18eb3-263">Consulte serviços de audioconferência discada números</span><span class="sxs-lookup"><span data-stu-id="18eb3-263">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="18eb3-264">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="18eb3-264">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="18eb3-265">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-265">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="18eb3-266">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-266">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="18eb3-267">Aqui, você pode:</span><span class="sxs-lookup"><span data-stu-id="18eb3-267">Here you can:</span></span>
    
  - <span data-ttu-id="18eb3-268">Exiba os números de telefone definidos pelo Office 365 a serem usados para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="18eb3-268">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="18eb3-269">Exiba o local e os idiomas principais e secundários, que serão usados pelo atendedor automático conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="18eb3-269">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="18eb3-270">Selecione o número de telefone padrão que será fornecido aos usuários quando eles estão habilitados para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="18eb3-270">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="18eb3-271">No entanto, se o número de telefone de ponte de conferência de áudio padrão for alterado, não alterará o número de telefone padrão para usuários existentes.</span><span class="sxs-lookup"><span data-stu-id="18eb3-271">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="18eb3-272">Você pode ir para a **conferência de áudio** > **usuários** e selecione Propriedades do usuário para alterar o padrão de número de um usuário escolhendo um novo número da lista de números que estão disponíveis em sua organização.</span><span class="sxs-lookup"><span data-stu-id="18eb3-272">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="18eb3-273">Consulte [ver uma lista de números de conferência de áudio](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-273">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="18eb3-274">Visualizar uma lista de usuários habilitados</span><span class="sxs-lookup"><span data-stu-id="18eb3-274">See a list of users that are enabled</span></span>

1. <span data-ttu-id="18eb3-275">Entre no Office 365 com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="18eb3-275">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="18eb3-276">Vá para o **Centro de administração do Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-276">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="18eb3-277">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio**> e, em seguida, **os usuários**.</span><span class="sxs-lookup"><span data-stu-id="18eb3-277">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="18eb3-278">Veja [Ver uma lista de usuários habilitados para conferência de áudio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="18eb3-278">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="18eb3-279">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="18eb3-279">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="18eb3-280">Existem diversas configurações que podem ser gerenciadas no nível da organização usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18eb3-280">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="18eb3-281">Isso facilita aplicar as configurações para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="18eb3-281">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="18eb3-282">Para obter mais ajuda sobre cada cmdlet, consulte [Cmdlets do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=627324).</span><span class="sxs-lookup"><span data-stu-id="18eb3-282">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="18eb3-283">Aqui estão as configurações de nível de organização:</span><span class="sxs-lookup"><span data-stu-id="18eb3-283">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="18eb3-284">**Definir notificações de entrada/saída** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="18eb3-284">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="18eb3-285">**A definição de registro de nome** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="18eb3-285">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="18eb3-286">**A definição do comprimento do PIN** O padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="18eb3-286">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="18eb3-287">**Configuração somente discada reuniões de um telefone** O padrão _$false_.</span><span class="sxs-lookup"><span data-stu-id="18eb3-287">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="18eb3-288">**Definindo-se enviar email aos usuários** O padrão é _$true_.</span><span class="sxs-lookup"><span data-stu-id="18eb3-288">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="18eb3-289">**Definindo-se enviar email a partir de uma conta diferente** O padrão é _$false_.</span><span class="sxs-lookup"><span data-stu-id="18eb3-289">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="18eb3-290">**Definindo o endereço From em que é enviado aos usuários de email** O padrão é _$null_.</span><span class="sxs-lookup"><span data-stu-id="18eb3-290">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="18eb3-291">**Definir o nome de exibição para o email que será enviado aos usuários** O padrão é _$null_.</span><span class="sxs-lookup"><span data-stu-id="18eb3-291">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="18eb3-292">Quer saber mais sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="18eb3-292">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="18eb3-p124">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="18eb3-p124">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="18eb3-296">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="18eb3-296">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="18eb3-297">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="18eb3-297">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="18eb3-298">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações de muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="18eb3-298">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="18eb3-299">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="18eb3-299">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="18eb3-300">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="18eb3-300">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="18eb3-301">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="18eb3-301">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="18eb3-302">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="18eb3-302">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="18eb3-p126">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="18eb3-p126">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="18eb3-305">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="18eb3-305">Related topics</span></span>

[<span data-ttu-id="18eb3-306">Gerenciar as configurações de audioconferência de um usuário</span><span class="sxs-lookup"><span data-stu-id="18eb3-306">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)

[<span data-ttu-id="18eb3-307">Configurar conferência de áudio para o Skype for Business e Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="18eb3-307">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
