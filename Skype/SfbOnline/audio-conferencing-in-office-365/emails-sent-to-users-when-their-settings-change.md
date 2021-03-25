---
title: Emails enviados aos usuários quando suas configurações mudam no Skype for Business Online
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Saiba mais sobre quais informações são enviadas automaticamente aos usuários por email quando suas configurações de conferência discada mudam no Skype for Business Online. '
ms.openlocfilehash: 4ab95af236fdb0ef8ff3aee6004fa8b11bf313af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110027"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a><span data-ttu-id="7fa8b-103">Emails enviados aos usuários quando suas configurações mudam no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7fa8b-103">Emails sent to users when their settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="7fa8b-104">Se você estiver procurando informações de email automáticas no Microsoft Teams, consulte Emails enviados aos usuários quando suas configurações [mudarem no Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="7fa8b-104">If you're looking for automatic email information in Microsoft Teams, see [Emails sent to users when their settings change in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="7fa8b-105">Os emails serão enviados automaticamente para usuários habilitados para [Audioconferência](set-up-audio-conferencing.md) usando a Microsoft como provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-105">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing.md) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="7fa8b-106">Por padrão, há quatro tipos de email que serão enviados aos usuários habilitados para Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-106">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="7fa8b-107">No entanto, se você quiser limitar o número de emails enviados aos usuários, poderá desativar.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-107">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="7fa8b-108">Audioconferência no Microsoft 365 ou Office 365 enviará emails para o email de seus usuários quando:</span><span class="sxs-lookup"><span data-stu-id="7fa8b-108">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="7fa8b-109">**Uma licença de Audioconferência é atribuída a eles ou quando você está alterando o provedor de audioconferência para a Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="7fa8b-109">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="7fa8b-110">Este email inclui a ID da conferência, o número de telefone de conferência padrão para as reuniões, o PIN de audioconferência para o usuário e as instruções e o link para usar a Ferramenta de Atualização de Reunião do Skype for Business Online usada para atualizar reuniões existentes para o usuário.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-110">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="7fa8b-111">Consulte [Atribuir licenças do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou Atribuir a Microsoft como provedor de [audioconferência.](assign-microsoft-as-the-audio-conferencing-provider.md)</span><span class="sxs-lookup"><span data-stu-id="7fa8b-111">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7fa8b-112">[!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-112">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="7fa8b-113">Você pode configurar [IDs dinâmicas de Audioconferência em sua organização.](./reset-a-conference-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="7fa8b-113">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="7fa8b-114">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="7fa8b-114">Here is an example of this email:</span></span>
    
     ![Skype for Business Verify License](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="7fa8b-116">Você pode saber mais sobre as licenças do Skype for Business em [Licenciamento de complementos do Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="7fa8b-116">You can find out more about Skype for Business licensing by seeing [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="7fa8b-117">**A ID de conferência ou número de telefone de conferência padrão de um usuário for alterado.**</span><span class="sxs-lookup"><span data-stu-id="7fa8b-117">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="7fa8b-118">Esse email contém a ID de conferência, o número de conferência padrão, as instruções e links para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-118">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="7fa8b-119">Mas esse email não inclui o PIN de audioconferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-119">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="7fa8b-120">Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="7fa8b-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7fa8b-121">[!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-121">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="7fa8b-122">Você pode configurar [IDs dinâmicas de Audioconferência em sua organização.](./reset-a-conference-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="7fa8b-122">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="7fa8b-123">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="7fa8b-123">Here is an example of this email:</span></span>
    
     ![As informações sobre conferência discada foram alteradas.](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="7fa8b-125">**O PIN de audioconferência de um usuário é redefinido.**</span><span class="sxs-lookup"><span data-stu-id="7fa8b-125">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="7fa8b-126">Este email contém o PIN de audioconferência do organizador, a ID de conferência existente e o número de telefone de conferência padrão para o usuário.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-126">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="7fa8b-127">Consulte [Redefinir o PIN de Audioconferência](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="7fa8b-127">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7fa8b-128">[!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-128">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="7fa8b-129">Você pode configurar [IDs dinâmicas de Audioconferência em sua organização.](./reset-a-conference-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="7fa8b-129">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="7fa8b-130">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="7fa8b-130">Here is an example of this email:</span></span>
    
     ![PIN para conferência discada alterado.](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="7fa8b-132">**A licença de um usuário é removida ou quando o provedor de audioconferência muda da Microsoft para outro provedor ou Nenhum.**</span><span class="sxs-lookup"><span data-stu-id="7fa8b-132">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="7fa8b-133">Isso acontece quando a licença de **Audioconferência** é removida de um usuário ou ao alterar o provedor de audioconferência de um usuário da Microsoft para um provedor de audioconferência de terceiros ou ao definir o provedor como **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-133">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="7fa8b-134">Este email contém as instruções e informações para o usuário usar a Ferramenta de Atualização de Reunião do Skype for Business Online para remover informações específicas de audioconferência, como o número de telefone de conferência padrão ou a ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-134">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="7fa8b-135">Consulte [Atribuir ou remover licenças para Aplicativos do Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="7fa8b-135">See [Assign or remove licenses for Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="7fa8b-136">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="7fa8b-136">Here is an example of this email:</span></span>
    
     ![A conferência discada está desativada.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="7fa8b-138">Alterar as mensagens de email enviadas a eles</span><span class="sxs-lookup"><span data-stu-id="7fa8b-138">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="7fa8b-139">Você pode fazer alterações no email que é enviado automaticamente aos usuários, incluindo o endereço de email e o nome de exibição incluído nas informações de contato *From.*</span><span class="sxs-lookup"><span data-stu-id="7fa8b-139">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="7fa8b-140">Por padrão, o remetente dos emails será do Microsoft 365 ou do Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="7fa8b-140">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet.</span></span> <span data-ttu-id="7fa8b-141">Para fazer alterações no endereço de email que está enviando o email para os usuários, você deve:</span><span class="sxs-lookup"><span data-stu-id="7fa8b-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="7fa8b-142">Digite o endereço de email no parâmetro  _SendEmailFromAddress_.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-142">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="7fa8b-143">Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="7fa8b-144">De definir  _o parâmetro SendEmailOverride_ como  _True_.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-144">Set the  _SendEmailOverride_ parameter to  _True_.</span></span>
    
<span data-ttu-id="7fa8b-145">Você pode fazer alterações no email enviado aos usuários, como o endereço de email de onde o email é enviado e o nome de exibição do email, executando:</span><span class="sxs-lookup"><span data-stu-id="7fa8b-145">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email, by running:</span></span>
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="7fa8b-146">Se você quiser alterar as informações de endereço de email, você precisa se certificar de que as políticas de email de entrada do seu ambiente permitem emails que vêm do endereço personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-146">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="7fa8b-147">Se você decidir substituir as informações de contato *De,* verifique se os emails são enviados corretamente aos usuários.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-147">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="7fa8b-148">Você pode fazer isso testando isso com um usuário em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-148">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="7fa8b-149">Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) para gerenciar outras configurações para sua organização, incluindo email.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-149">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="7fa8b-150">E se você não quiser que eles recebam emails?</span><span class="sxs-lookup"><span data-stu-id="7fa8b-150">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="7fa8b-151">Ao desativar o envio de emails para os usuários, o email não será enviado mesmo quando o usuário receber uma licença.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-151">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="7fa8b-152">Nesse caso, a ID da conferência, o número de telefone de conferência padrão e, o mais importante, o PIN de audioconferência não serão enviados ao usuário.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-152">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="7fa8b-153">Quando isso acontecer, você deve informar ao usuário, enviando um email separado ou ligando para eles.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-153">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="7fa8b-154">Por padrão, os emails serão enviados para seus usuários, mas se você quiser impedir que eles recebam emails para audioconferência, você pode usar o Centro de administração do Skype for Business ou Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-154">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use the Skype for Business admin center or Windows PowerShell.</span></span> 
 
<span data-ttu-id="7fa8b-155">![Um ícone mostrando o logotipo do Skype for Business ](../images/sfb-logo-30x30.png) **usando o centro de administração do Skype for Business**  </span><span class="sxs-lookup"><span data-stu-id="7fa8b-155">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png)  **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="7fa8b-156">No Centro de administração do **Skype for Business**, na navegação à esquerda, vá para Configurações de ponte da Microsoft de **audioconferência.**  >  </span><span class="sxs-lookup"><span data-stu-id="7fa8b-156">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="7fa8b-157">Na página **Configurações de ponte da Microsoft,** selecione ou desempure Enviar emails automaticamente aos usuários se suas configurações de **audioconferência mudarem**.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-157">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="7fa8b-158">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-158">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="7fa8b-159">**Usando Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="7fa8b-159">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="7fa8b-160">Execute os seguintes procedimentos para desabilitar o envio de email a todos os seus usuários:</span><span class="sxs-lookup"><span data-stu-id="7fa8b-160">Run the following to disable sending all of your users email:</span></span>
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

<span data-ttu-id="7fa8b-161">Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) para gerenciar outras configurações para sua organização, incluindo email.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-161">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="7fa8b-162">O que mais devo saber sobre esse email?</span><span class="sxs-lookup"><span data-stu-id="7fa8b-162">What else should you know about this email?</span></span>

- <span data-ttu-id="7fa8b-163">Para mais informações sobre como habilitar e desabilitar o envio de emails para seus usuários, consulte [Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="7fa8b-163">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="7fa8b-164">Às vezes, os usuários perdem suas informações de áudio e você precisa ser capaz de enviar todas as informações de áudio para eles.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-164">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="7fa8b-165">Você pode fazer isso usando o Centro de administração do Skype for Business e clicando em Enviar informações de conferência por **email** nas propriedades de audioconferência para um usuário.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-165">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user.</span></span> <span data-ttu-id="7fa8b-166">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="7fa8b-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="7fa8b-167">No entanto, essas informações não incluem o PIN de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-167">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="7fa8b-168">Este é um exemplo de email que será enviado a eles:</span><span class="sxs-lookup"><span data-stu-id="7fa8b-168">Here is an example of this email that will be sent to them:</span></span>
    
     ![Email para conferência discada](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="7fa8b-170">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7fa8b-170">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="7fa8b-171">Por padrão, o remetente dos emails será do Microsoft 365 ou do Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="7fa8b-171">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet.</span></span>
    
- <span data-ttu-id="7fa8b-172">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-172">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7fa8b-173">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-173">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="7fa8b-174">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="7fa8b-174">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7fa8b-175">Por que você precisa usar o Microsoft 365 ou o Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7fa8b-175">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="7fa8b-176">[Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="7fa8b-176">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="7fa8b-177">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="7fa8b-177">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="7fa8b-178">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="7fa8b-178">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="7fa8b-179">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7fa8b-179">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="7fa8b-180">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7fa8b-180">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="7fa8b-181">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7fa8b-181">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="7fa8b-p115">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="7fa8b-p115">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7fa8b-184">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7fa8b-184">Related topics</span></span>

[<span data-ttu-id="7fa8b-185">Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="7fa8b-185">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="7fa8b-186">Enviar um email para um usuário com suas informações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="7fa8b-186">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)