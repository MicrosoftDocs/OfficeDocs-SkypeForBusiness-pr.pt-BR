---
title: Ativar ou desativar o envio de e-mails quando alterar configurações de audioconferência no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: 'Saiba como ativar ou desativar o Skype de enviar e-mails para usuários quando configurações, como alterações de PIN ou o número de conferência padrão, são alteradas no Microsoft Teams. '
ms.openlocfilehash: 7c08f0268c707a545873afe76e850a90a41087b4
ms.sourcegitcommit: d3c459dc1304db5f5ba78b5e093b5a4fd797c8ec
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "30178634"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="6a506-103">Ativar ou desativar o envio de e-mails quando alterar configurações de audioconferência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a506-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="6a506-104">Os usuários são notificados automaticamente por e-mail quando são habilitados para audioconferência.</span><span class="sxs-lookup"><span data-stu-id="6a506-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="6a506-105">Pode haver ocasiões, no entanto, em que você deseja reduzir o número de e-mails enviados aos usuários do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6a506-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="6a506-106">Nesses casos, você pode desabilitar o envio de e-mails.</span><span class="sxs-lookup"><span data-stu-id="6a506-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="6a506-107">Se você desabilitar o envio de e-mails, nenhum e-mail de audioconferência será enviado para os usuários, incluindo e-mails notificando quando o usuário está habilitado ou desabilitado para audioconferência, quando o PIN é redefinido ou quando o número de telefone padrão e o ID de conferência são alterados.</span><span class="sxs-lookup"><span data-stu-id="6a506-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="6a506-108">Aqui está um exemplo de e-mail enviado aos usuários habilitados para audioconferência:</span><span class="sxs-lookup"><span data-stu-id="6a506-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![E-mail de audioconferência](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="6a506-110">Quando os e-mails são enviados aos seus usuários?</span><span class="sxs-lookup"><span data-stu-id="6a506-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="6a506-111">Vários e-mails são enviados aos usuários da sua organização depois que são habilitados para a audioconferência:</span><span class="sxs-lookup"><span data-stu-id="6a506-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="6a506-112">Quando uma licença de **Audioconferência** é atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="6a506-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="6a506-113">Quando você redefine manualmente o PIN de audioconferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="6a506-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="6a506-114">Quando você redefine manualmente o ID de conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="6a506-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="6a506-115">Quando a licença de **Audioconferência** deles é removida.</span><span class="sxs-lookup"><span data-stu-id="6a506-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="6a506-116">Quando o provedor de audioconferência de um usuário é alterado da Microsoft para outro provedor ou para **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="6a506-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="6a506-117">Quando o provedor de audioconferência de um usuário é alterado para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a506-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="6a506-118">Habilitar ou desabilitar o envio de e-mails para os usuários</span><span class="sxs-lookup"><span data-stu-id="6a506-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="6a506-119">É possível usar o Microsoft Teams ou o Windows PowerShell para habilitar ou desabilitar o envio de e-mails para os usuários.</span><span class="sxs-lookup"><span data-stu-id="6a506-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="6a506-120">![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**</span><span class="sxs-lookup"><span data-stu-id="6a506-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6a506-121">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="6a506-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="6a506-122">No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="6a506-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="6a506-123">No painel **Configurações de ponte**, habilite ou desabilite **Enviar e-mails aos usuários automaticamente de suas configurações de discagem forem alteradas**.</span><span class="sxs-lookup"><span data-stu-id="6a506-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="6a506-124">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6a506-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="6a506-125">**Usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6a506-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="6a506-126">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6a506-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6a506-127">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6a506-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="6a506-p102">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="6a506-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6a506-131">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="6a506-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="6a506-132">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a506-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="6a506-133">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6a506-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="6a506-134">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6a506-134">Related topics</span></span>

[<span data-ttu-id="6a506-135">E-mails enviados para os usuários quando suas configurações de Audioconferência são alteradas</span><span class="sxs-lookup"><span data-stu-id="6a506-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="6a506-136">Enviar um email para um usuário com suas informações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="6a506-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


