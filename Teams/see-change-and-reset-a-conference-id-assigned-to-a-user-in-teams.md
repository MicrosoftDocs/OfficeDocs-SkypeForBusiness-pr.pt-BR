---
title: Ver, alterar e redefinir a ID de conferência de um usuário
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
- seo-marvel-apr2020
description: Saiba como atribuir uma ID de conferência a um usuário no Microsoft Teams e quais os parâmetros de IDs de conferência devem ser.
ms.openlocfilehash: b57a419266ceca09a73fc4bf75bb12153e41ea91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117204"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="90d7b-103">Exibir e redefinir uma ID de conferência atribuída a um usuário no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90d7b-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="90d7b-104">Uma ID de conferência é atribuída automaticamente a um usuário do Microsoft Teams quando está configurada para Audioconferência no Microsoft 365 ou Office 365 e usa a Microsoft como provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="90d7b-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="90d7b-105">A ID da conferência atribuída é enviada no convite da reunião quando a reunião é agendada.</span><span class="sxs-lookup"><span data-stu-id="90d7b-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="90d7b-106">Cada reunião agendada por um usuário receberá uma ID de conferência exclusiva.</span><span class="sxs-lookup"><span data-stu-id="90d7b-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="90d7b-107">Embora uma ID de conferência seja criada e atribuída automaticamente a um usuário, pode haver momentos em que um usuário não deseja usá-la e você deseja defini-la como um determinado número, ou quando seus usuários não puderem se lembrar ou perderem a ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="90d7b-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="90d7b-108">Você pode usar o Centro de administração do Microsoft Teams ou Windows PowerShell exibir, alterar e redefinir a ID da conferência.</span><span class="sxs-lookup"><span data-stu-id="90d7b-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="90d7b-109">Um e-mail será enviado ao usuário com a ID da conferência e os números de telefone da audioconferência padrão ou, se você redefinir a ID da conferência, será enviado um e-mail diferente que incluirá a ID da conferência, mas não um PIN.</span><span class="sxs-lookup"><span data-stu-id="90d7b-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="90d7b-110">Consulte [Redefinir uma ID de conferência para um usuário no Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) para obter mais informações sobre como redefinir o PIN de um organizador de conferência.</span><span class="sxs-lookup"><span data-stu-id="90d7b-110">See [Reset a conference ID for a user in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) for more information about how to reset a conference organizer's PIN.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="90d7b-111">Visualizar e redefinir as IDs de conferências</span><span class="sxs-lookup"><span data-stu-id="90d7b-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="90d7b-112">Para exibir a ID da conferência</span><span class="sxs-lookup"><span data-stu-id="90d7b-112">To view the conference ID</span></span>

<span data-ttu-id="90d7b-113">![Um ícone que mostra o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="90d7b-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="90d7b-114">Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="90d7b-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="90d7b-115">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="90d7b-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="90d7b-116">Em **Audioconferência,** procure em **ID da Conferência.**</span><span class="sxs-lookup"><span data-stu-id="90d7b-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="90d7b-117">Você pode enviar todas as informações de conferência para o usuário em um email que inclui a ID da conferência e números de telefone de áudio clicando no **link** Enviar informações de conferência no email.</span><span class="sxs-lookup"><span data-stu-id="90d7b-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="90d7b-118">**Usando Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="90d7b-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="90d7b-119">Consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="90d7b-119">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="90d7b-120">Para redefinir a ID da conferência</span><span class="sxs-lookup"><span data-stu-id="90d7b-120">To reset the conference ID</span></span>

<span data-ttu-id="90d7b-121">É possível redefinir uma ID de conferência para um usuário se, por exemplo, ele a esquecer.</span><span class="sxs-lookup"><span data-stu-id="90d7b-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="90d7b-122">![Um ícone que mostra o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="90d7b-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="90d7b-123">Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="90d7b-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="90d7b-124">Na parte superior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="90d7b-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="90d7b-125">Em **Audioconferência,** clique **em Redefinir a ID da conferência.**</span><span class="sxs-lookup"><span data-stu-id="90d7b-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="90d7b-126">Na janela **Redefinir a ID da** conferência, clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="90d7b-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="90d7b-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="90d7b-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="90d7b-128">**Usando Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="90d7b-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="90d7b-129">Consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="90d7b-129">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="90d7b-130">O que mais você deve saber?</span><span class="sxs-lookup"><span data-stu-id="90d7b-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="90d7b-131">Depois que uma nova ID de conferência é criada ou uma é redefinida, a ID de conferência antiga não pode ser usada pelos chamadores.</span><span class="sxs-lookup"><span data-stu-id="90d7b-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="90d7b-132">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites.</span><span class="sxs-lookup"><span data-stu-id="90d7b-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="90d7b-133">A ID da conferência deve atender ao comprimento em dígitos definidos na ponte de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="90d7b-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="90d7b-134">Não é possível usar caracteres alfabéticos ou especiais em IDs de conferência; somente números podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="90d7b-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="90d7b-135">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="90d7b-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="90d7b-136">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="90d7b-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="90d7b-137">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="90d7b-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="90d7b-138">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="90d7b-138">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="90d7b-139">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="90d7b-139">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="90d7b-140">[Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="90d7b-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="90d7b-141">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="90d7b-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="90d7b-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="90d7b-142">Related topics</span></span>

[<span data-ttu-id="90d7b-143">Experimente ou compre Audioconferência no Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="90d7b-143">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)