---
title: Ativar ou desativar o envio de e-mails quando alterar configurações de audioconferência no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: 'Saiba como ativar ou desativar o Skype de enviar e-mails para usuários quando configurações, como alterações de PIN ou o número de conferência padrão, são alteradas no Microsoft Teams. '
ms.openlocfilehash: a59553f26ee39e042fa28d9e58e7f5ae2aae21be
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23892498"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="18725-103">Ativar ou desativar o envio de e-mails quando alterar configurações de audioconferência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="18725-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="18725-104">Os usuários são notificados automaticamente por e-mail quando são habilitados para audioconferência.</span><span class="sxs-lookup"><span data-stu-id="18725-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="18725-105">Pode haver ocasiões, no entanto, em que você deseja reduzir o número de e-mails enviados aos usuários do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="18725-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="18725-106">Nesses casos, você pode desabilitar o envio de e-mails.</span><span class="sxs-lookup"><span data-stu-id="18725-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="18725-107">Se você desabilitar o envio de e-mails, nenhum e-mail de audioconferência será enviado para os usuários, incluindo e-mails notificando quando o usuário está habilitado ou desabilitado para audioconferência, quando o PIN é redefinido ou quando o número de telefone padrão e o ID de conferência são alterados.</span><span class="sxs-lookup"><span data-stu-id="18725-107">If you disable sending emails, all dial-in conferencing emails won't be sent to your users including emails for when users are enabled or disabled for dial-in conferencing, when their PIN is reset, when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="18725-108">Aqui está um exemplo de e-mail enviado aos usuários habilitados para audioconferência:</span><span class="sxs-lookup"><span data-stu-id="18725-108">Here is an example of the email that is sent to users that are enabled for dial-in conferencing:</span></span>
  
![E-mail de audioconferência](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="18725-110">Quando os e-mails são enviados aos seus usuários?</span><span class="sxs-lookup"><span data-stu-id="18725-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="18725-111">Vários e-mails são enviados aos usuários da sua organização depois que são habilitados para a audioconferência:</span><span class="sxs-lookup"><span data-stu-id="18725-111">There are several emails that are sent to users in your organization after they are enabled for dial-in conferencing:</span></span>
    
  - <span data-ttu-id="18725-112">Quando uma licença de **Audioconferência** é atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="18725-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="18725-113">Quando você redefine manualmente o PIN de audioconferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="18725-113">When you manually reset the user's dial-in conferencing PIN.</span></span>
    
  - <span data-ttu-id="18725-114">Quando você redefine manualmente o ID de conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="18725-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="18725-115">Quando a licença de **Audioconferência** deles é removida.</span><span class="sxs-lookup"><span data-stu-id="18725-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="18725-116">Quando o provedor de audioconferência de um usuário é alterado da Microsoft para outro provedor ou para **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="18725-116">When the dial-in conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="18725-117">Quando o provedor de audioconferência de um usuário é alterado para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18725-117">When the dial-in conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="18725-118">Habilitar ou desabilitar o envio de e-mails para os usuários</span><span class="sxs-lookup"><span data-stu-id="18725-118">Enable or disable email from being sent to dial-in users</span></span>

<span data-ttu-id="18725-119">É possível usar o Microsoft Teams ou o Windows PowerShell para habilitar ou desabilitar o envio de e-mails para os usuários.</span><span class="sxs-lookup"><span data-stu-id="18725-119">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email from being sent to users.</span></span>

<span data-ttu-id="18725-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**</span><span class="sxs-lookup"><span data-stu-id="18725-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>
1. <span data-ttu-id="18725-121">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="18725-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="18725-122">No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.</span><span class="sxs-lookup"><span data-stu-id="18725-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="18725-123">No painel **Configurações de ponte**, habilite ou desabilite **Enviar e-mails aos usuários automaticamente de suas configurações de discagem forem alteradas**.</span><span class="sxs-lookup"><span data-stu-id="18725-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="18725-124">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18725-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="18725-125">**Usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="18725-125">\*\*\*\* Using Windows PowerShell</span></span>
  
<span data-ttu-id="18725-126">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="18725-126">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="18725-127">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="18725-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="18725-p102">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="18725-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="18725-131">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="18725-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="18725-132">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="18725-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="18725-133">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="18725-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="18725-134">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="18725-134">Related topics</span></span>

[<span data-ttu-id="18725-135">E-mails enviados para os usuários quando suas configurações de Audioconferência são alteradas</span><span class="sxs-lookup"><span data-stu-id="18725-135">Emails sent to users when their settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="18725-136">Enviar um email para um usuário com suas informações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="18725-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


