---
title: Emails enviados aos usuários ao alteram suas configurações
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: 'Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. '
ms.openlocfilehash: 0cf1eabd25a6be5d6104c2593e5bc286d15d59f0
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2018
---
# <a name="emails-sent-to-users-when-their-settings-change"></a><span data-ttu-id="c90fa-103">Emails enviados aos usuários ao alteram suas configurações</span><span class="sxs-lookup"><span data-stu-id="c90fa-103">Emails sent to users when their settings change</span></span>

<span data-ttu-id="c90fa-104">Emails serão enviados automaticamente para usuários que estão [habilitados para conferência de áudio](set-up-audio-conferencing.md) usando o Microsoft como um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="c90fa-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing.md) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="c90fa-105">Por padrão, há quatro tipos de email que será enviada para os usuários habilitados para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="c90fa-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="c90fa-106">No entanto, se desejar limitar o número de emails enviados aos usuários, você pode desativá-lo.</span><span class="sxs-lookup"><span data-stu-id="c90fa-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="c90fa-107">Serviços de audioconferência no Office 365 enviará o email para seus usuários de email quando:</span><span class="sxs-lookup"><span data-stu-id="c90fa-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="c90fa-108">**Uma licença de conferência de áudio é atribuída a eles ou quando você estiver alterando o provedor de serviços de audioconferência à Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="c90fa-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="c90fa-109">Este email inclui o ID de conferência, o número de telefone de conferência padrão para as reuniões, os serviços de audioconferência PIN para o usuário e as instruções e link usar o Skype para negócios Online Meeting Update Tool que é usado para atualizar as reuniões existentes para o usuário.</span><span class="sxs-lookup"><span data-stu-id="c90fa-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="c90fa-110">Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [Atribuir Microsoft como um provedor de serviços de audioconferência](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="c90fa-110">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c90fa-111">[!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="c90fa-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="c90fa-112">Você pode configurar as [IDs de conferência de áudio dinâmicos em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="c90fa-112">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="c90fa-113">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="c90fa-113">Here is an example of this email:</span></span>
    
     ![Skype for Business Verify License](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="c90fa-115">Você pode encontrar mais informações sobre Skype para licenciamento de negócios, conferindo [Skype para licenciamento de complemento de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c90fa-115">You can find out more about Skype for Business licensing by seeing [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="c90fa-116">**A ID de conferência ou número de telefone de conferência padrão de um usuário for alterado.**</span><span class="sxs-lookup"><span data-stu-id="c90fa-116">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="c90fa-117">Esse email contém a ID de conferência, o número de conferência padrão, as instruções e links para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário.</span><span class="sxs-lookup"><span data-stu-id="c90fa-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="c90fa-118">Mas este email não inclui serviços de audioconferência PIN do usuário.</span><span class="sxs-lookup"><span data-stu-id="c90fa-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="c90fa-119">Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="c90fa-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c90fa-120">[!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="c90fa-120">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="c90fa-121">Você pode configurar as [IDs de conferência de áudio dinâmicos em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="c90fa-121">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="c90fa-122">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="c90fa-122">Here is an example of this email:</span></span>
    
     ![As informações sobre conferência discada foram alteradas.](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="c90fa-124">**O PIN de um usuário de serviços de audioconferência é redefinido.**</span><span class="sxs-lookup"><span data-stu-id="c90fa-124">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="c90fa-125">Este email contém serviços de audioconferência do organizador PIN, o ID de conferência existente e número de telefone de conferência padrão para o usuário.</span><span class="sxs-lookup"><span data-stu-id="c90fa-125">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="c90fa-126">Veja [Redefinir o PIN de conferência de áudio para um usuário](reset-the-audio-conferencing-pin-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="c90fa-126">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c90fa-127">[!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="c90fa-127">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="c90fa-128">Você pode configurar as [IDs de conferência de áudio dinâmicos em sua organização](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="c90fa-128">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="c90fa-129">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="c90fa-129">Here is an example of this email:</span></span>
    
     ![PIN para conferência discada alterado.](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="c90fa-131">**Uma licença de usuário é removida ou quando o provedor de serviços de audioconferência altera da Microsoft para outro provedor ou nenhum.**</span><span class="sxs-lookup"><span data-stu-id="c90fa-131">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="c90fa-132">Isso acontece quando a licença de **Conferência de áudio** é removida de um usuário ou quando a alteração do provedor de serviços de audioconferência de um usuário da Microsoft a um provedor de serviços de audioconferência de terceiros ou ao configurar o provedor como **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="c90fa-132">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="c90fa-133">Este email contém as instruções e informações para o usuário usar o Skype para ferramenta de atualização de Reunião Online comercial para remover informações específicas de conferência de áudio, como o padrão ID de conferência telefônica número ou conferência.</span><span class="sxs-lookup"><span data-stu-id="c90fa-133">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="c90fa-134">Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="c90fa-134">See [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="c90fa-135">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="c90fa-135">Here is an example of this email:</span></span>
    
     ![A conferência discada está desativada.](../images/audio-conferencing-turned-off.png)
  
## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="c90fa-137">Alterar as mensagens de email enviadas a eles</span><span class="sxs-lookup"><span data-stu-id="c90fa-137">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="c90fa-138">Você pode fazer alterações para email que será enviado automaticamente aos usuários, incluindo o endereço de email e o nome de exibição que está incluído nas informações de contato *do* .</span><span class="sxs-lookup"><span data-stu-id="c90fa-138">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="c90fa-139">Por padrão, o remetente dos e-mails será do Office 365, mas você pode alterar o endereço de email e nome para exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .</span><span class="sxs-lookup"><span data-stu-id="c90fa-139">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="c90fa-140">Para fazer alterações para o endereço de email que está enviando email aos usuários, você deve:</span><span class="sxs-lookup"><span data-stu-id="c90fa-140">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="c90fa-141">Digite o endereço de email no parâmetro  _SendEmailFromAddress_.</span><span class="sxs-lookup"><span data-stu-id="c90fa-141">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="c90fa-142">Digite o nome exibido no email no parâmetro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="c90fa-142">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="c90fa-143">Defina o parâmetro _SendEmailOverride_ como _True_.</span><span class="sxs-lookup"><span data-stu-id="c90fa-143">Set the  _SendEmailOverride_ parameter to  _True_.</span></span>
    
<span data-ttu-id="c90fa-144">Você pode fazer alterações para o email enviado aos usuários, como o endereço de email que o email é enviado de e o nome de exibição para o email, executando:</span><span class="sxs-lookup"><span data-stu-id="c90fa-144">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email, by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="c90fa-145">Se você deseja alterar as informações de endereço de email, será necessário certificar-se de que as políticas de email de entrada do seu ambiente permitem emails provenientes de personalizado especificado do endereço.</span><span class="sxs-lookup"><span data-stu-id="c90fa-145">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="c90fa-146">Se você decidir substituir as informações de contato *do* , você deve verificar se os emails corretamente serão enviados aos usuários.</span><span class="sxs-lookup"><span data-stu-id="c90fa-146">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="c90fa-147">Você pode fazer isso testando isso com um usuário em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c90fa-147">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="c90fa-148">Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações da sua organização, incluindo email.</span><span class="sxs-lookup"><span data-stu-id="c90fa-148">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="c90fa-149">E se você não quiser que eles recebam emails?</span><span class="sxs-lookup"><span data-stu-id="c90fa-149">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="c90fa-150">Ao desativar o envio de emails para os usuários, o email não será enviado mesmo quando o usuário receber uma licença.</span><span class="sxs-lookup"><span data-stu-id="c90fa-150">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="c90fa-151">Neste caso, o ID de conferência, padrão o número de telefone de conferência e, mais importante, o seu PIN de conferência de áudio não será enviada ao usuário.</span><span class="sxs-lookup"><span data-stu-id="c90fa-151">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="c90fa-152">Quando isso acontecer, você deve informar ao usuário, enviando um email separado ou ligando para eles.</span><span class="sxs-lookup"><span data-stu-id="c90fa-152">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="c90fa-153">Por padrão, emails serão enviadas aos seus usuários, mas se desejar impedir a email de recebimento para conferência de áudio, você pode usar o Microsoft Teams, o Skype para o Centro de administração de negócios, ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c90fa-153">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams, the Skype for Business admin center, or Windows PowerShell.</span></span> 

<span data-ttu-id="c90fa-154">**Usando equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="c90fa-154">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="c90fa-155">No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="c90fa-155">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="c90fa-156">Na parte superior da página **Pontes de conferência** , clique em **Configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="c90fa-156">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="c90fa-157">No painel de **configurações de ponte** , habilite ou desabilite a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de discagem**.</span><span class="sxs-lookup"><span data-stu-id="c90fa-157">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="c90fa-158">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c90fa-158">Click **Apply**.</span></span>
  
<span data-ttu-id="c90fa-159">**Usando o Skype para o Centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="c90fa-159">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="c90fa-160">No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="c90fa-160">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="c90fa-161">Na página **configurações de ponte da Microsoft** , marque ou desmarque **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de conferência de áudio**.</span><span class="sxs-lookup"><span data-stu-id="c90fa-161">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="c90fa-162">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c90fa-162">Click **Save**.</span></span> 
    
<span data-ttu-id="c90fa-163">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c90fa-163">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="c90fa-164">Execute os seguintes procedimentos para desabilitar o envio de email a todos os seus usuários:</span><span class="sxs-lookup"><span data-stu-id="c90fa-164">Run the following to disable sending all of your users email:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

<span data-ttu-id="c90fa-165">Você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) para gerenciar outras configurações da sua organização, incluindo email.</span><span class="sxs-lookup"><span data-stu-id="c90fa-165">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="c90fa-166">O que mais devo saber sobre esse email?</span><span class="sxs-lookup"><span data-stu-id="c90fa-166">What else should you know about this email?</span></span>

- <span data-ttu-id="c90fa-167">Para mais informações sobre como habilitar e desabilitar o envio de emails para seus usuários, consulte [Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="c90fa-167">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="c90fa-168">Em alguns casos, os usuários perderão suas informações de áudio e você precisa ser capaz de enviar-lhes todas as suas informações de áudio para acessá-los.</span><span class="sxs-lookup"><span data-stu-id="c90fa-168">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="c90fa-169">Você pode fazer isso usando o Skype para centro de administração de negócios e clicar em **Enviar informações de conferência via email** , sob as propriedades de conferência de áudio para um usuário.</span><span class="sxs-lookup"><span data-stu-id="c90fa-169">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user.</span></span> <span data-ttu-id="c90fa-170">Veja [Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="c90fa-170">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="c90fa-171">No entanto, essas informações não incluem o PIN de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="c90fa-171">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="c90fa-172">Este é um exemplo de email que será enviado a eles:</span><span class="sxs-lookup"><span data-stu-id="c90fa-172">Here is an example of this email that will be sent to them:</span></span>
    
     ![Email para conferência discada](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c90fa-174">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c90fa-174">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c90fa-175">Por padrão, o remetente dos e-mails será do Office 365, mas você pode alterar o endereço de email e nome para exibição usando o Windows PowerShell e o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .</span><span class="sxs-lookup"><span data-stu-id="c90fa-175">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span>
    
- <span data-ttu-id="c90fa-p113">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c90fa-p113">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c90fa-179">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="c90fa-179">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c90fa-180">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c90fa-180">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="c90fa-181">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="c90fa-181">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c90fa-182">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c90fa-182">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="c90fa-183">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c90fa-183">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c90fa-184">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c90fa-184">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c90fa-185">Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c90fa-185">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="c90fa-p115">[!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="c90fa-p115">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c90fa-188">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c90fa-188">Related topics</span></span>

[<span data-ttu-id="c90fa-189">Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="c90fa-189">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="c90fa-190">Enviar um email para um usuário com suas informações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="c90fa-190">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
