---
title: Opções de email quando as configurações de Audioconferência mudam
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
description: 'Saiba como habilitar ou desabilitar Skype enviar emails para os usuários quando configurações como alterações de pino ou o número de conferência padrão é Microsoft Teams. '
ms.openlocfilehash: e1bb6df0a443f01ed3c9bc70d03eedc05f217ce4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092699"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="03361-103">Ativar ou desativar o envio de e-mails quando as configurações de audioconferência são alteradas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="03361-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="03361-104">Os usuários são automaticamente notificados por email quando estão habilitados para Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="03361-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="03361-105">No entanto, pode haver momentos em que você deseja reduzir o número de emails enviados para Microsoft Teams usuários.</span><span class="sxs-lookup"><span data-stu-id="03361-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="03361-106">Nesses casos, você pode desabilitar o envio de emails.</span><span class="sxs-lookup"><span data-stu-id="03361-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="03361-107">Se você desabilitar o envio de emails, os emails de Audioconferência não serão enviados para seus usuários, incluindo emails para quando os usuários estão habilitados ou desabilitados para a audioconferência, quando o PIN é redefinido e quando a ID da conferência e o número de telefone de conferência padrão são trocados.</span><span class="sxs-lookup"><span data-stu-id="03361-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="03361-108">Aqui está um exemplo do email que é enviado aos usuários quando eles estão habilitados para Audioconferência:</span><span class="sxs-lookup"><span data-stu-id="03361-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Exemplo de uma mensagem de email de Audioconferência](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="03361-110">Quando os emails são enviados para seus usuários?</span><span class="sxs-lookup"><span data-stu-id="03361-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="03361-111">Há vários emails enviados aos usuários em sua organização depois que eles são habilitados para audioconferência:</span><span class="sxs-lookup"><span data-stu-id="03361-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="03361-112">Quando uma **licença de Audioconferência** é atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="03361-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="03361-113">Quando você redefine manualmente o PIN de audioconferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="03361-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="03361-114">Quando você redefine manualmente o ID de conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="03361-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="03361-115">Quando a **licença de Audioconferência** é removida delas.</span><span class="sxs-lookup"><span data-stu-id="03361-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="03361-116">Quando o provedor de audioconferência de um usuário é alterado da Microsoft para outro provedor ou **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="03361-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="03361-117">Quando o provedor de audioconferência de um usuário é alterado para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="03361-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="03361-118">Habilitar ou desabilitar o envio de emails aos usuários</span><span class="sxs-lookup"><span data-stu-id="03361-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="03361-119">Você pode usar Microsoft Teams ou Windows PowerShell para habilitar ou desabilitar emails enviados aos usuários.</span><span class="sxs-lookup"><span data-stu-id="03361-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="03361-120">![Um ícone que mostra o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="03361-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="03361-121">Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.</span><span class="sxs-lookup"><span data-stu-id="03361-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="03361-122">Na parte superior da página **Pontes de Conferência,** clique em **Configurações de ponte.**</span><span class="sxs-lookup"><span data-stu-id="03361-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="03361-123">No painel **Configurações de** ponte, habilita ou desabilita Enviar emails automaticamente aos usuários se suas configurações de **discagem mudarem**.</span><span class="sxs-lookup"><span data-stu-id="03361-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="03361-124">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="03361-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="03361-125">**Usando Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="03361-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="03361-126">Consulte a [Microsoft Teams referência do PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="03361-126">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="03361-127">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="03361-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="03361-128">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="03361-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="03361-129">Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="03361-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="03361-130">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="03361-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="03361-131">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="03361-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="03361-132">[Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="03361-132">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="03361-133">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="03361-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="03361-134">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="03361-134">Related topics</span></span>

[<span data-ttu-id="03361-135">Emails enviados aos usuários quando suas configurações de Audioconferência mudam</span><span class="sxs-lookup"><span data-stu-id="03361-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="03361-136">Enviar um email para um usuário com suas informações de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="03361-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)