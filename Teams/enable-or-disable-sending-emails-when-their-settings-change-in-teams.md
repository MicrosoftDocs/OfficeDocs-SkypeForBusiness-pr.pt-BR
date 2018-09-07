---
title: Habilitar ou desabilitar o envio de emails quando a alteração de configurações de conferência de áudio nos Teams da Microsoft
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprenda a habilitar ou desabilitar Skype enviem emails para usuários quando configurações como o pin é alterado ou as alterações de número de conferência padrão no Microsoft Teams. '
ms.openlocfilehash: 5d18d039c379bb56a861ba6f6a36d23f301150b4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861887"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="b48db-103">Habilitar ou desabilitar o envio de emails quando a alteração de configurações de conferência de áudio nos Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b48db-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="b48db-104">Os usuários são notificados automaticamente por email quando estiverem habilitados para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="b48db-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="b48db-105">Pode haver momentos, no entanto, quando você deseja reduzir o número de emails que serão enviadas aos usuários do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b48db-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="b48db-106">Nesses casos, você pode desabilitar o envio de email.</span><span class="sxs-lookup"><span data-stu-id="b48db-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="b48db-107">Se você desabilitar o envio de emails, emails de conferência de áudio não serão enviadas aos seus usuários, incluindo emails para quando os usuários estão habilitados ou desabilitados para conferências de áudio, quando o seu PIN é redefinido e quando as alterações no número de telefone a ID de conferência e a conferência padrão .</span><span class="sxs-lookup"><span data-stu-id="b48db-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="b48db-108">Aqui está um exemplo de email enviada aos usuários quando eles estão habilitados para conferência de áudio:</span><span class="sxs-lookup"><span data-stu-id="b48db-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Email de conferência de áudio](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="b48db-110">Quando os emails são enviados para seus usuários?</span><span class="sxs-lookup"><span data-stu-id="b48db-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="b48db-111">Há vários emails que serão enviadas aos usuários em sua organização depois que eles estão habilitados para conferência de áudio:</span><span class="sxs-lookup"><span data-stu-id="b48db-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="b48db-112">Quando uma licença de **Conferência de áudio** é atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="b48db-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="b48db-113">Quando você redefinir manualmente os serviços de audioconferência PIN do usuário.</span><span class="sxs-lookup"><span data-stu-id="b48db-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="b48db-114">Quando você redefine manualmente o ID de conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="b48db-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="b48db-115">Quando a licença de **Conferência de áudio** seja removida deles.</span><span class="sxs-lookup"><span data-stu-id="b48db-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="b48db-116">Quando o provedor de serviços de audioconferência de um usuário for alterado da Microsoft para outro provedor ou **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="b48db-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="b48db-117">Quando o provedor de serviços de audioconferência de um usuário é alterado para Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b48db-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="b48db-118">Habilitar ou desabilitar o email que está sendo enviado a usuários</span><span class="sxs-lookup"><span data-stu-id="b48db-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="b48db-119">Você pode usar o Microsoft Teams ou o Windows PowerShell para habilitar ou desabilitar o email enviado aos usuários.</span><span class="sxs-lookup"><span data-stu-id="b48db-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="b48db-120">![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="b48db-120">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="b48db-121">No painel de navegação esquerdo, vá para **reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="b48db-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="b48db-122">Na parte superior da página **Pontes de conferência** , clique em **configurações de ponte**.</span><span class="sxs-lookup"><span data-stu-id="b48db-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="b48db-123">No painel de **configurações de ponte** , habilite ou desabilite a **Enviar automaticamente os e-mails para os usuários se alteram suas configurações de discagem**.</span><span class="sxs-lookup"><span data-stu-id="b48db-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="b48db-124">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b48db-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="b48db-125">**Usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b48db-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="b48db-126">Consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b48db-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b48db-127">Quer saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="b48db-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="b48db-p102">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b48db-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b48db-131">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="b48db-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b48db-132">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b48db-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="b48db-133">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b48db-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="b48db-134">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b48db-134">Related topics</span></span>

[<span data-ttu-id="b48db-135">Emails enviados aos usuários ao alteram suas configurações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="b48db-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="b48db-136">Enviar um email para um usuário com suas informações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="b48db-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


