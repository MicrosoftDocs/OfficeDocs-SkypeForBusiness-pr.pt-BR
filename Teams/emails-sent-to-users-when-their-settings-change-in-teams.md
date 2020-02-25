---
title: E-mails enviados para os usuários quando suas configurações são alteradas no Microsoft Teams
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
description: 'Saiba as informações que são enviadas automaticamente aos usuários por e-mail quando suas configurações de conferência discada são alteradas no Microsoft Teams. '
ms.openlocfilehash: 28dcf8e166eff4a8852dd1ad77828213dc88fd05
ms.sourcegitcommit: 73518a589db1a9883fc97827f0ddb9132995fbfa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42236861"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="ca8e7-103">E-mails enviados para os usuários quando suas configurações são alteradas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ca8e7-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="ca8e7-104">Serão enviados e-mails automaticamente para usuários que estão [habilitados para audioconferência](set-up-audio-conferencing-in-teams.md) e usam a Microsoft como provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="ca8e7-105">Por padrão, existem quatro tipos de e-mail que são enviados aos usuários habilitados para audioconferência.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="ca8e7-106">No entanto, se você deseja limitar o número de e-mails enviados aos usuários, é possível desativá-los.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="ca8e7-107">A audioconferência no Office 365 enviará um e-mail para o e-mail de seus usuários quando:</span><span class="sxs-lookup"><span data-stu-id="ca8e7-107">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="ca8e7-108">**Uma licença de Audioconferência PSTN for atribuída a eles ou quando você alterar o provedor de audioconferência para a Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="ca8e7-109">Esse e-mail inclui o ID de conferência, o número de telefone de conferência padrão para as reuniões, o PIN de audioconferência do usuário, além das instruções e do link para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="ca8e7-110">Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md) ou [atribuir a Microsoft como o provedor de áudio de audioconferência](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="ca8e7-110">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca8e7-111">Se a sua organização estiver habilitada para IDs de conferência dinâmicos, todas as reuniões agendadas de um usuário terão IDs de conferência exclusivos.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="ca8e7-112">Você pode configurar [IDs dinâmicos de audioconferência na sua organização](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="ca8e7-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="ca8e7-113">Aqui está um exemplo desse e-mail:</span><span class="sxs-lookup"><span data-stu-id="ca8e7-113">Here is an example of this email:</span></span>

     ![Verificar licença do Skype for Business](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="ca8e7-115">Para saber mais sobre licenciamento, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="ca8e7-115">To find out more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="ca8e7-116">**O ID de conferência ou número de telefone de conferência padrão de um usuário é alterado.**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="ca8e7-117">Esse email contém a ID de conferência, o número de conferência padrão, as instruções e links para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="ca8e7-118">Mas esse e-mail não inclui o PIN de audioconferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="ca8e7-119">Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ca8e7-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="ca8e7-120">Aqui está um exemplo desse e-mail:</span><span class="sxs-lookup"><span data-stu-id="ca8e7-120">Here is an example of this email:</span></span>

     ![As informações sobre conferência discada foram alteradas.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="ca8e7-122">**O PIN de audioconferência de um usuário é redefinido.**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="ca8e7-123">Esse e-mail contém o PIN de audioconferência do organizador, o ID de conferência existente e o número de telefone de conferência padrão do usuário.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="ca8e7-124">Veja [Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ca8e7-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="ca8e7-125">Aqui está um exemplo desse e-mail:</span><span class="sxs-lookup"><span data-stu-id="ca8e7-125">Here is an example of this email:</span></span>
    
     ![O PIN de conferência discada foi alterado.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="ca8e7-127">**A licença do usuário for removida ou quando o provedor de audioconferência é alterado da Microsoft para outro provedor ou Nenhum.**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="ca8e7-128">Isso acontece quando a licença de **conferência de áudio** é removida de um usuário ou ao configurar o provedor de serviços de audioconferência para **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-128">This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.</span></span>

    <span data-ttu-id="ca8e7-129">Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="ca8e7-129">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="ca8e7-130">Aqui está um exemplo desse email:</span><span class="sxs-lookup"><span data-stu-id="ca8e7-130">Here is an example of this email:</span></span>

     ![A conferência discada está desativada.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="ca8e7-132">Alterar as mensagens de email enviadas a eles</span><span class="sxs-lookup"><span data-stu-id="ca8e7-132">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="ca8e7-133">Você pode fazer alterações ao email que será enviado automaticamente aos usuários.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-133">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="ca8e7-134">Por padrão, o remetente dos emails será do Office 365, mas você pode alterar o nome de exibição usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-134">By default, the sender of the emails will be from Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="ca8e7-135">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-135">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="ca8e7-136">E se você não quiser que eles recebam emails?</span><span class="sxs-lookup"><span data-stu-id="ca8e7-136">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="ca8e7-137">Ao desativar o envio de emails para os usuários, o email não será enviado mesmo quando o usuário receber uma licença.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-137">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="ca8e7-138">Nesse caso, a ID de conferência, o número de telefone de conferência padrão e, o mais importante, o PIN de audioconferência não será enviado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-138">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="ca8e7-139">Quando isso acontecer, você deve informar ao usuário, enviando um email separado ou ligando para eles.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-139">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="ca8e7-140">Por padrão, os emails serão enviados aos seus usuários, mas se você quiser impedir que eles recebam emails para videoconferências, você pode usar o Microsoft Teams ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-140">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="ca8e7-141">![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ca8e7-142">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-142">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="ca8e7-143">Na parte superior da página **pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-143">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="ca8e7-144">No painel **configurações de ponte** , habilite ou desabilite **enviar emails automaticamente aos usuários se as configurações de discagem forem alteradas**.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-144">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="ca8e7-145">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-145">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="ca8e7-146">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ca8e7-146">**Using Windows PowerShell**</span></span>

<span data-ttu-id="ca8e7-147">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-147">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ca8e7-148">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ca8e7-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="ca8e7-149">Por padrão, o remetente dos emails será do Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-149">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="ca8e7-p108">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ca8e7-p108">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="ca8e7-153">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="ca8e7-153">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="ca8e7-154">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca8e7-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="ca8e7-155">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ca8e7-155">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ca8e7-156">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ca8e7-156">Related topics</span></span>

[<span data-ttu-id="ca8e7-157">Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="ca8e7-157">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="ca8e7-158">Enviar um email para um usuário com suas informações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="ca8e7-158">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
