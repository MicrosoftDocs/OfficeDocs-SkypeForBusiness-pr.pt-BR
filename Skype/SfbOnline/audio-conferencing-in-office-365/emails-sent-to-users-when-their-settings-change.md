---
title: Emails enviados para usuários quando as configurações forem alteradas no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: 'Saiba quais informações são enviadas automaticamente para os usuários por e-mail quando as configurações de conferência discada forem alteradas no Skype for Business online. '
ms.openlocfilehash: 8a0ecc27e3184b8258db7e094beb9f3c4b64796d
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962719"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a><span data-ttu-id="630ea-103">Emails enviados para usuários quando as configurações forem alteradas no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="630ea-103">Emails sent to users when their settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="630ea-104">Se você estiver procurando por informações automáticas de email no Microsoft Teams, consulte [emails enviados para os usuários quando as configurações forem alteradas no Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="630ea-104">If you're looking for automatic email information in Microsoft Teams, see [Emails sent to users when their settings change in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="630ea-105">Os emails serão enviados automaticamente para os usuários que estão [habilitados para conferência de áudio](set-up-audio-conferencing.md) usando a Microsoft como provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="630ea-105">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing.md) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="630ea-106">Por padrão, há quatro tipos de email que serão enviados aos usuários que estão habilitados para videoconferências.</span><span class="sxs-lookup"><span data-stu-id="630ea-106">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="630ea-107">No entanto, se quiser limitar o número de emails enviados para os usuários, você pode desativá-lo.</span><span class="sxs-lookup"><span data-stu-id="630ea-107">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="630ea-108">A conferência de áudio no Office 365 enviará emails ao email dos usuários quando:</span><span class="sxs-lookup"><span data-stu-id="630ea-108">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="630ea-109">**Uma licença de conferência de áudio é atribuída a eles ou quando você está alterando o provedor de serviços de audioconferência para a Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="630ea-109">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="630ea-110">Este e-mail inclui a ID de conferência, o número de telefone de conferência padrão para as reuniões, o PIN de audioconferência para o usuário e as instruções e o link para usar a ferramenta de atualização de reunião do Skype for Business online que é usada para atualizar reuniões existentes para o utilizador.</span><span class="sxs-lookup"><span data-stu-id="630ea-110">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="630ea-111">Consulte [atribuir licenças do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [atribuir a Microsoft como provedor de serviços de audioconferência](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="630ea-111">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="630ea-112">[!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="630ea-112">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="630ea-113">Você pode configurar [IDs dinâmicas de audioconferência em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="630ea-113">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="630ea-114">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="630ea-114">Here is an example of this email:</span></span>
    
     ![Skype for Business Verify License](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="630ea-116">Você pode saber mais sobre as licenças do Skype for Business em [Licenciamento de complementos do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="630ea-116">You can find out more about Skype for Business licensing by seeing [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="630ea-117">**A ID de conferência ou número de telefone de conferência padrão de um usuário for alterado.**</span><span class="sxs-lookup"><span data-stu-id="630ea-117">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="630ea-118">Esse email contém a ID de conferência, o número de conferência padrão, as instruções e links para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário.</span><span class="sxs-lookup"><span data-stu-id="630ea-118">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="630ea-119">Mas esse email não inclui o PIN de audioconferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="630ea-119">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="630ea-120">Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="630ea-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="630ea-121">[!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="630ea-121">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="630ea-122">Você pode configurar [IDs dinâmicas de audioconferência em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="630ea-122">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="630ea-123">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="630ea-123">Here is an example of this email:</span></span>
    
     ![As informações sobre conferência discada foram alteradas.](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="630ea-125">**O PIN de conferência de áudio de um usuário é redefinido.**</span><span class="sxs-lookup"><span data-stu-id="630ea-125">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="630ea-126">Este e-mail contém o pino de audioconferência do organizador, a ID de conferência existente e o número de telefone de conferência padrão para o usuário.</span><span class="sxs-lookup"><span data-stu-id="630ea-126">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="630ea-127">Consulte [redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="630ea-127">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="630ea-128">[!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="630ea-128">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="630ea-129">Você pode configurar [IDs dinâmicas de audioconferência em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="630ea-129">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="630ea-130">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="630ea-130">Here is an example of this email:</span></span>
    
     ![PIN para conferência discada alterado.](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="630ea-132">**A licença de um usuário é removida ou quando o provedor de serviços de audioconferência é alterado da Microsoft para outro provedor ou nenhum.**</span><span class="sxs-lookup"><span data-stu-id="630ea-132">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="630ea-133">Isso acontece quando a licença de **conferência de áudio** é removida de um usuário ou ao alterar o provedor de serviços de audioconferência de um usuário da Microsoft para um provedor de serviços de audioconferência de terceiros ou quando o provedor é definido como **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="630ea-133">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="630ea-134">Este e-mail contém as instruções e informações para o usuário usar a ferramenta de atualização de reunião do Skype for Business online para remover informações específicas da conferência de áudio, como o número de telefone ou a ID de conferência padrão.</span><span class="sxs-lookup"><span data-stu-id="630ea-134">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="630ea-135">Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="630ea-135">See [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="630ea-136">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="630ea-136">Here is an example of this email:</span></span>
    
     ![A conferência discada está desativada.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="630ea-138">Alterar as mensagens de email enviadas a eles</span><span class="sxs-lookup"><span data-stu-id="630ea-138">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="630ea-139">Você pode fazer alterações nos emails enviados automaticamente para os usuários, incluindo o endereço de email e o nome para exibição que está incluído nas informações *de contato do* remetente.</span><span class="sxs-lookup"><span data-stu-id="630ea-139">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="630ea-140">Por padrão, o remetente dos emails será do Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell e o cmdlet [set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=627285) .</span><span class="sxs-lookup"><span data-stu-id="630ea-140">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="630ea-141">Para fazer alterações no endereço de email que está enviando o email aos usuários, você deve:</span><span class="sxs-lookup"><span data-stu-id="630ea-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="630ea-142">Digite o endereço de email no parâmetro  _SendEmailFromAddress_.</span><span class="sxs-lookup"><span data-stu-id="630ea-142">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="630ea-143">Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="630ea-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="630ea-144">Defina o parâmetro _SendEmailOverride_ como _true_.</span><span class="sxs-lookup"><span data-stu-id="630ea-144">Set the  _SendEmailOverride_ parameter to  _True_.</span></span>
    
<span data-ttu-id="630ea-145">Você pode fazer alterações nos emails enviados para usuários, como o endereço de email do qual o email é enviado e o nome de exibição do email, executando:</span><span class="sxs-lookup"><span data-stu-id="630ea-145">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email, by running:</span></span>
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="630ea-146">Se você quiser alterar as informações do endereço de email, é preciso certificar-se de que as políticas de email de entrada do seu ambiente permitam os emails provenientes do endereço de especificado de personalizado.</span><span class="sxs-lookup"><span data-stu-id="630ea-146">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="630ea-147">Se você decidir substituir as informações *de contato do* remetente, verifique se os emails são enviados corretamente para os usuários.</span><span class="sxs-lookup"><span data-stu-id="630ea-147">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="630ea-148">Você pode fazer isso testando isso com um único usuário em sua organização.</span><span class="sxs-lookup"><span data-stu-id="630ea-148">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="630ea-149">Você pode usar o cmdlet [set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações de sua organização, incluindo o email.</span><span class="sxs-lookup"><span data-stu-id="630ea-149">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="630ea-150">E se você não quiser que eles recebam emails?</span><span class="sxs-lookup"><span data-stu-id="630ea-150">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="630ea-151">Ao desativar o envio de emails para os usuários, o email não será enviado mesmo quando o usuário receber uma licença.</span><span class="sxs-lookup"><span data-stu-id="630ea-151">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="630ea-152">Nesse caso, a ID de conferência, o número de telefone de conferência padrão e, o mais importante, o PIN de audioconferência não será enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="630ea-152">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="630ea-153">Quando isso acontecer, você deve informar ao usuário, enviando um email separado ou ligando para eles.</span><span class="sxs-lookup"><span data-stu-id="630ea-153">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="630ea-154">Por padrão, os emails serão enviados aos seus usuários, mas se você quiser impedir que eles recebam emails para videoconferências, você pode usar o centro de administração do Skype for Business ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="630ea-154">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use the Skype for Business admin center or Windows PowerShell.</span></span> 
 
<span data-ttu-id="630ea-155">![Um ícone mostrando o logotipo](../images/sfb-logo-30x30.png)do Skype for Business**usando o centro de administração do Skype for Business**  </span><span class="sxs-lookup"><span data-stu-id="630ea-155">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png)  **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="630ea-156">No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá para **conferência** > de áudio**configurações da ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="630ea-156">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="630ea-157">Na página **configurações da ponte da Microsoft** , marque ou desmarque **enviar emails automaticamente aos usuários se as configurações de conferência de áudio forem alteradas**.</span><span class="sxs-lookup"><span data-stu-id="630ea-157">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="630ea-158">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="630ea-158">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="630ea-159">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="630ea-159">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="630ea-160">Execute os seguintes procedimentos para desabilitar o envio de email a todos os seus usuários:</span><span class="sxs-lookup"><span data-stu-id="630ea-160">Run the following to disable sending all of your users email:</span></span>
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

<span data-ttu-id="630ea-161">Você pode usar o cmdlet [set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações de sua organização, incluindo o email.</span><span class="sxs-lookup"><span data-stu-id="630ea-161">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="630ea-162">O que mais devo saber sobre esse email?</span><span class="sxs-lookup"><span data-stu-id="630ea-162">What else should you know about this email?</span></span>

- <span data-ttu-id="630ea-163">Para mais informações sobre como habilitar e desabilitar o envio de emails para seus usuários, consulte [Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="630ea-163">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="630ea-164">Às vezes, os usuários perdem suas informações de áudio e você precisa ser capaz de enviar todas as informações de áudio para eles.</span><span class="sxs-lookup"><span data-stu-id="630ea-164">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="630ea-165">Você pode fazer isso usando o centro de administração do Skype for Business e clicando em **enviar informações de conferência por e-mail** nas propriedades de audioconferência de áudio de um usuário.</span><span class="sxs-lookup"><span data-stu-id="630ea-165">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user.</span></span> <span data-ttu-id="630ea-166">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="630ea-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="630ea-167">No entanto, essas informações não incluem o PIN de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="630ea-167">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="630ea-168">Este é um exemplo de email que será enviado a eles:</span><span class="sxs-lookup"><span data-stu-id="630ea-168">Here is an example of this email that will be sent to them:</span></span>
    
     ![Email para conferência discada](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="630ea-170">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="630ea-170">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="630ea-171">Por padrão, o remetente dos emails será do Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell e o cmdlet [set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=627285) .</span><span class="sxs-lookup"><span data-stu-id="630ea-171">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span>
    
- <span data-ttu-id="630ea-p113">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="630ea-p113">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="630ea-175">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="630ea-175">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="630ea-176">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="630ea-176">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="630ea-177">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está realizando alterações de configuração para muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="630ea-177">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="630ea-178">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="630ea-178">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="630ea-179">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="630ea-179">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="630ea-180">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="630ea-180">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="630ea-181">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="630ea-181">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="630ea-p115">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="630ea-p115">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="630ea-184">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="630ea-184">Related topics</span></span>

[<span data-ttu-id="630ea-185">Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="630ea-185">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="630ea-186">Enviar um email para um usuário com suas informações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="630ea-186">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
