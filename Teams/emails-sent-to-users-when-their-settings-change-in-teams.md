---
title: Emails enviados para os usuários quando suas configurações são alteradas
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Saiba mais sobre quais informações são enviadas automaticamente aos usuários por email quando suas configurações de conferência discada mudam no Microsoft Teams. '
ms.openlocfilehash: a9ca30e7e701afca2e42eccfaef4f3d45660cd3a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120752"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="cb555-103">E-mails enviados para os usuários quando suas configurações são alteradas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cb555-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="cb555-104">Os emails serão enviados automaticamente para usuários habilitados para [Audioconferência](set-up-audio-conferencing-in-teams.md) usando a Microsoft como provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="cb555-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="cb555-105">Por padrão, há quatro tipos de email que serão enviados aos usuários habilitados para Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="cb555-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="cb555-106">No entanto, se você quiser limitar o número de emails enviados aos usuários, poderá desativar.</span><span class="sxs-lookup"><span data-stu-id="cb555-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="cb555-107">Audioconferência no Microsoft 365 ou Office 365 enviará emails para o email de seus usuários quando:</span><span class="sxs-lookup"><span data-stu-id="cb555-107">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="cb555-108">**Uma licença de Audioconferência é atribuída a eles ou quando você está alterando o provedor de audioconferência para a Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="cb555-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="cb555-109">Este email inclui a ID da conferência, o número de telefone de conferência padrão para as reuniões, o PIN de audioconferência para o usuário e as instruções e o link para usar a Ferramenta de Atualização de Reunião do Skype for Business Online usada para atualizar reuniões existentes para o usuário.</span><span class="sxs-lookup"><span data-stu-id="cb555-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="cb555-110">Consulte [Atribuir licenças de](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) complemento do Microsoft Teams ou Atribuir a Microsoft como provedor de [audioconferência.](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)</span><span class="sxs-lookup"><span data-stu-id="cb555-110">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="cb555-111">[!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="cb555-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="cb555-112">Você pode configurar [IDs dinâmicas de Audioconferência em sua organização.](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)</span><span class="sxs-lookup"><span data-stu-id="cb555-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="cb555-113">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="cb555-113">Here is an example of this email:</span></span>

     ![Skype for Business Verify License](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="cb555-115">Para saber mais sobre licenciamento, consulte [Licenciamento de complemento do Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="cb555-115">To find out more about licensing, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="cb555-116">**A ID de conferência ou número de telefone de conferência padrão de um usuário for alterado.**</span><span class="sxs-lookup"><span data-stu-id="cb555-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="cb555-117">Esse email contém a ID de conferência, o número de conferência padrão, as instruções e links para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário.</span><span class="sxs-lookup"><span data-stu-id="cb555-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="cb555-118">Mas esse email não inclui o PIN de audioconferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="cb555-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="cb555-119">Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cb555-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="cb555-120">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="cb555-120">Here is an example of this email:</span></span>

     ![As informações sobre conferência discada foram alteradas.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="cb555-122">**O PIN de audioconferência de um usuário é redefinido.**</span><span class="sxs-lookup"><span data-stu-id="cb555-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="cb555-123">Este email contém o PIN de audioconferência do organizador, a ID de conferência existente e o número de telefone de conferência padrão para o usuário.</span><span class="sxs-lookup"><span data-stu-id="cb555-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="cb555-124">Consulte [Redefinir o PIN de Audioconferência](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cb555-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="cb555-125">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="cb555-125">Here is an example of this email:</span></span>
    
     ![PIN para conferência discada alterado.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="cb555-127">**A licença de um usuário é removida ou quando o provedor de audioconferência muda da Microsoft para outro provedor ou Nenhum.**</span><span class="sxs-lookup"><span data-stu-id="cb555-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="cb555-128">Isso acontece quando a **licença de Audioconferência** é removida de um usuário ou ao definir o provedor de audioconferência como **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="cb555-128">This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.</span></span>

    <span data-ttu-id="cb555-129">Consulte [Atribuir ou remover licenças do Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="cb555-129">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="cb555-130">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="cb555-130">Here is an example of this email:</span></span>

     ![A conferência discada está desativada.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="cb555-132">Alterar as mensagens de email enviadas a eles</span><span class="sxs-lookup"><span data-stu-id="cb555-132">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="cb555-133">Você pode fazer alterações no email que é enviado automaticamente aos usuários.</span><span class="sxs-lookup"><span data-stu-id="cb555-133">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="cb555-134">Por padrão, o remetente dos emails será do Microsoft 365 ou office 365, mas você pode alterar o nome de exibição usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb555-134">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="cb555-135">Consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cb555-135">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="cb555-136">E se você não quiser que eles recebam emails?</span><span class="sxs-lookup"><span data-stu-id="cb555-136">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="cb555-137">Ao desativar o envio de emails para os usuários, o email não será enviado mesmo quando o usuário receber uma licença.</span><span class="sxs-lookup"><span data-stu-id="cb555-137">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="cb555-138">Nesse caso, a ID da conferência, o número de telefone de conferência padrão e, o mais importante, o PIN de audioconferência não serão enviados ao usuário.</span><span class="sxs-lookup"><span data-stu-id="cb555-138">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="cb555-139">Quando isso acontecer, você deve informar ao usuário, enviando um email separado ou ligando para eles.</span><span class="sxs-lookup"><span data-stu-id="cb555-139">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="cb555-140">Por padrão, os emails serão enviados para seus usuários, mas se você quiser impedir que eles recebam emails para audioconferência, você pode usar o Microsoft Teams ou Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb555-140">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="cb555-141">![Um ícone que mostra o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="cb555-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="cb555-142">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="cb555-142">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="cb555-143">Na parte superior da página **Pontes de Conferência,** clique em **Configurações de ponte.**</span><span class="sxs-lookup"><span data-stu-id="cb555-143">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="cb555-144">No painel **Configurações de** ponte, habilita ou desabilita Enviar emails automaticamente aos usuários se suas configurações de **discagem mudarem**.</span><span class="sxs-lookup"><span data-stu-id="cb555-144">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="cb555-145">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cb555-145">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="cb555-146">**Usando Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="cb555-146">**Using Windows PowerShell**</span></span>

<span data-ttu-id="cb555-147">Consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cb555-147">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="cb555-148">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="cb555-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="cb555-149">Por padrão, o remetente dos emails será do Microsoft 365 ou do Office 365, mas você pode alterar o endereço de email e o nome de exibição usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb555-149">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="cb555-150">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="cb555-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="cb555-151">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="cb555-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="cb555-152">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="cb555-152">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="cb555-153">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="cb555-153">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="cb555-154">[Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="cb555-154">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="cb555-155">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cb555-155">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="cb555-156">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cb555-156">Related topics</span></span>

[<span data-ttu-id="cb555-157">Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="cb555-157">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="cb555-158">Enviar um email para um usuário com suas informações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="cb555-158">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)