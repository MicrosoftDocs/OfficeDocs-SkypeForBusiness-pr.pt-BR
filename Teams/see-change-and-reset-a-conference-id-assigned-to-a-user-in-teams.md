---
title: Consultar, alterar e redefinir um ID de conferência atribuído a um usuário no Microsoft Teams
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba como atribuir um ID de conferência a um usuário no Microsoft Teams e quais devem ser os parâmetros do ID de conferência. '
ms.openlocfilehash: 317216f84044eb404541a98d24c69b2f7fb61bc4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017081"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="77f5c-103">Visualizar e redefinir um ID de conferência atribuído a um usuário no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77f5c-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="77f5c-104">Uma ID de conferência é automaticamente atribuída a um usuário do Microsoft Teams quando eles estiverem configurados para conferência de áudio no Office 365 e usarem o Microsoft como um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="77f5c-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="77f5c-105">A ID de conferência atribuída é enviada no convite da reunião, quando a reunião foi agendada.</span><span class="sxs-lookup"><span data-stu-id="77f5c-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="77f5c-106">Cada reunião que um usuário agenda será obtido atribuída uma ID de conferência exclusivas.</span><span class="sxs-lookup"><span data-stu-id="77f5c-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="77f5c-107">Embora uma ID de conferência será criada automaticamente e atribuída a um usuário, pode haver ocasiões quando um usuário não deseja usar este e deseja defini-la a um certo número, ou quando os usuários não conseguir se lembrar ou tem perdido sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="77f5c-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="77f5c-108">Você pode usar o Centro de administração do Microsoft Teams ou o Windows PowerShell para exibir, alterar e redefinir a sua ID de conferência.</span><span class="sxs-lookup"><span data-stu-id="77f5c-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="77f5c-109">Um e-mail será enviado ao usuário com a ID da conferência e os números de telefone da audioconferência padrão ou, se você redefinir a ID da conferência, será enviado um e-mail diferente que incluirá a ID da conferência, mas não um PIN.</span><span class="sxs-lookup"><span data-stu-id="77f5c-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="77f5c-110">Para obter mais informações sobre como redefinir o PIN do organizador da conferência, [acesse aqui](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="77f5c-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="77f5c-111">Visualizar e redefinir as IDs de conferências</span><span class="sxs-lookup"><span data-stu-id="77f5c-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="77f5c-112">Para visualizar o ID de conferência</span><span class="sxs-lookup"><span data-stu-id="77f5c-112">To view the conference ID</span></span>

<span data-ttu-id="77f5c-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**</span><span class="sxs-lookup"><span data-stu-id="77f5c-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="77f5c-114">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="77f5c-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="77f5c-115">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="77f5c-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="77f5c-116">Em **Audioconferência**, veja **ID de conferência**.</span><span class="sxs-lookup"><span data-stu-id="77f5c-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="77f5c-117">É possível enviar todas as informações da conferência para o usuário em um e-mail que contém o ID de conferência e os números de telefone de áudio, clicando em **Enviar informações da conferência por e-mail**.</span><span class="sxs-lookup"><span data-stu-id="77f5c-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="77f5c-118">**Usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="77f5c-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="77f5c-119">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="77f5c-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="77f5c-120">Para redefinir o ID de conferência</span><span class="sxs-lookup"><span data-stu-id="77f5c-120">To reset the conference ID</span></span>

<span data-ttu-id="77f5c-121">É possível redefinir o ID de conferência para um usuário se ele esquecer o ID, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="77f5c-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="77f5c-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**</span><span class="sxs-lookup"><span data-stu-id="77f5c-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="77f5c-123">No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.</span><span class="sxs-lookup"><span data-stu-id="77f5c-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="77f5c-124">No topo da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="77f5c-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="77f5c-125">Em **Audio conferência**, clique em **Redefinir ID de conferência**.</span><span class="sxs-lookup"><span data-stu-id="77f5c-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="77f5c-126">Na janela **Redefinir ID de conferência** , clique em **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="77f5c-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="77f5c-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="77f5c-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="77f5c-128">**Usar o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="77f5c-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="77f5c-129">Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="77f5c-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="77f5c-130">O que mais você precisa saber?</span><span class="sxs-lookup"><span data-stu-id="77f5c-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="77f5c-131">Depois que uma nova ID de conferência é criada ou um é redefinido, o ID de conferência antigos não pode ser usado por chamadores.</span><span class="sxs-lookup"><span data-stu-id="77f5c-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="77f5c-132">Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites.</span><span class="sxs-lookup"><span data-stu-id="77f5c-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="77f5c-133">A ID de conferência deve atender a duração em dígitos, defina a ponte de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="77f5c-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="77f5c-134">Você não pode usar caracteres alfabéticos ou especiais de conferência IDs; somente números podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="77f5c-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="77f5c-135">O ID de conferência de todos os seus usuários de audioconferência deve ter sete dígitos por padrão; o número de dígitos não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="77f5c-135">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="77f5c-136">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="77f5c-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="77f5c-p107">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="77f5c-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="77f5c-140">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="77f5c-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="77f5c-141">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77f5c-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="77f5c-142">Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="77f5c-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="77f5c-143">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="77f5c-143">Related topics</span></span>

[<span data-ttu-id="77f5c-144">Experimentar ou comprar a audioconferência no Office 365</span><span class="sxs-lookup"><span data-stu-id="77f5c-144">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

